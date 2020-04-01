title: A Gentle Review to MUSIC 270
---
These notes are created during Fall 2019. Here is a VexTab example:

<div class="vex-tabdiv"
    width=680 scale=1.0
    editor_width=680 editor_height=330>options space=20
    tabstave
    notation=true
    key=A time=4/4

    notes :q =|: (5/2.5/3.7/4) :8 7-5h6/3 ^3^ 5h6-7/5 ^3^ :q 7V/4 |
    notes :8 t12p7/4 s5s3/4 :8 3s:16:5-7/5 :h p5/4
    text :w, |#segno, ,|, :hd, , #tr


    options space=25
</div>

which is extremely fantastic for rendering music score in html.

# Musical Density: Triads, Seventh Chords, and Texture

> Supplementary chapter from *The Complete Musician*, Chapter 3

So far, we have studied melody and two-voice counterpoint. We now move into the third and final building block of tonal music: harmony. As stated earlier, harmony is most easily viewed as filling in the musical space provided by the counterpoint of two outer voices. The usual format for discussing harmony is the chorale texture: soprano, alto, tenor, and bass. Thus, the soprano and bass provide the **outer-voice counterpoint**, and the alto and tenor fill in the space between the soprano and bass, creating **chords**.

## Triads

### Triad Types

* diminished (d)
* minor (m)
* major (M)
* augmented (A)

### Triad Inversions

A triad is in **root position** if the root is the lowest-sounding pitch-that
is, the root is in the bass. If the third or the fifth of a triad appears in the
bass, the triad is in **first inversion** or **second inversion**.
It doesn't matter how the pitches above the bass are distributed;
the pitch in the bass determines whether the chord is in root position
or an inversion.

* Root position (Root in bass)
* First inversion (3rd in bass)
* Second inversion (5th in bass)

In tonal music, the character and behavior of chords depends on the
intervals formed among voices, especially between the bass and the voices
above it. As we've seen, root-position major and minor triads are consonant
(relatively stable) because of the perfect fifth between their root and fifth,
whereas diminished triads are dissonant (relatively unstable) because of the
diminished fifth between their root and fifth.

When inverted, each type of triad becomes progressively less stable. For
example, in first inversion, major and minor triads are less stable than in root
position, because they include the intervals of a perfect fourth and a minor or
major sixth. This is not true, however, for diminished triads: In root position
they are highly dissonant because of the diminished fifth, but in first inversion,
only consonant thirds and sixths sound above the bass (the tritone is less
audible, because it does not involve the bass).

In second inversion, major and minor triads are regarded as dissonant
because the perfect fourth is now formed with the bass, which drives the
harmony. (Remember that in two voices, the perfect fourth is considered
dissonant.) Even in textures of three or more voices (as in the present case),
when a perfect fourth is formed with the bass, we hear it as dissonant.
Both root-position and first-inversion triads are common in tonal music;
however, second-inversion triads, due to their greater instability, occur only in
restricted contexts. Thus while triads in root position and first inversion are
more or less interchangeable, second-inversion triads are in a class of their own.

## Figured Bass

Many composers who were active between 1600 and 1800 used a shorthand
notation to describe the intervals created by notes sounding above the bass.
This type of shorthand, **figured bass**, is a handy way of understanding chord
construction as well as melodic movement between chords. (Today's leadsheet
symbols of jazz and popular music serve a similar purpose.) Figured
bass is predicated on the fact that the bass is harmonically the most important
voice of any texture. A figured bass has two components:

1. A bass note.
2. Numbers, or "figures" -- listed under the bass -- that indicate the generic intervals formed by the bass and each of the other voices. The numbers are typically listed one below another, from largest to smallest.

<img src="/markdown/pics/music270/figured_bass.png" alt="figured bass example" width="100%">

### Figured Bass Realization

<img src="/markdown/pics/music270/fig_bass_realization.png" alt="fig_bass_realization" width="100%">

### Figured Bass Abbreviations

<img src="/markdown/pics/music270/fig_bass_abbr.png" alt="fig_bass_abbr" width="100%">

### Figured Bass Chromaticism

Figured bass follows the given key signature-that is, the notes above the
bass follow the given key signature unless the figure is altered. A few common
ways to indicate chromatic alterations to notes above the bass include:

* If there is an accidental on a pitch above the bass, the same accidental is
attached to the corresponding interval in the figured bass.
* If an accidental occurs on the pitch that is a third above the bass, the
number 3 is omitted and only the accidental is written.
* A plus sign or a slash through a number raises the pitch by one half step.
* If the bass note is chromatically altered, nothing changes in the figure,
since the figure indicates only intervals above the bass.

<img src="/markdown/pics/music270/fig_bass_chromaticism.png" alt="fig_bass_chromaticism" width="60%">

### Figured Bass and Melodic Motion

Figured bass can also show the melodic motion of individual voices,
especially voices that move by step. A dash between numbers
shows motion in the same voice, as viewed from the bass.

<img src="/markdown/pics/music270/fig_bass_melodic_motion.png" alt="fig_bass_melodic_motion" width="50%">

## Triads and the Scale: Harmonic Analysis

Each scale degree of a major or minor scale can support a triad constructed of
pitches from that scale. We use roman numerals to represent triads: The
numeral indicates the scale degree on which a triad is built, and the case of the
roman numeral reflects a triad's quality. Uppercase roman numerals are used
for major triads, lowercase numerals for minor triads, and diminished triads
are represented by lowercase roman numerals with the addition of a degree
sign.

### Scale Degree Triads Types in Major

<img src="/markdown/pics/music270/scale_in_major.png" alt="scale in major" width="100%">

### Scale Degree Triads Types in Minor

<img src="/markdown/pics/music270/scale_in_minor.png" alt="scale in minor" width="100%">

### Complete Harmonic Analysis

A complete harmonic analysis combines roman numerals and figured
bass. The roman numeral identifies the root (by scale degree) and quality of a
triad, and a figure identifies root position or inversion. Finally, recall
that figured bass can also identify melodic motion by individual voices
above the bass (such as 5-6 or 4-3).

