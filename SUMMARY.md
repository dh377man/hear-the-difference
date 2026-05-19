# Hear the Difference — Project Summary

A browser-based music discrimination game for elementary general music students (K–5), built as an AI-assisted prototype to explore (a) how music educators can evaluate ed-tech tools and (b) what's now possible when teachers can design software with AI assistance.

**Live URL:** https://dh377man.github.io/hear-the-difference/

---

## What the game does

Students hear two short musical patterns and decide whether they are the **same** or **different**. There are two modes:

- **Pitch Patterns** — short melodies on a pentatonic scale (C–D–E–G–A).
- **Rhythm Patterns** — short rhythms using clicks and rests at a steady tempo.

A round is five trials. After each answer, students can replay both patterns ("Hear it again") to compare what they heard, then move to the next trial.

## Five adaptive levels

The game advances a student a level when they answer 4 of 5 trials correctly, and drops them down a level after 2 misses in 3 recent trials. The difficulty curve is driven by three controlled variables:

| Level | Pattern length | Tempo | Pitch change difficulty | Rhythm flip difficulty |
|------:|:---|:---|:---|:---|
| 1 | 4 elements | ♩ = 80 | Last note only, ≥ 2 scale steps | Last beat only |
| 2 | 5 elements | ♩ = 80 | Last two notes, ≥ 2 steps | Last two beats |
| 3 | 6 elements | ♩ = 90 | Any position, ≥ 1 step | Any beat |
| 4 | 6 elements | ♩ = 100 | Any position | + eighth-note texture |
| 5 | 6 elements | ♩ = 110 | + octave leap available | Flip biased to weak off-beats |

The level structure controls both *what* makes a pattern harder and *where* in the pattern the difference occurs. This matters: changing the last note of a melody is much easier to detect than changing the first note, and a flip on a downbeat is far more obvious than a flip on a metrically weak position.

## Two age-band experiences

A first-launch question routes students to one of two skins, each with the same underlying game but age-appropriate presentation:

- **Junior (K–2):** animal avatars, a friendly owl mascot ("Echo") who gives encouraging feedback, a sticker book with collectible milestones, bright pastel theme.
- **Pro (3–5):** dark synthwave theme with neon accents, a heads-up display showing XP, combo counter, and score, full-screen "LEVEL UP" flash, "Achievements" instead of stickers, geometric sigils instead of animal avatars.

## Teacher tracking (class mode)

Teachers can set up a class with a 4-digit PIN and add students individually. Each student has their own profile (name, avatar, grade band, level progress, round history). A PIN-gated **dashboard** shows every student's level in each mode and their mastery progress.

Mastery is defined as **3 or more rounds at a given level scoring ≥ 80%**. The dashboard displays mastery as colored dots (one per level) so a teacher can see at a glance which students have mastered which content. Teachers can also launch a student's session directly from the dashboard.

## What's deliberately NOT in this version

These are not missing — they're scope decisions worth examining:

- **Uneven meters and longer durations.** Levels stop at simple meter and quarter/eighth-note resolution.
- **Cloud sync.** All data lives in the browser. No accounts, no cross-device sync. Each device is its own universe.
- **Backup / export.** No mechanism to save class data to a file. If browser data is cleared, the class is gone.
- **Microphone / singing input.** The task is pure same/different discrimination, not pitch matching or production.
- **Music notation.** Patterns are heard, not read.
- **Accessibility audit.** Reduced-motion and high-contrast are partially addressed; no formal WCAG conformance.
- **FERPA compliance documentation.** Data stays on the device, but no formal review has been performed.

## How students and teachers actually use it

- **One-device, classroom-station model** (recommended for the current build): a single iPad or Chromebook used as a listening center. Students rotate through, tap their name, play a round. Teacher reviews the dashboard during or after class.
- **One-device-per-teacher model**: each teacher uses their own laptop or tablet; their class roster lives in that browser. Different teachers' data never collides because the storage is per-browser-per-device.
- **One-device-per-student model**: works for play, but the class roster becomes fragmented across devices. Better suited for "Just Me" mode (single student per device).

## Questions worth evaluating

If you're using this as an evaluation exercise, here are the questions worth holding it up against:

1. **Does the difficulty curve actually correspond to ease of detection?** Try Level 1 vs Level 3 trials yourself — can you tell the difference between "easy by design" and "harder by design"?
2. **Where does the engagement layer help, and where might it distract?** Does Echo the owl help or get in the way? Do XP and combos motivate or trivialize the listening?
3. **Is the teacher tracking enough to be useful?** What's missing? What's there that you'd never use?
4. **What would have to change for this to serve 600 students reliably?** This is the most important question — see the limitations list above and consider what's a code problem, what's an infrastructure problem, and what's an organizational problem.
5. **What did AI-assisted development make easy here, and what did it not change?** The prototype was built in roughly six hours of conversation. The next 600 hours would still be required for a real product.

---

*Built collaboratively by Daniel Hellman (music educator and product owner) and Claude (Anthropic's AI assistant), May 2026. All design and pedagogical decisions are the educator's; all code generation was AI-assisted.*
