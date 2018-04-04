---
layout: post
title: Cellular Automaton in Logisim
published: true
tags:
  - Automaton
image: https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/TopModule.png
---

This is the second post of my series on Cellular Automatons. In this post, I'll show how I have designed and simulated an 8-bit Cellular Automaton using [Logisim](https://github.com/sderrien/logisim-evolution).

If you wonder what a Cellular Automaton is, go read my [first post](http://maker.itnerd.space/what-is-a-cellular-automaton/).

## Elementary block

We'll start by designing the smallest part of the Automaton: a combinational block that computes the next generation of a cell, given the cell (i1), its two neighbours (i0 and i2) and the rule (8bit). I'll call it the elementary block:

![](https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/aBlock-out.png) 

![](https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/aBlock-in.png)

Basically the 1 bit output is the Nth bit of Rule, where N is {i2,i1,i0}.

## Cellular Automaton

This module is the 8-bit Cellular Automaton module: it computes an 8-bit input and outputs the next generation 8 bits.

It is a combinational module made of 8 *elementary blocks*:

![](https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/Automaton8bit-inside.png)(https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/Automaton8bit-inside.png)

Notice the wriring of the elementary blocks, especially how the block B0 takes i7,i0 and i1 as input, and block B7 takes i6,i7 and i0 as input.

## Top module

In the top module we'll put the Cellular Automaton to use. Upon start, we feed it with the first line of 8 bits (seed), then at each clock cycle we'll compute the *next generation* and feed it back in into the Automaton. The current generation will be shown on a row of 8 LEDs.

![](https://github.com/adumont/CellularAutomaton/raw/master/Automaton-Logisim-8bits/assets/TopModule.png)

The top module is made of:

- one 8-bit Cellular Automaton,
- the output is feedback to the input via a register and wired to a row of 8 LEDs,
- the mux on the input feeds the first generation (Seed) upon startup or reset

## Simulation in Logisim

You can watch the simulation in Logisim on Youtube:

[![](http://img.youtube.com/vi/8XUDAzpuUUQ/0.jpg)](http://www.youtube.com/watch?v=8XUDAzpuUUQ)

## Files of the project

You can find the logisim project file on [Github](https://github.com/adumont/CellularAutomaton/tree/master/Automaton-Logisim-8bits).

In the next posts of this series I'll write about the Verilog version of my Automaton (which indeed was the first one I created).
If you found this post interesting, don't hesitate to share it and/or leave a comment.