<img src="/markdown/pics/music270/complete_harmonic_analysis.png" alt="complete Harmonic Analysis" width="50%">

## Harmony and the Keyboard

**Keyboard style** is a four-voice texture in which three notes (voices) are played
in the right hand, within the space of one octave, and one note (voice) is
played in the left hand. The notes in the right hand are labeled (from highest
to lowest) soprano, alto, and tenor. The bass is played with the left hand.
This helps to emphasize the outer voices, and is the most common hand
position we will use. Further, on occasion you will be writing in keyboard
style, although most of our writing will place the upper two voices (soprano
and alto) in the treble clef and the lower two voices (tenor and bass) in the
bass clef, a distribution called **chorale style**. Example 3.11 shows the harmonic
progression I-V-I in both keyboard style and chorale style.

### Four-Voice Styles

<img src="/markdown/pics/music270/4-voices-style.png" alt="four-voice-style" width="50%">


## Seventh Chords

Sonorities with four notes that can be stacked in thirds are called **seventh
chords**. We identify seventh chords by their two most audible features: the
type of triad formed by the root, third, and fifth of the chord; and the type of
seventh above the root of the chord. There are five important types of seventh
chords-though, like the triad types, they are not used with equal frequency.
Example 3.12 shows the following qualities of chords, built on the root C:

* major seventh chord (MM7)
* dominant seventh chord (Mm7)
* minor seventh chord (mm7)
* half-diminished seventh chord (dm7)
* diminished, or fully diminished, seventh chord (dd7)

<img src="/markdown/pics/music270/seven_chord.png" alt="seven_chord" width="70%">

### Inversion of Seventh Chords

<img src="/markdown/pics/music270/seven_inversion.png" alt="seven_inversion" width="70%">

When we analyze seventh chords with roman numerals, we use the following to show the chord qualities:

* MM7 and Mm7 chords use uppercase roman numerals.
* mm7 chords use lowercase roman numerals.
* dm7 chords use lowercase roman numerals, plus a slashed degree sign (<sup>&Oslash;</sup>).
* dd7 chords use lowercase roman numerals, plus a degree sign (&deg;).

### Scale Degree Seventh-Chord Types in Major and Minor

<img src="/markdown/pics/music270/7-in-major-minor.png" alt="7-in-major-minor" width="100%">

### A Complete Harmonic Analysis of Triads and Seventh Chords

<img src="/markdown/pics/music270/complete-triads-7-chords.png" alt="complete-triads-7-chords" width="100%">

## Musical Texture

So far we have explored triads and seventh chords in their most simple form:
as simultaneously sounding vertical sonorities. Vertical alignment is but one
of many ways that composers distribute the members of a chord.

**Texture** refers to many elements of music, including register and timbre
of instrumental combinations. But in particular, texture refers to music's
density (e.g., the number of voices and their spacing). Tonal music has many
types of texture, but we can group them into three basic categories, each of
which is distinguished by the way the melody is projected. The following
excerpts from the literature illustrate the three basic textures: monophonic,
polyphonic, and homophonic.

**Monophonic texture** is defined as a single-line melody with no
accompaniment. Both a cantus firmus and a tune you whistle are monophonic
textures. Schubert's last symphony begins monophonically with
horns that play the primary melody of the first movement (Example 3.16).
Note that a texture can be monophonic even though it might be played (e.g.,
in octaves) by more than one instrument.

**Polyphonic**, or **contrapuntal**, **texture** is the combination of two or more
melodies so there is no clear distinction between melody and accompaniment.

**Homophonic texture** is a cross between monophonic and polyphonic
textures, given that there is usually a clear melody accompanied by
additional voices. The accompaniments can be highly varied; this richness of
possibilities is why homophonic texture is the most widespread of the three
texture types in common-practice music. The vertical, block-chord chorale
texture we have been studying is one of the simplest types of homophonic
textures, given that the accompanying voices are rhythmically aligned with
the primary voice, which usually appears in the highest register.
In most homophonic textures, however, single harmonies are spread
out over time, with their chordal members distributed over one or more
beats, measures, or even multiple measures.

## Analytical Method

> Example 3.18C is the first 4 measures of *Mozart, Piano Sonata in C major, K. 545, Allegro*.

The harmonies in Example 3.18C unfold at a leisurely pace, given that there
are only seven chords in four measures. Depending on the composer, style
period, and type of piece, chords may change slowly or quickly. The rate of
harmonic change is called **harmonic rhythm**.

The preceding clunky analysis is improved by a more concise and informative
roman numeral analysis. (Note values that correspond to the duration
of each harmony reveal the harmonic rhythm.)

Mozart is able to write such a slow harmonic rhythm because of the
rhythmic interest created by the accompanimental figures, which-along
with the tune-contain each of the chord members. The broken-chord
accompanimental pattern in Example 3.18C, called an **Alberti bass**, is
common in the Classical style. The Alberti bass and other such
accompanimental patterns are effective because our ears collect the
individual pitches of the broken-chord figure into a single harmony.


---


# Chapter 1 - Musical Sound and Its Notation

This chapter seems to be a gentle introduction without much theory behind it.

## The Nature of Sound

Vibration, compression, rarefaction, sound, cycle, frequency, Hertz, amplitude, noise, periodic, pitch, non periodic.

## The Harmonic Series

Complex vibration, fundamental, harmonic, overtones. Tone color, timbre.

Musical Accent:

- dynamic accent: louder
- tonic accent: higher
- agogic accent: longer

## Notation

Greater perfect system, octave, neumes. Five-line **staff**, ledger lines, score, great stuff.

Clefs: bass treble tenor alto soprano

Chromatics: chromatics accidentals natural sharp flat

# Chapter 2 - Scale and Intervals

melodic interval, harmonic interval

Unison, prime, octave, fifth, fourth.

diatonic scale: 自然音阶

