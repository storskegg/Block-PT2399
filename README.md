# Block-PT2399

A simple delay/echo design block based on the venerable PTC PT2399.

## Features

- Star Grounds: This board features a 2-star ground configuration
    1. All ground connections from and relating directly to the PT2399, and its
       dedicated power supply (`7805`) have their own trace to the negative lead
       on the `7805`'s `100uF` bypass capacitor.
    2. The above ground star, and all other ground connections (e.g. JFET
       impedance buffer) have their own traces back to `Sig_gnd`.
- Onboard regulation: The PT2399 is a particularly noisy beast, and must have
  its own power rail. As such, this board has its own 7805 regulator, and bypass
  capacitor (`100uF` located as close to the PT2399 as possible, while
  facilitating the star ground to the chip's supporting circuitry, and mfr's
  fabrication constraints.)

## Background

I've been working on a blues harp preamp for a buddy, and have been working on
the design in logical blocks that more or less get strung together. (It makes a
lot of sense when looking at valve gain stages, which are all basically the same
circuit repeated, maybe with different component values.) He mentioned wanting
delay or echo, and so I put this together. It is not a ground-up design, but
rather one that was inspired by the countless examples of using the PT2399
that you can find in the wild. (Sometimes it's better to stand on the shoulders
of giants.)

Anyhow, I decided to do up a board for ease of use in future projects.

