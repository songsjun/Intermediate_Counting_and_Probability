# Chapter 13: Events With States

*"L'etat, c'est moi (I am the state)"* -- Louis XIV

## 13.1 Introduction

Many "events" are actually sequences of smaller events. For example, baseball's World Series produces a winner only after a series of up to 7 games, each of which has its own winner. The games themselves consist of individual innings, and an individual game might last an arbitrarily long time (if the game is tied after 9 innings and extra innings need to be played).

A state is a description of an intermediate stage of an event. For example, in the World Series, a state might be "the teams are tied at 2 games apiece." States allow us to break up complex events into more manageable simple events. It's a bit hard to precisely describe exactly what is a state, but the problems in this chapter should give you a pretty good idea of what states are and how we use them.

We will also look at some different types of problems that involve states. One such type of problem deals with random walks, which are processes in which a person or thing is moving around some universe (which might be a line, a plane, the surface of some polyhedron, etc.) and in which the direction of movement of any particular step of the walk is randomly chosen.

Another type of problem that we often use states to solve is problems about 2-player strategy games. We can think of intermediate positions of such a game as states, some of which are winning positions (from which the player that makes the next move can win) and the rest are losing positions. (We're only going to consider games that do not have ties, although games with ties can be studied using similar techniques.) Thinking of a game in terms of its intermediate states is often a useful way to analyze the game's strategies.

*"We are by nature observers, and thereby learners. That is our permanent state."* -- Ralph Waldo Emerson

## 13.4 Exercises

**13.4.2** Sean and Larry are playing a game on a blackboard. Sean starts by writing the number 1, and then in alternating turns (starting with Larry), each player multiplies the current number by any number from 2 through 9 (inclusive) and writes the new number on the board. The first player to write a number larger than 1000 wins. A sample game might be (each number is preceded by "S" or "L" to indicate who wrote it):
S1, L3, S12, L60, S420, L1260; Larry wins.

Which player should win and why? **Hints:** 249

**13.4.3** The game of Split is played with two piles of chips. On each turn, a player removes one pile and splits the remaining pile into two new piles in any manner he chooses. (For example, the game might start with piles of 9 and 12 chips; the first player could remove the 9-chip pile and split the other pile into piles of 8 and 4 chips.) A player loses if he or she is unable to move. What are the winning starting positions? **Hints:** 344

**13.4.4** If a game of Nim starts with 3 piles of 2, 4, and 6 chips, which player should win?

**13.4.5** Two players take turns drawing diagonals on a 100-sided regular polygon, subject to the condition that no two drawn diagonals can cross. A player who cannot move loses. Which player has a winning strategy? **Hints:** 5, 200

**13.4.6$\star$** Wythoff's game is similar to Nim: the game starts with two piles of chips, and on each move a player may either remove any number of chips from one pile, or an equal number of chips from both piles. The player who takes the last chip is the winner.
(a) Suppose that the game begins with piles of 5 and 6 chips. Which player should win and why?
(b)$\star$ Determine the winning and losing positions. **Hints:** 303, 16, 120

## 13.5 Summary

- A state is a description of an intermediate stage of an event. States allow us to break up complex events into more manageable simple events.
- For a problem with multiple states, it often helps to draw a diagram. Draw a box for each state and arrows for the transitions between states. Label probabilities or expected values as appropriate.
- Try to make your states as simple as possible. Often, in a problem involving states, identifying the simplest possible set of states is a major step towards solving the problem.
- It often helps to introduce variable(s) that store information about the intermediate state(s). This is especially true in events that can last for an arbitrarily long sequence of states.
- A particular type of state problem is a 2-player game. We try to identify winning positions and losing positions.
- When analyzing a game, it often helps to look at smaller versions of the game, and try to notice a pattern. Then we try to prove that our pattern works.

We also saw the following general problem-solving concepts:

> **Concept:** If it's easy to do, a quick check of your work in the middle of a problem can prevent errors from propagating through a long solution.

> **Concept:** Many problems have "nonconstructive" solutions, in which we can show the existence of some object (for example, a winning strategy for a 2-player game), but we can't exhibit precisely what that object is.

## Review Problems

**Problem 13.13:** Andrea flips a fair coin repeatedly, continuing until she either flips two heads in a row (the sequence HH) or flips tails followed by heads (the sequence TH). What is the probability that she will stop after flipping HH? (Source: HMMT)

**Problem 13.14:** A $3 \times 3 \times 3$ cube is composed of 27 small $1 \times 1 \times 1$ cubes, and little passageways allow for movement between adjacent cubes. (Cubes are adjacent if they share a face; cubes sharing only an edge are not adjacent.) A mouse is placed in a corner cube (the shaded cube in the picture at right), and a piece of cheese is placed in the center $1 \times 1 \times 1$ cube. Each minute, the mouse moves randomly to an adjacent cube. Find the expected number of minutes before the mouse reaches the cheese.

**Problem 13.15:** A bag contains two red beads and two green beads. You reach into the bag and pull out a bead, replacing it with a red bead regardless of the color you pulled out. What is the expected number of replacements needed so that all beads in the bag are red? (Source: AMC)

**Problem 13.16:** Recall that in a tennis game, if the players are tied at "deuce," then the game continues until one player has won two more points than the other player. Homer and Marge are again playing tennis and have reached deuce. Unfortunately for them, Bart is now the umpire of the game, and during any point, he will call "Let" with probability $\frac{1}{3}$, meaning that Homer and Marge will have to play that point again. If Homer has a $\frac{3}{5}$ probability of winning any given point in which Bart does not call "Let," then what is the expected number of points necessary (including points in which Bart calls "Let") before the game is completed?

**Problem 13.17:** A space alien is doing a random walk starting at 0 on the nonnegative number line. From 0 the alien must take one step to the right (to 1), but from any positive position on the line, the alien will move one step left or right with equal probability. What is the expected number of times that the alien will revisit 0 before the first time that he visits 5?

**Problem 13.18:** The figure at right is a map of part of a city: the small rectangles are city blocks and the lines are streets. Each morning a student walks from intersection $A$ to intersection $B$, always walking along streets shown, always going east or south. For variety, at each intersection where he has a choice, he chooses with equal probability whether to go east or south. Find the probability that, on any given morning, he walks through intersection $C$. (Source: AMC)

**Problem 13.19:** We play a game. The pot starts at $\$ 0$. On every turn, you flip a fair coin. If you flip heads, I add $\$ 100$ to the pot. If you flip tails, I take all of the money out of the pot, and you are assessed a "strike." You can stop the game before any flip and collect the contents of the pot, but if you get 3 strikes, the game is over and you win nothing. Find, with proof, the expected value of your winnings if you follow an optimal strategy. (Source: USAMTS)

**Problem 13.20:** A particle moves in the Cartesian plane from one lattice point to another according to the following rules:
1. From any lattice point $(a, b)$, the particle may move only to $(a+1, b)$, $(a, b+1)$, or $(a+1, b+1)$.
2. There are no right angle turns in the particle's path. That is, the sequence of points visited contains neither a subsequence of the form $(a, b),(a+1, b),(a+1, b+1)$ nor a subsequence of the form $(a, b)$, $(a, b+1),(a+1, b+1)$.

How many different paths can the particle take from $(0,0)$ to $(5,5)$? (Source: AIME)

## Challenge Problems

**Problem 13.21:** In a game similar to three card monte, the dealer places three cards on the table: the queen of spades and two red cards. The cards are placed in a row, with the queen in the center; the card configuration is thus RQR. The dealer proceeds with a series of moves. On each move, the dealer randomly switches the center card with one of the two edge cards (so the configuration after the first move is either RRQ or QRR). What is the probability that, after 2004 moves, the center card is the queen? (Source: HMMT)

**Problem 13.22:** A calculator has a display, which shows a nonnegative integer $N$, and a button, which replaces $N$ by a random integer chosen from the set $\{0,1, \ldots, N-1\}$, provided that $N>0$. Initially, the display holds the number $N=2003$. If the button is pressed repeatedly until $N=0$, what is the probability that the numbers $1,10,100$, and 1000 will all show up on the display at some point? (Source: HMMT) **Hints:** 116, 46

**Problem 13.23:** There are 6 peas in a glass, 4 floating on the top and 2 sitting on the bottom. At each five second interval, a random number of peas from 0 to 2 sink from the top to the bottom and a random number from 0 to 2 rise from the bottom to the top. (If there is only 1 pea left, it moves or stays put with equal probability.) What is the probability that all six peas are on the top before all six are on the bottom? (Source: Mandelbrot) **Hints:** 206

**Problem 13.24:** You and I each have $\$ 14$. I flip a fair coin repeatedly. If it comes up heads, I give you a dollar, but if it comes up tails, you give me a dollar. What is the expected number of flips until one of us runs out of money? (Source: Mandelbrot) **Hints:** 91, 317

**Problem 13.25$\star$** Here is the general analysis for Heaps with an arbitrary number of piles.

Let $A$ be the number of 2-chip piles, and let $B$ be the number of piles with either an even number (greater than 2) of chips or a single chip. The winning positions are those in which either $A$ or $B$ is odd.

Prove that it is correct, and describe the winning strategy. **Hints:** 1, 56

**Problem 13.26$\star$** Here is the general analysis for Nim with an arbitrary number of piles.

Represent the number of chips in each pile by a binary number (for example, 6 chips is the binary number 110). The losing positions are those in which there are an even number of 1's in each digit-position, counted across all the piles. (For example, piles of 7, 5, 3, and 1 chips is a losing position, because the binary representations 111, 101, 11, and 1 have an even number of 1's in the ones, twos, and fours places.)

Prove that it is correct, and describe the winning strategy. **Hints:** 245, 287