Diatonic intervals, compound itnervals, interval inversion

whole step, half step

## Quantity and Quality

minor seconds, major seconds.

Perfect, imperfect, augmented, diminished, tritones

## Chromatic Inflection

Chromatic half steps, diatonic half steps

doubly augmented/diminished. Double sharps, double flats.

enharmonic equivalents, enharmonic intervals

# Chapter 3 - Modes and Keys

When we listen to a melody, we hear its intervals as motional events combining to form phrases that link to shape the sounding line. In melody we experience the diatonic scale as an organized and coherent whole, a dynamic community of tones that relate through their mutual attractive forces. We refer to thie scheme of sounds as a melody's **mode**. (调式)

## Scale and Mode

Tonic final, dominant

Church modes: (skipped) Page 26

Locrian Mode

From Modality to Tonality

## Chromatic Scale

## Keys

key signature

Major/minor mode

Relative/parallel keys

circle of fifth

enharmonic keys

**Degrees of the major scale**:

```
C: Tonic
D: Supertonic
E: Median
F: Subdominant
E: Doninant
A: Submediant
B: Leading Note
```
<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w
    notes C/4
    notes D/4
    notes E/4
    notes F/4
    notes G/4
    notes A/4
    notes B/4
    notes C/5

    text :w,.-1, Tonic,Supertonic,Mediant,Subdominant,Dominant,Submediant,Leading tone

</div>

**Degrees of the minor scale**:

```
A: Tonic
B: Supertonic
C: Mediant
D: Subdominant
E: Dominant
F: Submediant
G: Subtonic
```

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w
    notes A/4
    notes B/4
    notes C/5
    notes D/5
    notes E/5
    notes F/5
    notes G/5
    notes A/5    

    text :w,.-1, Tonic,Supertonic,Mediant,Subdominant,Dominant,Submediant,Subtonic

</div>


Alternations to the minor mode: melodic/harmonic minor

# Chapter 4 - Rhythm and Meter

Rhythm, beat, note values, dot (附点), rest, tempo

## Musical Meter

meter, baronies, measure, duple meter, triple meter, quadruple meter (common time). Simple meter, compound meter.

Time signature, meter signature. Beam. Triplets, duplets.

Downbeat.

Syncopation & Hemiola (3:2)

## Octave & Measure

# Chapter 5 - Melodic Design

Music is an *occurent* art: like poetry, and dance, and drama, it happens as an unfolding in time.

## The Cantas

We begin our study of melody by crafying a line that conveys this sense of motion in its simplest terms. We call this fundamental music gesture a **cantus** (the Latin singular and plural form for "song").

### Initial Tone

Principle tones: \\(\hat 1,\hat 3,\hat 5\\)

### Cadence

A melody's close is called its **cadence**.

## Composing a Cantus

### Balance and Proportion

The cantus should extend in length anywhere from nine to sixteen tones. A line of fewer tones will generate little direction and development, while a line of more tones will rist the continuity of a single gesture. Stepwise motion will secure the coherence and direction of the cantus, and leaps will introduce drama and variety. These two types of motion, **conjunct** and **disjunct**, complement each other and continually interact within the line. Long stretches of stepwise motion will sound dull and lifeless, while an unrelieved series of leaps will sound erratic and incoherent.

The leap of a fifth or a sixth presents a major tensional event in the cantus. When a fifth or a sixth occurs as the line's opening event, the leap is considered prepared, but it will need to be resolved.

As a lesser tension, the leap of fourth is not so sensitive.

Leaps can be introduced to the line singly or in pairs. When paired, one leap will be a third.

When two notes relating by step alternate, a **trill** results.

### Tritone

Medieval musicians considered the tritone (the augmented fourth and diminished fifth) to be "dangerous" interval and avoided its use in melody as a *diabolus in musica* (devil in music).

### Apogee and Perigee

We call the highest internal tone the **apogee**. We call the lowest internal tone the **perigee**.


# Chapter 6 - Duple Paraphrase '

<mark>' Note that this chapter is marked **important** to review.</mark>

## Introduction

In language, an effective writing style is characterized by the presence of supporting and elaborative detail. By substituting specific words for general ones, by expanding with concrete examples and details, or by employing figures of speech (smiles and metaphors), we invest a simple "plain-sense" statement with clarity and interest. This process is called **paraphrasing**. When we paraphrase, we go beyond the simple statement, we enlarge upon it, to more fully express its meaning.

## Melody Paraphrase

The directional pointing of almost every interval in basic melody is particularized by a specific **melodic figure**.

### Paraphrase in Practice

It first arises in the ancient (and ongoing) practice called **heterophony**. Their extended melodic elaborations, sung to one syllable, are called **melismas**.

<img src="https://upload.wikimedia.org/wikipedia/commons/2/2f/Syllabic_and_melismatic.png" alt="melismas" width="100%">

