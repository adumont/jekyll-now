---
layout: post
title: What is a Cellular Automaton?
published: false
tags:
  - Automaton
---

I first heard of the concept of Cellular Automaton while watching an Electrical and Computer Engineering&nbsp;course lecture by Bruce Land (available on Youtube)

[![](http://img.youtube.com/vi/sKhvMhTiuM4/0.jpg)](http://www.youtube.com/watch?v=sKhvMhTiuM4)

Some googling pointed me to this page on Wolfram with more details on the [Cellular Automata](http://mathworld.wolfram.com/ElementaryCellularAutomaton.html).

Basically, in a Cellular Automaton, the value of the next evolution of a cell depends on the value of the cell itself, and the value of its adjacent cells.

For example, let's represent a one-dimension population of 16 cells (a line of cells) and let's focus on cell 4:

[IMAGE 16 cells]

The next generation of cell 4 will depend on the value of cell 4 and the two adjacent cells (cells 4 and 5).

In the most simple form, each cell can have two values, 0 (dead) or 1 (alive). As we are looking at 3 cells, there are 2^3=8 posibilities of values for the triplet.

Let's imagine an arbitrary rule for our Cellular Automaton: "the generation N+1 of a cell will be 0 if the generation N of the cell is equal to the two adjacent cells". In other words, if the 3 cells have the same value (0 or 1), the next generation of the cell will die (be 0). Otherwise, if at least one of the two neighbour cells is different, it will survive (be 1).

We can see that this rules makes the rule 126:

&nbsp;