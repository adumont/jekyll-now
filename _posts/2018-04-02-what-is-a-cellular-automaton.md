---
layout: post
title: What is a Cellular Automaton?
published: true
tags:
  - Automaton
---

This is the first post of a series I am writing about designing and running Cellular Automatons in an FPGA. I'll end up with several variants, from one lighting up LEDs to another one drawing on a VGA monitor. But first, what is a Cellular Automaton?
{: .present-before-paste}

I first heard of the concept of Cellular Automaton while watching an Electrical and Computer Engineering course lecture by Bruce Land (available on Youtube):
{: .present-before-paste}

[![](http://img.youtube.com/vi/yvqkg44_DQA/0.jpg)](http://www.youtube.com/watch?v=yvqkg44_DQA)
{: .present-before-paste}

Some googling pointed me to this page on Wolfram with more details on the [Cellular Automata](http://mathworld.wolfram.com/ElementaryCellularAutomaton.html).
{: .present-before-paste}

Basically, in a Cellular Automaton, the value of the next evolution of a cell depends on the value of the cell itself, and the value of its adjacent cells.
{: .present-before-paste}

For example, let's represent a one-dimension population of 16 cells (a line of cells) and let's focus on cell 4:
{: .present-before-paste}

![](/uploads/automaton-genn-cell4.png)
{: .present-before-paste}

The next generation of cell 4 will depend on the value of cell 4 and the two adjacent cells (cells 4 and 5):
{: .present-before-paste}

![](/uploads/automaton-genn1.png)
{: .present-before-paste}

In the most simple form, each cell can have two values, 0 (dead) or 1 (alive). As we are looking at 3 cells, there are 2^3=8 posibilities of values for the triplet.
{: .present-before-paste}

Let's imagine an arbitrary rule for our Cellular Automaton: "*the generation N+1 of a cell will be 0 if the generation N of the cell is equal to the two adjacent cells*". In other words, if the 3 cells have the same value (0 or 1), the next generation of the cell will die (be 0). Otherwise, if at least one of the two neighbour cells is different, it will survive (be 1).
{: .present-before-paste}

We can see that this rules makes the [rule 126](http://mathworld.wolfram.com/Rule126.html):
{: .present-before-paste}

![](/uploads/automaton-rule126.png)
{: .present-before-paste}

If we start with a black (1) cell at the center of the first line (generation 0), and we compute each succesive line with the rule above, we will obtain this drawing:
{: .present-before-paste}

![](/uploads/elementarycarule126-1200.gif)
{: .present-before-paste}

We have seen Rule 126. As we can see, a rule is actually a 8 bit value! So there are 256 different rules for a One Dimension Cellular Automaton.
{: .present-before-paste}

Here are the results obtains for other rules:
{: .present-before-paste}

![](/uploads/elementaryca-850.gif)
{: .present-before-paste}

In future articles, we'll see how to create a Cellular Automaton in Verilog and run it in an FPGA to output generations on leds, and on a VGA display.
{: .present-before-paste}