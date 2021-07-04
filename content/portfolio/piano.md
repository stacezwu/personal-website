+++
title = "Program Sound Synthesis on an Embedded Processor"
date = "2021-03-24"

[extra]
subtitle = "We built a small piano"
date = "March 2021"
abstract = "We build a music synthesis program using an embedded processor to generate the wave form in real time based on current keyboard inputs."
+++

# The Project
Using an embedded processor and a keyboard input device, we built a small electric piano. The piano can play multiple keys at once, plays correct wave-forms for the musical notes by generating overlapping sinus wave-forms in real time as keys are pressed.

It also modulates the amplitude of each note component, depending on how long the corresponding key has been pressed for, reducing the amplitude (loudness) over time to simulate a physical piano.

# My Contributions

I programmed the display logic and interrupts, which are responsible for decoding the inputs coming from the key-pad. The display shows which chord is pressed in real time.

My other major contribution was to propose and implement the use of the [CORDIC](https://en.wikipedia.org/wiki/CORDIC) algorithm to efficiently generate the sign wave-forms. On the resource-constrained micro controller, computing these is a non-trivial task.

To enable as many keys as possible to be pressed, but also retain a good quality audio, the CORDIC algorithm can adapt to take varying numbers of cycles depending on how many keys are pressed simultaneously. This allows for more keys to be pressed, while preserving the resolution of the wave-form when only one or two keys are active.

![](/image/portfolio/piano.png)