From [声乐复音词汇的定义](http://music.tnua.edu.tw/music/PS/chinese/terms.htm):
> Heterophony (异音): 「异音」一词，是由希腊文heteros「不同的」，及phone「声音」二字所组成，最初由柏拉图（Plato）于教学中使用，借以表示单旋律音乐进行时所产生变化的情形，但定义并不明确。在民族音乐学中，「异音」是复音音乐最初的一种形式，意指很多人以齐唱（或齐奏）的方式演唱（奏）同一旋律，但所演唱（奏）的旋律音高或节奏无法完全一致，而产生另外的旋律或节奏线条，此种现象即为异音（Heterophony）。William P. Malm则认为「异音」一词应以「相同的声音」（disphony）代替，因音乐在异音现象的进行中，每一个声部还是同时作相同旋律的进行，只是因为节奏上的变化，才使音乐的进行有所不同。法国语言音乐研究中心的民族音乐学者Simha Arom，在关于非洲音乐的研究上，也采用Malm的观点。

> 异音现象的产生，是由于一种意外（accident）或偶然（hazard）的情形下发生，通常是因演唱者未经音乐训练，在演唱同一个旋律时，产生不同的音高与节奏，造成两个或数个旋律线条叠置在一起，形成「偶然性」的异音现象。这种偶然、意外的现象，后来造成了当地的族人音乐美学观的改变，而驱使他们逐渐的从单音音乐中的意外，去摸索或追求复音音乐的现象，最后甚至刻意造成这样的演唱形式。

> Counterpoint (对位法): Counterpoint这个字，是由拉丁文punctus contra punctum衍生而来的，为「音符对音符」或是扩充为「旋律对旋律」之意。在西方音乐中，是以规则的运用两个或两个以上同时发声的旋律，将其相互组合。而在非欧洲的传统音乐中，所使用的对位方式是相当自由的，并没有任何的规则存在。其对位的方式，也是由两个或两个以上的旋律或声部，两者同时发声而组成，虽然声部彼此之间的旋律与节奏都有所差异，但都具有自己的特色且个别独立，并共同构成音乐的整体。

A sometimes excessive use of melodic decoration occurs in late medieval and early Renaissance keyboard arrangements of vocal music. Called **intabulations**, these compositions abound in various stereotyped ornamentation formulas.

In the organ chorales of the Baroque era, elaborative melody reaches new heights, in a skillful blending of paraphrase -- melody within melody -- and ornamentation. In the nineteenth century, favorite melodies from opera and art song were popularized in piano transcriptions -- often by the same composer. Paraphrase technique represents an essential skill for __jazz__ performer. A single popular song can accommodate any number of elaborative interpretations, by singer and instrumentalist alike.

## Duple Paraphrase

We meet the primary type of melodic elaboration in **duple paraphrase**: each whole-note measure of the cantus is expressed in two half notes, which articulate the basic pulse.

### Melodic figures

> As a note here, I would recommend learning from [Embellishing tones](http://openmusictheory.com/embellishingTones.html).

For the present, we will limit our vocabulary to twelve **melodic figures** common to vocal melody. A few carry historical names; the others are given names here for ease of recognition and convenience in discussion.

**Neighbor motion** and **prime embelishment** elaborate the interval of a unison (prime).

Neighbor motion (N):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w A-A/4 |
    notes :h A-G-A/4 | A-B-A/4

</div>

Prime embellishment (PEM):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w A-A/4 |
    notes :h A/4-C/5-A/4 | A-F-A/4


</div>

The **échappée**, the ***skip-step***, and the **doubleskip** elaborate the interval of a second.

Échappée (E):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w C/5-B/4 |
    notes :h C/5-D/5-B/4 =|| :w B/4-C/5 | :h B/4-A/4-C/5 =||


</div>

Skip-step (SS):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w C/5-B/4 |
    notes :h C/5-A/4-B/4 =|| :w B/4-C/5 | :h B/4-D/5-C/5 =||


</div>

Doubleskip (DS):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w C/5-B/4 |
    notes :h C/5-G/4-B/4 | C/5-E/5-B/4 =|| :w B/4-C/5 | :h B/4-E/5-C/5 | B-G/4-C/5 =||


</div>

**Passing motion**, the **skip-step**, and the **broken chord** elaborate the interval of a third.

Passing (P):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w A/4-C/5 |
    notes :h A/4-B/4-C/5 =|| :w C/5-A/4 | :h C/5-B/4-A/4 =||


</div>

Skip-step (SS):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w A/4-C/5 |
    notes :h A/4-D/5-C/5 =|| :w C/5-A/4 | :h C/5-B/4-A/4 =||


</div>

Broken chord (BC):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w A/4-C/5 |
    notes :h A/4-E/5-C/5 | A-F/4-C/5 =|| :w C/5-A/4 | :h C/5-F/4-A/4 | C-E/5-A/4 =||


</div>


The **cambiata**, **incomplete passing motion**, the **skip-step**, and the **broken chord** elaborate the interval of a fourth.

Cambiata (C):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w D/5-A/4 |
    notes :h D/5-C/5-A/4 =|| :w A/4-D/5 | :h A/5-B/4-D/4 =||


</div>

Incomplete passing (IP):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w D/5-A/4 |
    notes :h D/5-B/4-A/4 =|| :w A/4-D/5 | :h A/4-C/5-D/5 =||


</div>

Skip-step (SS):



<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w D/5-A/4 |
    notes :h D/5-G/4-A/4 =|| :w A/4-D/5 | :h A/4-E/5-D/5 =||


</div>

Broken chord (BC):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w D/5-A/4 |
    notes :h D/5-F/4-A/4 | D/5-F/5-A/4 =|| :w A/4-D/5 | :h A/4-F/5-D/5 | A/4-F/4-D/5 =||


</div>

**Arpeggigation** and the **skip-step** elaborate the interval of a fifth. **Arpeggigation** elaborates the interval of a sixth.

Two additional figures available to our paraphrasing are the **anticipation** and the **repetition**. Their usefulness in the elementary rhythm of duple paraphrase is slight because they do not enhance the melody's contour. We will limit the repetition to one or two occurences within the line and hold the anticipation to a possible apperance at the final cadence.

Arpeggigation (ARP):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w G/4-D/5 |
    notes :h G/4-B/4-D/5 =|| :w D/5-G/4 | :h D/5-B/4-G/4 =||


</div>

Skip-step (SS):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w G/4-D/5 |
    notes :h G/4-E/5-D/5 =|| :w D/5-G/4 | :h D/5-F/4-G/4 =||


</div>

Arpeggigation (ARP):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w E/5-G/4 |
    notes :h E/5-C/5-G/4 | E/5-B/4-G/4 =|| :w G/4-E/5 | :h G/4-B/4-E/5 | G/4-C/5-E/5 =||


</div>


Anticipation (ANT):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :h A/4 :w G/4 =||
    notes :h A/4 G/4 | :w G/4 =|=


</div>

Direct-note repetition (REP):

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false

    notes :w D/5  C/5 |
    notes :h D-D-C/5


</div>

## Formal Design

Vocal melody rides on the breath, and breath is a limited store that requires constant replenishing. "Breathing out and breathing in" is a s necessary and natural to melody as to life itself. That part of melody that rides on a "breathing out" we call a **phrase**, and each phrase cadence is punctuated with a "breathing in."

Rests and breathing pauses figure importantly in the shaping of a melodic line. They offer the contrast of silence to the sounding tones, and serve to articulate the melody, much as punctuation articulates language.

The half rest in duple paraphrase acts as an emphatic punctuation of definite duration, and the **luftpause** ("breathing" pause) as a musical comma of brief and indefinite duration. The luftpause is notated as an apostrophe above the staff.

### Phrase Cadences

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true
    tablature=false
    clef=alto

    notes :w D/4-C/4-A/3-B/3-C/4-E/4

</div>


Four phrase cadences are available to duple paraphrase. A phrase can close on an undecorated cantus tone by notating it as a whole note followed by a luftpause,

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true    
    time=2/2
    tablature=false
    clef=alto

    notes :h D/4-E/4 | C/4-B/3 | A/3-G/3 | B/3-D/4 |
    notes :w C/4 |
    notes :h E-G/4 |
    text :w,.3,.font=courier-24-, , , , , , &#8217;



</div>

as a half note followed by a half rest,


<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true    
    time=2/2
    tablature=false
    clef=alto

    notes :h D/4-E/4 | C/4-B/3 | A/3-G/3 | B/3-D/4 |
    notes :h C/4 ## |
    notes :h E-G/4 |

</div>


and as a whole note followed by a half rest.

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true    
    time=2/2
    tablature=false
    clef=alto

    notes :h D/4-E/4 | C/4-B/3 | A/3-G/3 | B/3-D/4 |
    notes :w C/4 |
    notes :h ## E/4 |


</div>

Any melodic figure can be "broken" with a luftpause to create phrase closure at mid-measure.

<div class="vex-tabdiv">

options space=20  width=750

    tabstave
    notation=true    
    time=2/2
    tablature=false
    clef=alto

    notes :h D/4-E/4 | C/4-B/3 | A/3-G/3 | B/3-D/4 |
    notes :h C/4 F/4 |
    notes :h E-G/4 |
    text :w,.3,.font=courier-24-, , , ,&#x2063;
    text :h,.3,.font=courier-24-, &#x2063;, &#8217;



</div>


When either of these last two cadence patterns occurs, the succeeding phrase will open on a measure's second beat. This introductory tone is called an **[anacrusis](http://terms.naer.edu.tw/detail/1293487/?index=3)**, a Greek word meaning "to push back" -- that is, the opening of the succeeding phrase is "pushed back" to the preceding half note.

### Displacing a Cantus Tone

The elementary rhythm of duple paraphrase will allow only an occational displacement of the cantus tone to its measure's second half, either as a phrase anacrusis, or as the inclusive tone of a melodic figure. This technique is called **rhythmic displacement**. When displacing a cantus tone, take care that you do not create a downbeat-to-downbeat tritone (augmented fourth, diminished fifth): the metrical accent will emphasize the outlined tritone and so disrupt the flow of the line.

## Melodic Design

### Initial Measure

You can open the paraphrase in one of three ways: the first cantus tone can be notated as a whole note, as a half note (an anacrusis) following a half rest, or as a half note. In the last case the first interval of the cantus will accept a melodic figure.

### Final Cadence

The penultimate (倒数第二) cantus tone will stand on its measure's downbeat. This measure will accept either an échappée, a skip-step, or an anticipation of the final cantus tone. The last measure of the paraphrase will carry a whole note.

## Composing a Duple Paraphrase

Begin by selecting a cantus. To avoid predictability, vary the phrase lengths and the cadential types.

Compose a phrase at a time.

The ultimate test of a melodic paraphrase is its singability. When you identify a problem, correct it in the larger context of the phrase, not in isolation.


# Chapter 7 - Harmonic Framework '

<mark>' Note that this chapter is marked **important** to review.</mark>

When we sing or play two melodies together, we call their relationship **counterpoint**. The term derives from the Latin phrase *punctus contra punctum*, or "note (punctus) against note," and by extension, "melody against melody."

When we increase the vertical distance between our two melodies, we establish a framework for a larger music and define a tonal space for additional melodic lines. When all the melodic lines of this larger music move in the same rhythm, the texture is decribed as **homorphythmic**, and the music is called **homophony**.

Two melodies set in counterpoint express their relationship in the intervals formed by their simultaneous tones. These "singable spaces" are called **harmonic intervals**, from the Greek word *harmonia*, a "fitting together." When harmonic intervals are sounded in isolation, apart from a musical context, we classify them according to their aural effect, whether stable or unstable, calm or tense. Intervals that sound calm and stable are called **consonant**, from the Latin word *consonare*, "to sound together," or "to agree." Intervals that sound tense and unstable are called **dissonant**, from the Latin word *dissonare*, "to sound apart," or "to disagree."

## The Soprano-Bass Framework

The elements of harmonic motion are ideally studied in a whole-note homophony.

The upper voice of this frame is called the **soprano** (from the Italian *sopra*, or "above"), and is notated on the treble staff. The lower voice is called the **bass** (from the French *bas*, or "low"), and is notated on the bass staff. The normal vocal ranges of soprano and bass span compound fifths: the soprano ascends from middle C and the bass ascends from low R. On occasion, these ranges may be extended by one tone at either extreme. In order to accommodate the alto and tenor voices, the distance between soprano and bass will never be **less than a fifth**.

The relationship of these melodies is described in terms of four [relative motions](http://openmusictheory.com/motionTypes.html): contrary, similar parallel, and oblique. (See page 79 for details). **Contrary** and **similar** motions will best promote the independence of the soprano and bass lines. Although **parallel** motion can provide a "lock step" the two melodies, merging their individual gestures. Limit each apperance of parallel motion in your soprano-bass dialogue to four successive beats. **Oblique motion** in note-against-note homophony commonly involves an inner voice. (In oblique motion, one voice is stationary, while the other voice moves (in either direction). The stationary tone may or may not be rearticulated.)

The harmonic intervals available to this framework are the six historical consonances (and their compounds): **the perfect octave and fifth and the major and minor sixth and tenth**. Because of their relative instability -- and consequent mobility -- sixths and tenth will best promote the harmonic motion of your soprano-bass dialogue. Because of their stability and static weight, the octave and fifth should occur infrequently and will require special treatment.

The fifth (or compound fifth) will occur on penultimate beat of the music when the soprano carries a \\(\hat 2 - \hat 1\\) cadence. The static weight of this fifth is minimized when approached by contrary motion. When this cadential fifth is approached by similar motion (called a **direct fifth**), the soprano will move by step. The fifth can approach by contrary motion, or by similar motion when soprano moves by step.

The octave (or compound octave) will always occupy the music's final beat, and it will occur on the opening beat when the soprano carries the tonic. Like the fifth, the octave can be approached by similar motion (called a **direct octave**) when soprano moves by step. The octave can be introduced by contrary motion within the three-beat stepwise pattern called **tone exchange**.

Finally, two fifths or two octaves may not sound in direct succession, whether the motion between the voices is parallel or contrary.

### Initial Beat
To establish the mode at the music's outset, the bass will **always** begin on the **tonic**, whether the soprano begins on \\(\hat 1, \hat 3, \hat 5\\).

### Cadence
**Clausula vera**: true close: \\(\hat 2-\hat 1\\) and \\(\hat 7 -\hat 8\\)

**Harmonic cadence**: \\(\hat 5 -\hat 1\\) bass cadence

### Cross-Relation
When a *chromatic* pitch in one melodic line sounds in succession with its *natural* counterpart in a second line, the jarring effect is called a **cross-relation**.

### Designing the bass
* Singable melody
* freer introduction and treatment of lepas. Large leaps in the bass must be prepared and resolved
* A sixth or an octave can occur as the bass line's opening event. A leap of fourth or a fifth is less sensitive.
* If prepared, no need to be resolved. If resolved, no need to be prepared.

<img src="/markdown/pics/music270/pre_unre.png" alt="prepared unresolved" width="100%">

## Creating a Soprano-Bass Framework
### Opening Bass Gambits
Plot and sing each bass gambit before notating: use your ear and eye before your pencil. Plan linearly and check vertically. Identify the harmonic intervals by number between the staves.

# Chapter 8 - Chordal Succession
## Chords
Refer to the first supplementary chapter...

## Tenor and Alto
The normal vocal ranges of both inner voices span compound fifth:
- tenor: from an octave below middle C to a fifth above
- alto: from a fourth below middle C to a ninth above

However, in homophony, their ranges rarely exceed a sixth.

### Voice Spacing
When SAT sound adjacent chord tones, **closed postion**. When one (sometimes 2) chord tones are skipped between soprano and alto or alto and tenor, **open position**.

### Voice Crossing and Voice Overlap

**Voice crossing**: When two voices momentarily trade positions, the higher voice becoming the lower.

**Voice overlap**: When the higher of two voices moves to a tone lower than the preceding tone of the lower voice; or conversely, when the lower voice moves to a tone higher than the preceding tone of the higher voice.

### Chord Doubling
Any chord tone can be doubled, however, as each chord of our homophony must be complete. The cadential tonic is exceptional; see **The Authentic Cadence**.

### Consecutive Perfect Intervals
Two voices in *parallel* motion should not be sound the same perfect interval in direct succession, whether it be a unison, a fifth, or an octave.

### Figured Bass
Numbers are employed below the bass to indicate the intervals formed between bass and each of the upper voices.

## The Authentic Cadence
* Soprano: 2 - 1 or 7 - 8
* Tenor or alto sounds the other
* The remaining voice, tenor or alto, sounds a falling 5 - 3 close, doubling the bass dominant and supplying the third or the final triad.

Note that the final triad lacks its fifth.

### Picardy Third

Minor-mode music from the late Renaissance through the Baroque typically cadences on a major triad by rasing the final chord's third.

## Composing a Modal Homophony
Two "rules of thumb" (tenor and alto):
1. When a tone is common to two or more successive chords, retain it in the same voice.
2. Otherwise, move each voice to the nearest available chord tone.

### Completing the Homophony
*Use your ear and your eye before your pencil*.

# Chapter 9 - Melodic Dialogue
Polyphony: two melodies, each distinctive in tonal contour and rhythmic profile, relating in a counterpoint of simple consonances, sparingly seasoned with dissonance.

## Melodic Rhythm
**Rhythmic patterns** characterize the rhythmic modes.

Each rhythmic pattern begins on a measure's downbeat, is complete within the measure, and repeats. In this regard, it resembles the repeating pattern of syllables in poetry called a **foot**.

Trochaic rhythm: 3/2 measure with a whole note followed by a half note. Tribrachic: 3/2, 3 half notes. (don't think we covered this in music 270 with Laitz book...)

## The Lower Voice
A cantus will sere as the lower voice. 3/2, Trochaic.

## The Upper Voice
3/2, tribrachic.

## The Counterpoint
对位法

Because of their (similar, parallel and oblique motions) static weight and duplicating effect, perfect intervals require careful treatment in the light texture of two-part polyphony. So limit its apperance to the measure's second beat.

## Four Dissonant Melodic Figures

- Perfect fourth
- major and minor seconds, seventh, and ninth
- tritones (aug fourths and dim fifths)

### Initial Measure
opening harmonic interval: unison, third, fifth, octave, tenth. When the upper voice enters on the second beat of the measure, the first two tones constitute an anacrusis.

### Cadence
clausula verta: 2 - 1 and 7 - 8. This polyphonic cadence creates the harmonic motion of major sixth-to-perfect octave.

### Cross-Relations
Chromatic within the music need to be introduced with care to avoid possible cross-relations.

## Composing a Melodic Dialogue
Begin by choosing a cantus and deciding its voice: bass, tenor or alto.

# Chapter 10 - Triple Paraphrase
Through rhythmic figures we enter each measure of the line and articulate its temporal potential. These patterns of pitch and rhythm combine to form the compose figures called **motives**; these motives associative to convey the melody's vital form.

## Paraphrase in Triple Meter
### Rhythmic Patterns
Four are available:
- trochaic and tribrachic.
- The trochaic ordering of whole note-half is reversed in **iambic rhythm**.
- **Dactylic rhythm** offers a buoyant alternative to tribrachic rhythm. The first half note is dotted, agogic sound. The succeeding quarter note counteracts this agogic, propelling the line forward to the upbeat half note.

From wiki greensleeves,

<img src="https://upload.wikimedia.org/score/f/w/fwgn6erx9khoyxblj9sylqwr5gm8jl5/fwgn6erx.png" alt="greensleeves" width="100%">

All these rhythmic patterns can be found in **augmentation** (longer note values) or **diminution** (shorter note values).
### Melodic Figures
Any one of the three-note melodic figures can be combined with either the trochaic or iambic rhythmic patterns.

... Finally, one melodic figure can be developed through elision by overlapping upper and lower neighbor motions and eliding the common one. This four-note figure is called **double neghbor**.

## Formal Design
Motives link to form a phrase, and phrases join to form a **period**, the name given to a complete musical sentence.
- Antecedent-consequence period is the most common. Avoids strong resolution, then closes on the tonic.
- Symmetricial phrasing.
- Bar form, when a repeat sign is placed at the end of the antecedent phrase.

### Phase Cadences
- whole note followed by a half rest
- a dotted whole note followed by a luftpause
- whole note followed by a luftpause

The asymmetrical **phase group** contrasts with the symmetry (or near symmetry) of the antecedent-consequent and bar-form types.

### Displacing The Cantus Tone
- Does the "new" downbeat encourage the line's primary contour?
- Have you inadvertently created a downbeat-to-downbeat tritone?
- Does the melodic figure gained justify the displacement?

## Melodic Design
Purpose: enlarge upon the cantus through articulation of its measures by rhythimic patterns.


# Chapter 11 - Vocal Duet
Lively conversation between two voices.

## The Text

## The Upper Voice
Unlike paraphrasing, the upper voice of the vocal duet is not based on a cantus.

## Composing a Vocal Duet


# Chapter 12 - Tonic Confirmation '
<mark>' Note that this chapter is marked **important** to review.</mark>

Music's *harmonia*, the "fitting together" of its linear parts, came to be heard not simply as a by-product melodic interaction, but more importantly, as a significant propulsive force in its own right.

## Chords of Dominant Function
### Passing 6/4
This 6/4 chord is dissonant because it sets a fourth against the bass.

Two types:
- passing \\(P_4^6\\) (See page 167)
- cadential 6/4

### V<sup>7</sup> Chord
Dominant seventh.

### VII<sup>6</sup> Chord
When the bass carries scale degree \\(\hat2\\), however, VII<sup>6</sup> can stand in place of \\(V_3^4\\).

As a chord of dominant function, VII<sup>6</sup> in a minor key must include the leading tone (raise \\(\hat 7\\)).

### Role of 7 and 4

In whatever voice, 7 will regularly resolve to 8 in our tonal harmony when any chord of dominant function relates to I. The cadential treatment of 7 is exceptional.

In whatever voice, 4 will regularly resolve to 3 in V<sup>7</sup> and its inversions.

## Prolonging the Tonic
> [Extra Resources](http://openmusictheory.com/harmonicSyntax2.html)

The opening gambit:
- the analyzed soprano
- sketched bass
- introducing appropriate melodic figures
- complete by adding the tenor and alto voices

The counterpoint of the soprano-bass framework effectively *horizontalizes* the tonic chord: the chord unfolds in time. This important and fundamental process is called **prolongation**.

### Tonic-Dominant Prolongations
Various **elaborative chords** can stand on beat two of four-beat prolongation. Any diatonic, nondominant triad or sixth chord can perform this function, including diatonic V and VII in a minor key.

### Tonic-Subdominant Prolongations
Composers often confirm and emphasize the tonic triad at a music's close by following the V - I authentic cadence with the IV - I **plagal cadence**.

### Tonic Extension

Principal tones in both S and B occur in direct succession, a double statement of the chord is indicated: 5/3 - 6/3  or  6/3 - 5/3. This simple yet effective emphasis of I is called a **tonic extension**.

### Deceptive Resolution
Where the soprano melodic figure permits, for variety and contrast VI can be substituted for I following V or V<sup>7</sup> in a tonic-dominant prolongation. This V - VI progression is called a **deceptive resolution** since the listner expects to hear a confirming I after the V (or V<sup>7</sup>).

## Composing a Tonal Homophony
### Designing the bass
Major and minor tenth and sixth (and their compounds) should be predominate in the S-B framework. Fifth and octaves should be introduced with care because of their static quality.

### Opening Bass Gambits
When planning a tonic-dominant prolongation, ensure that both soprano and bass melodic figures will accommodate a chord of dominant function.

When planning a tonic-subdominant prolongation, ensure that both ... subdominant chord.

### Continuing the Bass to the Cadence
Figure the bass and provide a harmonic analysis.

### Adding the Tenor and Alto
The melodic-harmonic formations of tonal homophony are expressed most clearly by providing complete chordal sonority on every beat.
*Note that the leading tone is never doubled in a dominant-function chord.*

This objective of complete chordal sonority restricts the use of V<sup>7</sup>.


## The Cadence
### Role of 2 and 7
The resolution of 2 and 7 will in some cases be avoided, however, to gain a complete and stable chordal sonority for the final I: doubled root, third, and fifth. At the cadence, when 2 is carried by an inner voice, it can rise to 3; when 7 is carried by an inner voice, it can either rise to 3 or fall to 5. Because both 2 and 7 are consonant with the bass, when they are carried by inner voices in the authentic cadence they are freed of their normal tendencies. Here the V - I harmonic event takes precedence over the 2-1 and 7-8 melodic events. *The bass of the cadential V is regularly doubled*.

### V - V<sup>7</sup> Extension
In tonal harmony, the force of the authentic cadence expands to include the *third-from-last* beat. In four instances, 2-2-1, 7-9-8, 9-7-8, and 5-7-8, the soprano can be harmonized with the V - V<sup>7</sup> extension.

### Cadential 6/4
In two instances, 8-7-8 and 3-2-1, the cadential dominant can be decorated by a proceding 6/4 chord. This chord is called **cadential 6/4** (\\(\mathbf C_4^6\\)).

[More explanation](https://www.harmony.org.uk/book/voice_leading/cadential_6_4.htm) and [more](https://medium.com/@michaelkaulkin/name-that-chord-the-confusing-world-of-the-cadential-6-4-df58dd6a86cc).

### Cadential Pre-dominants
Frequently, the cadential dominant is introduced by a nondominant chord. These chords are termed **pre-dominants**. Six chords are available here as pre-dominants: II (only in major), II<sup>6</sup>, II<sub>5</sub><sup>6</sup>, IV, IV<sup>6</sup>, and VI.

In a minor key, three pre-dominant chords are available for harmonizing a soprano \#6 - \#7 - \#8 close: IV, II</sup>6</sup>81, and II; these chords carry the same qualities as in a major key.

### Extending the Cadential Predominant
The pre-dominant function can be enlarged to include two beats, and on occation, three beats. A pre-dominant chord can appear in double statement; two different pre-dominant chords can be paired; or a pre-dominant chord in double statement can be preceded or followed by a different pre-dominant chord.

Because they have three tones in common, IV<sup>6</sup> and II<sub>5</sub><sup>6</sup> often form a pre-dominant pair. They are often linked by a diatonic passing 6/4.


### Completing the Homophony

...

### Notations for Analysis
I, IV, etc: indicates chord root by scale degree

D: indicates deceptive resolution

\\(\underline{\phantom{This text will be invisible}}\\): indicates chordal extension

\\(\underbrace{\phantom{This text will be invisible}}\\): indicates tonic prolongation



# Chapter 13 - Suspensions & Syncopations '
<mark>' Note that this chapter is marked **important** to review.</mark>

> [Extra Resources](https://www.musical-u.com/learn/rhythm-training-101-study-syncopation/)

Rhythm's recurring beat is music's vital pulse, the primary and essential regulator of melodic movement and growth.

Meter bases its organizing principle on the fundamental pairing of downbeat and upbeat. Metric beats and agogic accents will normally agree; when they are in conflict, *syncopation* results.

We will construct this melodic dialogue by composing an elaborated upper voice against a cantus that will then be paraphrased.

## The Suspensions
One particular use of the agogic accent will introduce harmonic dissonance on a measure's downbeat. This important device is called a **suspension figure**. The consonant tone on beat one is rhythmically displaced to beat two, and its former downbeat position is taken over by the preceding measure's upbeat tone, tied across the bar as an agogic.

A suspension figure involves three tones: the consonant **preparation** on a measure's upbeat; the dissonant **suspension** on the following downbeat, tied over from the preparation; and the consonant **resolution** on the following upbeat, which will always enter by stepwise descent.

The 7 - 6 and 4 - 3 suspensions are available here.

The 6 - 5 and 5 - 6 **syncopation** figures closely resemble the suspension rhythmically in their use of half notes and ties; unlike the suspension, however, they do not introduce a harmonic dissonance.

### Decorating the Suspension
The suspension-resolution step of 7-6 and 4-3 suspensions can be elaborated by an echappee, and anticipation, or a skip-step.

## Rhythmic Patterns
Five are available:
- Spondaic: 𝅗𝅥 𝅗𝅥
- Trochaic: &#119134; . &#119135;
- Dactylic: 𝅗𝅥 𝅘𝅥 𝅘𝅥
- Anapestic: 𝅘𝅥 𝅘𝅥 𝅗𝅥
- Amphibrachic: 𝅘𝅥 𝅗𝅥 𝅘𝅥

## The Upper Voice
The three-note melodic figures: spondaic, trochaic. Four-note: dactylic, anapestic, amphibrachic.

Though it employs different rhythms and is set in duple meter, the upper voice exhibits the same design principles applied to the upper voice in a vocal duet (Chapter 11):
1. Its apogee should not be repeated or isolated by leaps.
2. Unidirectional motion should not exceed by the span of an octave.
3. Immediate repetition of melodic figures, rhythmic patterns, and suspensions should not exceed triple statement.
4. Downbeat-to-downbeat tritones should not occur.
5. Conjunct and disjunct motions should interchange frequently.

### Initial Measure
### Counterpoint
Treatment of perfect intervals is consistent with that in the vocal duet: unisons should not occur on a measure's downbeat; two fifths or two octave should not sound successive downbeats or on adjacent beats; nor should a fifth or an octave be approached in similar motion.

The four-note melodic figures can be expressed in spondaic and trochaic rhythms: *in both rhythms, the measure's upbeat will carry consonance*.
### Cadence
The music will cadence in a clausula vera decorated with a 7 - 6 suspension.

## Composing a Melodic Dialogue
### Opening Gambits
### Completing the Upper Voice
### Paraphrasing the Cantus
### Counterpoint
The individuality of the dialoguing voices will be maintained by
1. employing contrasting rhythmic patterns and melodic figures in the paraphrased cantus, and
2. by ensuring that the apogees do not coincide or share the same measure.

Passing or neighbor dissonance in the paraphrased cantus can be introduced on a measure's second or fourth quater. When the upper voice carries a suspension, the lower voice will respond with a three-note melodic figure in trochaic rhythm.

## Suspensions in Diminution


---
End of 270. In music 271, it will review chapter 12, then move to chapter 14.
