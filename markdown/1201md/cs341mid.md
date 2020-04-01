title: CS 341 - Algorithms (midterm)
---

Check my [scattered notes](../cs341)

# Pre
**Algorithm**: effective unambiguous finite

**solve a problem**: Every instance I of problem P, when alg runs, it outputs a valid soln to P.

- **Line-code model**: Each line takes 1 time step.
- **Bit-cost model**: single bit take 1 step.

Neither is ideal.

**Word Ram model**: The Word RAM model is the computational model
in which for an algorithm run on an input of size \\(n\\),
- the memory of the algorithm is broken up into words of length \\(w=\log n\\), and
- any elementary operation (read, write, add, multiply, AND, etc.) on any single word
in memory takes 1 time step.

Big \\(O, \Omega, \Theta\\) notation.

little-\\(o,\omega\\).
\\[
\lim_{n\to\infty} {f(n)\over g(n)}=0 \implies f=o(g)
\\]

## Reduction

**Idea**: Use known algs to solve new problems.

### 3-sum
sum 3 distinct = 0

Trivial3Sum \\(O(n^3)\\)

Improved3Sum: sort, then binary search \\(-B_i-B_j\\). \\(O(n\log n+n^2\log n)=O(n^2\log n)\\).

Quadratic3Sum:
- sort
- given \\(B[i]\\), simultaneously scan from both ends of \\(A\\) looking for \\(B[j] + B[k] = -B[i]\\).
- start wit \\(j=i+1\\) and \\(k=n\\)
- \\(O(n\log n+n^2)=O(n^2)\\)



### target3sum
sum 3 distinct = T

\\[
(A[i]-T/3)+(A[j]-T/3)+(A[k]-T/3)=0
\\]

Then let \\(B[i]=A[i]-T/3\\).

### 3array3SUM
three arrays of \\(n\\) distinct integers, one from each \\(A,B,C\\) whose sum equals 0.

