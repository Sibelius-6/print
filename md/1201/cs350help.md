---
title: CS 350 - Operating Systems (help page)
layout: mdtoc
---
... Also, check my [miscellaneous notes](../cs350/)
# Basics
## Installing and Configuring OS/161
From [*Installing OS/161 in the student.cs Computing Environment*](https://www.student.cs.uwaterloo.ca/~cs350/common/Install161.html).

Previous steps...
- Step 0: Which Machine to Use?
- Step 1: Setting Up Your Environment
- Step 2: Obtain a Copy of the OS/161 Source Code

### Step 3: Configure OS/161 and Build the OS/161 Kernel

In `cs350-os161`,
```bash
cd os161-1.99
./configure --ostree=$HOME/cs350-os161/root --toolprefix=cs350-
cd kern/conf
./config ASST0
cd ../compile/ASST0
# only need to do configuration once.
bmake depend
bmake
bmake install
```
### Step 4: Build the OS/161 User-level Programs
user level, no need to do it every time, but to be safe...
```
cd $HOME/cs350-os161/os161-1.99
bmake
bmake install
```
> You could also make it simple: `bmake && bmake install`. The second cmd only run provided the first succeeded.

### Step 5: Try Running OS/161
```bash
cd $HOME/cs350-os161/root
cp /u/cs350/sys161/sys161.conf sys161.conf
```
Still, don't need to do it every time.

To run the os, `sys161 kernel-ASST0` or simply `sys161 kernel`.

## 350_submit
In `cs350-os161` directory: `/u/cs350/bin/cs350_submit 0`.

## 350-gdb
Source: [Debugging with GDB](https://www.student.cs.uwaterloo.ca/~cs350/common/gdb.html)

Two windows open, and both in `root` dir. Note that you need to have one `ssh userid@linux...` and the other one `ssh -Y userid@linux...`. Otherwise you will get msg: `Connection refused`.

One window (main): `sys161 -w kernel`.

The other one (debugger): `cs350-gdb kernel` and then,
```bash
(gdb) dir ../os161-1.99/kern/compile/ASST0
(gdb) target remote unix:.sockets/gdb
```

Then in debugger window:
```bash
(gdb) break panic
(gdb) c
# type commands in main window
# Then it will break on panic msg
(gdb) where
(gdb) bt
(gdb) list
```

Also
```bash
(gdb) watch x
```
and gdb will break every time the value of x changes. Sometimes it will be where you expect it to change, other times it will change in an unexpected place (e.g. a pointer error).

# "Useful" Scripts
## keep awake
Keep the connection to `linux.student.cs` environment.
```bash
#!/bin/bash
secs=0
while :
do
    s=$(( secs%60 ))
    m=$(( secs/60 ))
    echo -ne " \033[31m$m mins $s secs have passed\033[0m\033[0K\r"
    sleep 1
    : $((secs++))
done
```
Press `ctrl+c` or `ctrl+z` to terminate.

## 350 git
git version control. Better to store the credentials locally.
```bash
#!/bin/bash
echo -e "\033[31mEnter the commit message\033[0m"
printf "> "
read msg

echo -e "\033[31m************************\033[0m"

git add *
git commit --allow-empty -m "$msg"


git push -u origin master
```

## 350 find
Find a function/variable. Where is it defined?!?
```bash
#!/bin/bash
echo -e "\033[31mEnter the key word\033[0m"
printf "> "
read msg

grep -IR --exclude-dir=compile $msg
```
credit to Kevin Lancot on piazza.

# Assignments
## A2a
**Deadlock**

After `sys161 kernel`, the OS stucks at
```bash
sys161: System/161 release 1.99.06, compiled Aug 23 2013 10:23:34
# cursor blinking here...
```

Spinlocks are available in boot up before locks, probly use spinlock instead.

And take a look at `boot in startup/main.c`:
```c
void
boot(void)
{   ...
    ram_bootstrap();
    proc_bootstrap();
    thread_bootstrap();
    hardclock_bootstrap();
    vfs_bootstrap();
    ...
}
```

## A2b
Weird assignment numebering scheme here instead of 0 1 2 3 4, we go 0 1 2a 2b 3. There's a reason for that: used to be 0 1 2 3, and 5 sys call in A2,
but problem was the true CS fashion: leave it until last 12 hours...

`execv` is not going to change the process structure. We are going to change the program that the process acts: addr space, threads.

Takes two params, first: program you want to run; second: an array of pointers to string arguments. Null-terminated array.

Few lines of code. Most lines, you can copy and paste from elsewhere in the OS: `runprogram`. What does it do?
- open the program file `vfs_open`
- Once the program is open, create a new addrspace for that program. `as_create`. And then `curproc_create` which you might have seen when
I was talking about `fork`. Set addr space of current process. As you set the addr space, you need to load the program into the addr space.
- `load_elf` is the actual act of loading the program's binary info and copy it into the correct position. (`elf`: executable linkable format, probly seen in CS241).
It creates the code and data segment, NO stack segment.
- Creates the user stack using `as_define_stack`.
- Once you have done all that, you program is loaded and has addr space, and you call `enter_new_process`.
You are going to pass the address of the stack and the value return from `load_elf` which is the enter point function
that is the address of the first instruction to execute in the new program.

One more thing you need to do, which is also in `runprogram`, you need to activate the addr space. Remember `as_activate` doesn't activate anything. It's a terrible name.
What it does is to clear TLB. Cause we are changing the address space that this process is using, which means any TLB entries corresponding to previous address space, then
we need to clear old things.

Now we need to create stack. In `runprogram`, we just call `as_define_stack`. But over here, we need to do more work: pass all arguments to the new program by populating
the new program's stack with all args we have extracted from old programs. So my recommendation is to implement a new version `as_define_stack` that does both stack creation and copying arguments onto the stack for you.

Not only `execv` on this assign, go back and modify `runprogram` such that it can also take cmd line args.

And after your version of `as_define_stack`, it's safe to delete the old addr space. We don't delete it immediately since each of the steps can fail, and then you want to return error code from `execv`. Recall that it only returns calling program if it fails. If it succeeds then newprogram starts running.

Kernel also lives in the Virtual Memory and we are also going to destroy old addr. In kernel mode, we can directly access memeory in the user's addr space, but not safe. User program can do sth stupid, then the addr might be invalid. Kernel should NEVER trust the user address, so the safest: special function `copyin`/`copyout`: not just copy... but validate the addr first. Use `copyinstr`/`copyoutstr` when copying NULL terminated strings.

To copy
- `copyinstr`: copy the program into the kernel safely
- count \# of arguments: copy in each of the addresses of the array and checking how many do you have before NULL
- Then copy in each arg string

You need to allocate memory for pointer array and the strings, strings take memeory. You can use `strlen`, but remember it doesn't include NULL terminator. OR you could assume a total length &#92;(\le &#92;) 128 bytes.

We need to take all these args copied into the kernel, and put then onto the stack of new user program. But it's not sufficient to arbitrarily dump things. There are some conventions to dictate the things have to live on the stack so the new program knows where to find the parameters. True in OS/161 and modern OS. These arguments must go onto the stack with a particular byte alignment.

If you are storing an actual string on the stack, no alignment required, character can go anywhere at any kind of addr. But a pointer to a string must live at an addr that is divisible by 4. AND any other type must live at an addr divisible by 8. Macros: `args_size = ROUNDUP(args_size, 8);`.

You might notice I never talked about allocating any spaces for those args on stack, cuz you don't have to. When we create stack (`as_define_stack`), we already allocate whole memory for stack. You own the memory, don't need to malloc: calculate the address and write to it.

### Suggested Steps
1. Copy `runprogram` to `execv`, and make sure it compiles at least.
2. Copy the program name into `execv`, print it to the screen.
3. Do modification.<br>
Do not even attempt args part until you have it working. Arg passing is the hardest.
4. Count \# args, print to the screen.
5. Then copy str into the kernel, print to the screen.
6. Finally add the args to the stack.


### A2b testing
```bash
sys161 kernel "p uw-testbin/hogparty;q"

sys161 kernel "p testbin/sty;q"

sys161 kernel "p uw-testbin/argtesttest;q"

sys161 kernel "p uw-testbin/argtest tests;q"

sys161 kernel "p testbin/add;q"
```

## A3
### Overview
Dumbvm is a very limited virtual memory system with four major limitations.
1. A full TLB leads to a kernel panic.
2. Text (i.e. code) segment is not read-only.
3. It never reuses physical memory (i.e. kfree does nothing).
    - Requires restarting the OS after each test
4. It uses segmentation addresses.
    - which causes external fragmentation
    - *No need to fix this in W20*.

### TLB replacement
What you need to do is: when the TLB is full, choose a victim, evict them, insert a new TLB entry. However, we are not asking you to implement clock algorithm, or any cache efficiency algorithm, they are already there, you just call it in 1-2 lines. What we want to use is `tlb_random()`: choose random victim in TLB, evict them and replace them with new TLB entry.

- VM related exceptions are handled by `vm_fault()`
- `vm_fault()` performs address translation and loads the virtual address to
physical address mapping into the TLB.
    - Iterates through the TLB to find an unused/invalid entry.
    - Overwrites the unused entry with the virtual to physical address mapping required by the instruction that generated the TLB exception.
- Modify `vm_fault()` so that when the TLB is full, it calls `tlb_random()` to
write the entry into a random TLB slot.
    - That’s it for TLB replacement!
    - Make sure that virtual page fields in the TLB are unique.

### Read-Only Text Segment
Currently, TLB entries are loaded with  `TLBLO_DIRTY` on for all entries. Therefore, all pages are readable and writeable. When you determine the fault addr is in the first segment (text or code segment), you need to set the flag: Hey, this is the read-only addr. Later on in `vm_fault`, when you add the TLB entry to the TLB, you need to set the read-only flag. This is one line code:
`elo &= ~TLBLO_DIRTY;`. (Load TLB entries for the text segment with `TLBLO_DIRTY` off). However, this is not enough. When the program is actually loading itself into the addr space on the very first attempt to write the very first piece of memory into the addr space, you haven't even run the program then, this is just during the loading of the addr space. The MMU is going to throw an exception that says you are trying to write to read-only memory. You cannot actually that segment to be read-only until it's loaded because you need to be able to write to it in order to load the segment in the first place.

So what you need to do is to add another flag, add this flag into the addr space structure. This flag is to indicatre have I loaded the addr space or not. Now is false, then at the very end of `load_elf`, which is responsible for loading the addr space, you set that flag to be true. Then in `vm_fault`, you set the read-only flag if the addr space is loaded which you will know from the addr space structure and this is a code segment addr. This is not quite enough, we need one more tiny detail.

Here's the problem: when you are loading the addr space in memory, you are going to create TLB entries and because the same process is running, we are not going to clear the TLB out when we actually start running things. So when `load_elf()` completes, flush the TLB (with `as_activate()`) and ensure that all future TLB entries for the text segment has `TLBLO_DIRTY` off. And at that point, read-only memory will work.

But we still kinda have a bit of problem. If I am a user program in Windows, then I try to write to a constant, does Windows blue screen and die? So this is the last part of read-only memory. When a user program ties to write to read-only memory, it will cause the OS panics and dies. The operating system didn't do anything wrong, so maybe we shouldn't do that. So we want to detect such case, instead of making OS die, we need to kill the process.
- I.e. detect when a user program tries to write to read-only memory.
- Have vm_fault() return the appropriate error code / signal.
- That will be picked up when `mips_trap` (which handles exceptions and interrupts) which calls `kill_curthread()`.
- Modify `kill_curthread` (which handles the situation where user-level code has a fatal fault) to kill the current process.

There are three different approaches to modifying `kill_curthread`.
1. Add the code to kill the thread to kill_curthread. But this approach is not reusing code. Not very good programming style.
2. Create your own function very similar to `sys__exit` (say `sys_kill`) except that the exit code/status will be different. Because that process is not terminating from a call from exit, it terminated be cause it did a bad thing, so different exit code.
3. Modify your implementation of `sys__exit` to take a parameter that is the reason why `sys__exit` was called.

The point is: when you run the test that does try to write to read-only memory, the operating system shouldn't panic and die, the program should die and nothing else.

So that's the two ez parts of the assignment.
### Managing Memory
Operating system is actually responsible for managing all of the system resources.
So we have our memory here, initially unused. During bootstrap process, we use the function called `ram_stealmem(num_pages)` which is going to take the memory from that pointer (pointing to where the free memory is) and advances it. Don't modify this part of the code. What we want is after that bootstrapping process, we want you to manage what's left.

We want you to use paging. Even though OS/161 is using segmentation and MMU is OS/161 is doing paging. When we allocate stuff with `alloc_kpages` and `free_kpages`, the nomination that we are actually doling out the memory is the whole pages, so we need to manage the remaining memory as pages. So what we are going to do is we need to logically divide the memory left into pages, then we need to keep track  of which of those pages are freed or not. We do this in a structure called `coremap`.

**coremap**:
- Keep track of whether the frame is in use (1) or not (0).
- To allocate RAM search through core-map to find a large enough space.
- For allocations of multiple continuous pages, keep track of how many pages have been allocated in the core-map and free it as one big unit.
- e.g. Frame 0 and 1 are part of one big allocation and so a call to free frame 0 will free both frames 0 and 1.
- Version 2 of the core-map just keeps the essential information.

| Frame # | In Use?     | Page | of |
| :------------- | :----- | :-- | :-- |
| 0 | 1 | 1 | 2 |
| 1 | 1 | 2 | 2 |
| 2 | 0 | 0 | 0 |
| 3 | 1 | 1 | 1 |
| 4 | 1 | 1 | 3 |
| 5 | 1 | 2 | 3 |
| 6 | 1 | 3 | 3 |
| 7 | 0 | 0 | 0 |

When you free memory, do you tell how much memory to free? No, you pass and addr, and magically free how much memory which need to be freed. This is done by coremap. When we do a contiguous allocation of memory that is multiple pages at time, we indicate that is a part of a contiguous allocation.
Now we call free, we pass the addr of the starting addr, and notice that it is part of a contiguous allocation, so when freeing, we not only free this one, also go to next one and free because coremap stores that info. When you allocate memory, go to the coremap and search for some number of contiguous pages, mark them in use and set the page of how many to mark it as a part of contiguous allocation. When freeing, you find the entry in that table and fre all these entries that correspond to the contiguous allocation.

Version 1: Frame #, In Use?, Page, of. Version 2: Page. We only need to keep page column.
- Allocation would be the same.
- To free pages you need to check its successor to see if it is part of a larger allocation, i.e. is its count one higher than your count.
- Must also keep track of where the 0th frame is located in physical memory so that when memory is requested the kernel can return an address to the start of the allocation.

**For Both Version 1 or 2.** With either implementation, since you are implementing the core of
memory allocation, so you do not call `kmalloc` to allocate space for the
core-map, you simply calculate its size and write to it and leave the rest of RAM as
frames to be allocated.

Then how do you know how much memory you have available to you?  In `vm_bootstrap`, call `ram_getsize` to get the remaining physical memory in the system. It will give a low (just after memory for
bootstrap) and a high address.
Once `ram_getsize` has been called, do not
call `ram_stealmem` again! Logically partition the remaining physical
memory into fixed size frames. Each
frame is `PAGE_SIZE` bytes and its address
must be an integer multiple of the page
size (i.e. it is page aligned). The frame numbers and the page numbers must be divisible by `PAGE_SIZE`, so I do not have a frame number or frame addr that starts at 500, that doesn't work.

After you have figured out how many entries you need in your coremap and calculate the amount of space needed for coremap, you should put the coremap immediately following the area that we allocated for the bootstrap process. The coremap should not be tracking the memory used by the coremap. The frames that the core-map manages should start after the core-map data structure (rounded up to be a multiple of the page size).

You never have to kfree the core-map. You use it until the system shuts down in which case kfreeing it is no longer necessary.

There are parts of the OS that will be calling `kmalloc` before you create the coremap so
- You will need to create a flag to indicate (coremap exists yet or not) when the kernel can stop using `ram_stealmem` and starting using the core-map to allocated physical memory. Before the coremap exists, you need to use `ram_stealmem`.
- Look at `vm_bootstrap` to help decide exactly when you create the core-map.
- You must also modify the two functions `alloc_kpages(int npages)` and `free_kpages(vaddr_t addr)` to use the core-map once it has been created.

### Alloc and Free
`alloc_kpages(int npages)`
- Allocates frames for both `kmalloc` and for address spaces.
- Frames need to be contiguous.
- Do *not* have `alloc_kpages` interact directly with core map.
- Instead look at a function it uses, `getppages`, and modify it so it uses `ram_stealmem` before the core-map is created and uses the core-map after it is created. The code there is only useful for *before* the coremap is created, so leave that there for pre-coremap, and then add the part for post-coremap.
- The reason for this is because some parts of the kernel call `getppages` directly rather than calling `alloc_kpages`.

`free_kpages(vaddr_t addr)`:
- It currently does not do anything but it should be freeing pages allocated with `alloc_kpages`.
- We don’t specify how many pages we need to free so it should free the same number of pages that was allocated.
- It should update the core-map to make those frames available after `free_kpages` is called.

Then page tables... skipped for W20.
### User Address / Kernel Virtual Address / Physical Address
- Remember that you are always working with virtual addresses.
    - Only use physical addresses when loading entries in the TLB.
    - Virtual addresses are converted either by the TLB or by the MMU directly.
- Addresses below 0x8000 0000 are user-space addresses that are TLB mapped.
- Addresses between 0x8000 0000 and 0xa000 0000 are kernel virtual addresses that are converted by the MMU directly, i.e.
<br>Kernel virtual address – 0x8000 0000 = physical address
- `kmalloc` always returns a kernel virtual address.
- Do not use kmalloc to allocate frames

Also make sure you can run tests back to back 30 times since you have fixed the memory. Also just run on *one* CPU.

> Lec 20: 55:00

# Random stuff
## Some good problems for midterm??
*Explain the difference between internal and external fragmentation.*

From [CSE451, University of Washington](https://courses.cs.washington.edu/courses/cse451/00sp/misc/quiz2sol.txt):

> Internal fragmentation is the wasted space within each allocated block
because of rounding up from the actual requested allocation to the
allocation granularity.  External fragmentation is the various free
spaced holes that are generated in either your memory or disk space.
External fragmented blocks are available for allocation, but may be
too small to be of any use.

So paging eliminates external frag., not internal frag.