color them:
\\[
\left \\\\{
\begin{array}{l}
D[i]\gets 10A[i]+1\\\\
E[i]\gets 10B[i]+2\\\\
F[i]\gets 10C[i]-3
\end{array}\right.
\\]

To show ... is a reduction, we show that \\(\alpha\\) is a solution to instance \\(A'\\) **if and only if** \\(\alpha'\\) is a solution to \\(A\\) of ... .
## Terminology
**Running time** can only be determined by implementing a program and
running it on a specic computer.

Running time is influenced by many factors, including the programming
language, processor, operating system, etc.

**Complexity** (AKA growth rate) can be analyzed by high-level
mathematical analysis. It is independent of the above-mentioned factors
aecting running time.
## Loop Analysis
1. Theta-bounds throughout the analysis
2. O and Omega separately

**unit cost model**: where we assume that
arithmetic operations such as \\(+,-,\times\\) and integer division take time \\(\Theta(1)\\).

If we want to consider the complexity of arithmetic operation on integers
of arbitrary size, we need to consider **bit complexity**, where we express the
complexity as a function of the length of the integers (as measured in bits).


# Divide and Conquer
## Recursion
Recursion is a special type of reduction, where we reduce the original problem to the same problem, but on a smaller input.

guess-and-check and recursion tree method.

Use recursion tree, we propose master theorem:
\\(a\\ge 1, b> 1\\). Consider the recurrence
\\[T(n)=aT\\left({n\\over b}\\right) + \\Theta(n^y)\\]
where n is a power of b.

Denote \\(x=\\log_b a\\). Then
\\[
T(n)\\in
\\begin{cases}
\Theta(n^x) &amp; \\text{if}~y&lt;x \\\\
\Theta(n^x\log n) &amp; \text{if} ~y=x \\\\
\Theta(n^y) &amp; \text{if}~y&gt;x.
\\end{cases}
\\]

\\(y<x\\): **heavy leaves**: the value of the recursion tree is dominated by
the values of the leaf nodes.

**balanced**: the values of the levels of the recursion tree are
constant (except for the last level).

**heavy top**: the value of the recursion tree is dominated by the
value of the root node.

## The D&C design strategy
**divide**: Given a problem instance \\(I\\), construct one or more smaller
problem instances, denoted \\(I_1, \ldots I_a\\) (these are called subproblems).

**conquer**: For \\(1\le j \le a\\), solve instance \\(I_j\\) recursively, obtain solutions \\(S_1,\ldots,S_a\\).

**combine**: Given \\(S_1,\ldots,S_a\\), use an appropriate combining function to find the solution \\(S\\) to the problem instance \\(I\\).

sloppy and exact recurrence.

## Examples
Non-dominated Points: Find all the points that are not dominated by any other point

Closest Pair: Euclidean distance of two points is minimized. Using strip area: \\(\delta=\min\\\\{\delta_L,\delta_R\\\\}\\). And search in rectangle of \\(2\delta\times\delta\\).

Fase Matrix Multiplication.

Quick-Select and Median of median select.

# Greedy alg  
is one
1. Break down a problem into a sequence of decisions that need to be made, then
2. Make the decisions one at a time, each time choosing the option that is optimal at the moment (and not worrying about later decisions).

Interval Selection, Coin Change.

## Interval Colouring
A set \\(\mathcal A=\\\\{A_1,\ldots,A_n\\\\}\\) of intervals. For \\(1\le i\le n, A_i=[s_i,f_i)\\) (start and finish time).

Any two intervals receiving the same colour are always disjoint. We want to minimize the number of colours.

**Alg**: Sort by starting time.

## Knapsack
Profits \\(P=[p_1,\ldots,p_n]\\); weights \\(W=[w_1\ldots,w_n]\\); and a capacity, \\(M\\).
\\[
\begin{array}{ll}
\max & \sum_{i=1}^n p_ix_i \\\\
\mathrm{s.t.} & \sum_{i=1}^n w_ix_i\le M
\end{array}
\\]

0-1 Knapsack: \\(x_i\in \\\\{0,1\\\\}, 1\le i \le n\\).

Rational Knapsack: \\(x_i\in \mathbb Q\\) and \\(0\le x_i\le 1,1\le i \le n\\).

## Stable Matching
See [CO 342](https://notes.sibeliusp.com/pdfs/1195/co342.pdf#page=47).

# Dynamic Programming
**Optimal Structure**:
Examine the structure of an optimal solution to a problem
instance I, and determine if an optimal solution for I can be
expressed in terms of optimal solutions to certain
subproblems of I.

**Define Subproblems**:
Define a set of subproblems S(I) of the instance I, the
solution of which enables the optimal solution of I to be
computed. I will be the last or largest instance in the set
S(I).

**Recurrence Relation**: Derive a recurrence relation on the optimal solutions to the
instances in S(I). This recurrence relation should be
completely specied in terms of optimal solutions to
(smaller) instances in S(I) and/or base cases.

**Compute Optimal Solutions**: Compute the optimal solutions to all the instances in S(I).
Compute these solutions using the recurrence relation in a
bottom-up fashion, filling in a table of values containing
these optimal solutions. Whenever a particular table entry is
filled in using the recurrence relation, the optimal solutions
of relevant subproblems can be looked up in the table (they
have been computed already). The final table entry is the
solution to I.


## 0-1 Knapsack
We will need to develop a recurrence relation.

Other cases omitted. One case if \\(i\ge 2, m\ge w_i\\), then

\\[P[i,m] = \max\\\\{P[i-1,m], p_i+P[i-1,m-w_i]\\\\}\\]

where \\(m\in [0,M]\\) is the capacity.

The final answer is \\(P[n,M]\\).

## Coin Changing
A list of coin denominations, \\(1=d_1,d_2,\ldots,d_n\\) and a
positive integer \\(T\\), which is called the target sum.

We want to find \\(A=[a_1,\ldots,a_n]\\):
\\[
\begin{array}{ll}
\min & N = \sum_{i=1}^n a_i \\\\
\mathrm{s.t.} & T= \sum_{i=1}^n a_id_i
\end{array}
\\]

Here we use two things to store:
- \\(N[i,t]\\): optimal soln to the subproblem consisting of the first \\(i\\) coin denominations \\(d_1,\ldots,d_i\\) and target sum \\(t\\).
- \\(A[i,t]\\): number of coins of type \\(d_i\\) used in \\(N[i,t]\\).

Complexity: \\(O(DT^2)\\). Large *n* and small *T* is where this DP solution shines!

## Longest Common Subsequence
Two sequences \\(X=(x_1,\ldots,x_m)\\) and \\(Y=(y_1,\ldots,y_n)\\) over finite alphabet \\(\Gamma\\).

Find a maximum length sequence \\(Z\\) that is a subsequence of both \\(X\\) and \\(Y\\).

Consider \\(X'=(x_1,\ldots,x_{m-1})\\) and \\(Y'=(y_1,\ldots,y_{n-1})\\).
1. If \\(x_m=y_n\\), then \\(LCS(X,Y)=1+LCS(X',Y')\\)
2. Otherwise, \\(LCS(X,Y)= \max \\\\{LCS(X,Y'), LCS(X',Y)\\\\}\\).

With this info (2d array), we can print the LCS, starting from bottom right.

## Memoization
Remeber which subproblems have been solved; if same subproblem is encountered more than once during the recursion, the solution will be *looked up in a table* rather than being recalculated.
