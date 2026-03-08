# Chapter 10: Recursion

*To understand recursion, you must first understand recursion. - Anonymous*

## 10.1 Introduction

The Fibonacci numbers from the last chapter are an example of recursion. Whenever we have a sequence of numbers in which the next number in the sequence is derived from previous numbers, we have a recursion. For example, with the Fibonacci numbers, we have the recurrence relation
$$F_{n}=F_{n-1}+F_{n-2}, \quad F_{0}=0, F_{1}=1 .$$

Each Fibonacci number (after the first two) depends on the two previous Fibonacci numbers.
In this chapter, we'll look at several problems in which we can use recursion as a solution method, and discuss more generally the types of problems for which recursion may be useful. In brief, whenever we have a problem in which we have to compute some quantity that can be expressed in terms of a positive integer $n$, and we can replace that computation with a computation of the same quantity but for smaller values (such as $n-1, n-2$, etc.), we may be able to use recursion to solve the problem. This can be a little confusing as an abstract concept, but should become more clear as we work through several examples.

Later in the chapter, we will explore a special sequence of numbers called the Catalan numbers. As we will see, these numbers pop up in a surprising number of different counting situations. The eminent combinatorist Richard Stanley, in his book Enumerative Combinatorics: Volume 2 and on its accompanying website, lists (as of this writing) 149 different mathematical objects that are counted by the Catalan numbers. The items on Stanley's list come from many different branches of mathematics, and several of these items have deep mathematical significance.

We will examine several problems whose answers involve the Catalan numbers. We will use our results from these problems to determine both the recursive definition of the Catalan numbers and also a fairly simple closed-form formula for the numbers.

## 10.2 Examples of Recursions

Problems

**Problem 10.1:** The diagram below shows 3 pegs and 8 rings of different sizes. All of the rings start on the left peg. The goal is to move all of the rings to the right peg. On each move, we can remove the top ring on any peg and place it on any other peg, provided that we do not place a ring on top of a smaller ring.
(a) Try the problem for 1, 2, or 3 rings. What is the minimum number of moves necessary to move all of the rings to the right peg?
(b) What is the minimum number of moves necessary in the full 8-ring version of the game?
(c) Suppose there were $n$ rings, where $n$ is an arbitrary positive integer. What is the minimum number of moves necessary?

**Problem 10.2:** I work for a valet parking company. Each of our customers drives either a Cadillac, a Continental, or a Porsche. My boss told me I have to reserve spaces in our parking lot and mark them as being for a Cadillac, a Continental, or a Porsche. Cadillacs and Continentals each take 2 spaces while Porsches only require 1.
(a) Suppose that our parking lot has 3 spaces. In how many ways can I allocate the spaces?
(b) What if the lot has 12 spaces?
(c) $\star$ What if the lot has 500 spaces?

**Problem 10.3:** Find the number of 10-digit ternary sequences (that is, sequences with digits 0, 1, or 2) such that the sequence does not contain two consecutive zeros.

**Problem 10.4:** 6 sprinters are in the 100-meter dash. Ties are allowed in the final standings, so that, for example, one possible order of finish is:

Runner \#6 wins; \#2 and \#5 tie for 2nd; and \#1, \#3 and \#4 all tie for last.
How many different finishing orders are possible?

The Fibonacci numbers are just one example of recursion. We'll look at some more recursion problems in this section. The common theme is that we break down each problem into smaller versions of the same problem.

> **Concept:** Whenever you can take a problem and express its solution in terms of smaller versions of the same problem, that problem is a good candidate for recursion.

**Problem 10.1:** The diagram below shows 3 pegs and 8 rings of different sizes. All of the rings start on the left peg. The goal is to move all of the rings to the right peg. On each move, we can remove the top ring on any peg and place it on any other peg, provided that we do not place a ring on top of a smaller ring.
(a) What is the minimum number of moves necessary to win the game?
(b) Suppose there were $n$ rings, where $n$ is an arbitrary positive integer. What is the minimum number of moves necessary?

*Solution for Problem 10.1:*
(a) Since we don't really know what the best strategy is, let's look at some smaller examples.

> **Concept:** Experiment with smaller examples in order to get a feel for a hard problem.

If there's only 1 ring, then we only need 1 move: we just move it to the right peg and we win!
If there are 2 rings, it's still pretty easy to win. We move the smaller ring to the middle peg, then move the larger ring to the right peg, and finally move the smaller ring to the right peg. We need 3 moves to win, and it's pretty clear that there's no way to win in fewer moves.

Experiment with 3 rings before reading further. How many moves are necessary?
It turns out that the best way to win is via the following sequence of moves:
- Start position
- Move smallest ring to right peg.
- Move middle ring to center peg.
- Move smallest ring to center peg.
- Move largest ring to right peg.
- Move smallest ring to left peg.
- Move middle ring to right peg.
- Move smallest ring to right peg.

So we can win in 7 moves. But how can we be sure that this is the least possible number of moves, and that we're not overlooking a better strategy that might allow us to win in 6 or fewer moves?

We can break up the necessary steps for solving the 3-ring version as follows:
- Move the smaller two rings to the middle peg.
- Move the largest ring to the right peg.
- Move the smaller two rings to the right peg.

Note that this must be the optimal strategy. We cannot move the largest ring until the smaller 2 rings have been moved off of it. We can't put the largest ring on the right peg unless it's empty. So there's no other possible course of action except for that which is listed above.

We know that moving the two smaller rings to the middle peg takes 3 moves, since that's just the 2-ring problem. Then our 4th move is moving the largest ring. Finally, we know that it takes 3 more moves to move the two smaller rings onto the right peg. So 7 moves is the best we can do.

We have also gained the necessary insight to solve the 8-ring case. The general strategy is
- Move the smaller 7 rings to the middle peg.
- Move the largest ring to the right peg.
- Move the smaller 7 rings to the right peg.

Therefore, we can say that
$$(\# \text { of moves to win with } 8 \text { rings })=2(\# \text { of moves to win with } 7 \text { rings })+1 .$$

If we let $h_{n}$ denote the number of moves necessary to solve the problem with $n$ rings, then we have $h_{n}=2 h_{n-1}+1$. This type of formula, in which the elements of a sequence are defined in terms of previous element(s) of the sequence, is called a recurrence relation or simply a recurrence.

> **Extra!** This problem is known as the Towers of Hanoi and was invented by the French mathematician Edouard Lucas in 1883. An animated version of the Towers of Hanoi problem (and its solution) was prominently featured on the website for the 2007 International Mathematical Olympiad, which was held in Hanoi, Vietnam.

We can now work our way up to $h_{8}$ by starting at $h_{1}=1$ and using the above recurrence relation:
$$\begin{array}{l}
h_{2}=2 h_{1}+1=2(1)+1=3 \\
h_{3}=2 h_{2}+1=2(3)+1=7 \\
h_{4}=2 h_{3}+1=2(7)+1=15 \\
h_{5}=2 h_{4}+1=2(15)+1=31 \\
h_{6}=2 h_{5}+1=2(31)+1=63 \\
h_{7}=2 h_{6}+1=2(63)+1=127 \\
h_{8}=2 h_{7}+1=2(127)+1=255
\end{array}$$

So we need 255 moves to win the game.
(b) Hopefully, the pattern of the above numbers is pretty clear. Each number is 1 less than a power of 2, so it looks like $h_{n}=2^{n}-1$. Observing a pattern is not a proof, though. We need to prove that this works. We do so by induction, checking that it works for the initial condition $n=1$ and that it satisfies the recurrence relation.

First, we see that $h_{1}=2^{1}-1=2-1=1$. Now we show that our formula for $h_{n}$ satisfies the recurrence relation, by induction. Assume that the formula works for $h_{n-1}$; that is, assume that $h_{n-1}=2^{n-1}-1$. Then by our recurrence relation:
$$h_{n}=2 h_{n-1}+1=2\left(2^{n-1}-1\right)+1=2^{n}-2+1=2^{n}-1 .$$

So, by induction, $h_{n}=2^{n}-1$ for all positive integers $n$.

A little later, we'll see how you might have come up with the formula if you didn't see a pattern. In fact, we see a bit of this approach in the next problem.

**Problem 10.2:** I work for a valet parking company. Each of our customers drives either a Cadillac, a Continental, or a Porsche. My boss told me I have to reserve spaces in our parking lot and mark them as being for a Cadillac, a Continental, or a Porsche. Cadillacs and Continentals each take 2 spaces while Porsches only require 1.
(a) The lot has 12 spaces. In how many ways can I allocate the spaces?
(b) What if the lot has 500 spaces?

*Solution for Problem 10.2:* We see that this problem easily scales, meaning that there's nothing particularly special about the number "12" in the problem: it would be essentially the same problem regardless of the number. We also see that, after we allocate the first space(s) for the first car, we have the same problem (with a smaller number of spots) as we started with. This makes the problem a good candidate for a recursive solution.
(a) Let $p_{n}$ denote the number of ways to allocate a parking lot with $n$ spots. If we allocate the first spot to a Porsche, then we can allocate the remaining $n-1$ spots in $p_{n-1}$ ways. If we allocate the first two spots to a Cadillac, then we can allocate the remaining $n-2$ spots in $p_{n-2}$ ways. Similarly, if we allocate the first two spots to a Continental, then we can allocate the remaining $n-2$ spots in $p_{n-2}$ ways. Therefore, our recurrence relation is
$$p_{n}=p_{n-1}+2 p_{n-2} .$$

We start with $p_{1}=1$ (since if there's only one spot, we have only one choice, which is to allocate it to a Porsche) and $p_{2}=3$ (since our choices are a Cadillac, a Continental, or two Porsches). Then we can use the recurrence relation to work our way up to $p_{12}$:
$$\begin{array}{l}
p_{3}=p_{2}+2 p_{1}=3+2(1)=5 \\
p_{4}=p_{3}+2 p_{2}=5+2(3)=11 \\
p_{5}=p_{4}+2 p_{3}=11+2(5)=21 \\
p_{6}=p_{5}+2 p_{4}=21+2(11)=43 \\
p_{7}=p_{6}+2 p_{5}=43+2(21)=85 \\
p_{8}=p_{7}+2 p_{6}=85+2(43)=171 \\
p_{9}=p_{8}+2 p_{7}=171+2(85)=341 \\
p_{10}=p_{9}+2 p_{8}=341+2(171)=683 \\
p_{11}=p_{10}+2 p_{9}=683+2(341)=1365 \\
p_{12}=p_{11}+2 p_{10}=1365+2(683)=2731
\end{array}$$

So there are 2731 ways in which we can allocate the 12 spaces.
(b) We don't want to keep listing out terms all the way to $p_{500}$. Instead, we'd like a nice formula that we can simply plug $n=500$ into and get the answer. But the pattern, if there even is a pattern, is not so obvious here.

One pattern that you might notice is that each number in the above list is almost twice the number immediately before it:
$$11=2(5)+1,21=2(11)-1,43=2(21)+1,85=2(43)-1, \ldots$$

But it's not at all clear how to turn this into a formula.
However, the "almost-doubling" of the numbers makes us think about exponential growth, so we can try the same tactic that we used to find the Binet formula for the Fibonacci numbers. We look for solutions to the recurrence of the form $c^{n}$ for some constant $c$. If we substitute this into the recurrence, we get
$$c^{n}=c^{n-1}+2 c^{n-2}$$

We can divide through by $c^{n-2}$ and we're left with $c^{2}=c+2$, which gives $c^{2}-c-2=0$. This factors as $(c-2)(c+1)=0$, so we see that $c=2$ or $c=-1$.

Then, just as we did when finding the Binet formula, we have that $p_{n}=\lambda_{1} 2^{n}+\lambda_{2}(-1)^{n}$, where $\lambda_{1}$ and $\lambda_{2}$ are unknown constants, and we use the initial conditions $p_{1}=1$ and $p_{2}=3$ to solve for the constants. This gives us a system of linear equations:
$$\begin{array}{l}
p_{1}=1=2 \lambda_{1}-\lambda_{2} \\
p_{2}=3=4 \lambda_{1}+\lambda_{2}
\end{array}$$

Adding them together gives $4=6 \lambda_{1}$, so $\lambda_{1}=\frac{2}{3}$, which then gives us $\lambda_{2}=\frac{1}{3}$. Therefore we have
$$p_{n}=\frac{2}{3} 2^{n}+\frac{1}{3}(-1)^{n}$$

We can now quickly compute $p_{n}$ for any value of $n$; in particular
$$p_{500}=\frac{2}{3} 2^{500}+\frac{1}{3}=\frac{2^{501}+1}{3} .$$

At this point, you may have a pretty good idea how to approach finding a closed-form formula for many recursions. We "guess" that the formula will somehow involve $c^{n}$, and then solve for $c$. We'll come back to this idea in the next section.

**Problem 10.3:** Find the number of 10-digit ternary sequences (that is, sequences with digits 0, 1, or 2) such that the sequence does not contain two consecutive zeros.

*Solution for Problem 10.3:* We can do casework based on the first digit of the sequence. If the first digit is a 0, then the next digit must be a 1 or a 2, and the remaining $n-2$ digits must not have two consecutive zeros. If the first digit is a 1 or a 2, then the remaining $n-1$ digits must not have two consecutive zeros.

So if $a_{n}$ is the number of $n$-digit ternary sequences with no two consecutive zeros, then $a_{n}$ satisfies the recurrence relation
$$a_{n}=2 a_{n-1}+2 a_{n-2}$$

This looks a lot like the Fibonacci sequence, except that each term is double the sum of the previous two terms.

Noting that $a_{1}=3$ and $a_{2}=8$ (any two-digit sequence except 00 is allowed), we can generate the sequence:
$$3,8,22,60,164,448,1224,3344,9136,24960, \ldots$$

So the answer is 24960. $\square$

**Problem 10.4:** 6 sprinters are in the 100-meter dash. Ties are allowed in the final standings, so that, for example, one possible order of finish is:

Runner \#6 wins; \#2 and \#5 tie for 2nd; and \#1, \#3 and \#4 all tie for last.
How many different finishing orders are possible?

*Solution for Problem 10.4:* What makes this problem difficult is that any number of people could tie for any position, including all 6 of them tying for first place. So trying to attack this problem using a direct method like casework seems very difficult, as there are a large number of cases to consider: we could have all 6 tied, or 5 could be tied with the other alone (ahead or behind), or it might go 4-1-1 (or 1-4-1 or 1-1-4), or 3-2-1 or 4-2 or 3-3 or 3-1-1-1 or.... We could try to list all of the possible cases and count the number of possibilities for each, but it would be long and messy, and it'd be easy to overlook a case and get the wrong answer.

So instead, let's try to look at some smaller version of the same problem to try to get a handle for what's going on. The easiest way to simplify the problem is to reduce the number of runners.

If there's only 1 runner, then obviously there's only 1 possible order of finish.
If there are two runners $A$ and $B$, then either $A$ could beat $B$, or $B$ could beat $A$, or they could tie. So there are 3 possible orders.

Let's go to 3 runners. Already it's starting to get complicated. If none of them tie, then there are 3! orders of finish. Or they could all finish in a 3-way tie. If 2 of them tie, then there are $\binom{3}{2}=3$ choices for which two tie, and then 2 choices for the order between the two tied runners and the 3rd non-tied runner, for a total of 6 possible orders when 2 of them tie. So there's a total of $6+1+6=13$ possible finishing orders for the 3-runner race.

Going to 4 runners leads to even nastier casework, and no clear pattern emerged from the numbers that we've gotten so far: $1,3,13$.

So let's look at the problem another way.

> **Concept:** If a solution method doesn't seem to be getting you anywhere, don't be afraid to start over and try a completely different approach.

We can look at the runner(s) that come in first. If $k$ runners tie for first, then there are $\binom{6}{k}$ ways to choose those runners. Then, we have $6-k$ runners left to arrange. This suggests a recursive approach, since the "$6-k$ runners left to arrange" part is a smaller version of the same problem.

So let $a_{n}$ be the number of possible orders of finish for an $n$-runner race. As above, we can break up the problem into cases based on how many runners tie for first. If $k$ runners tie for first, then we have $\binom{n}{k}$ ways to choose them, and $a_{n-k}$ ways that the remaining $n-k$ runners can finish.
This gives us our recursion:
$$a_{n}=\sum_{k=1}^{n}\binom{n}{k} a_{n-k}$$

Note that $a_{n}$ depends on all of the previous terms of the sequence of $a$'s.
Now we just crunch the numbers, noting that $a_{0}=1$: if there are no runners to arrange, then there are no choices to make.
$$\begin{array}{l}
a_{1}=a_{0}=1 \\
a_{2}=2 a_{1}+a_{0}=1+2=3 \\
a_{3}=3 a_{2}+3 a_{1}+a_{0}=9+3+1=13 \\
a_{4}=4 a_{3}+6 a_{2}+4 a_{1}+a_{0}=52+18+4+1=75 \\
a_{5}=5 a_{4}+10 a_{3}+10 a_{2}+5 a_{1}+a_{0}=375+130+30+5+1=541
\end{array}$$

Finally, we get our answer:
$$\begin{aligned}
a_{6} & =6 a_{5}+15 a_{4}+20 a_{3}+15 a_{2}+6 a_{1}+a_{0} \\
& =3246+1125+260+45+6+1 \\
& =4683
\end{aligned}$$

The numbers that we found:
$$1,3,13,75,541,4683, \ldots,$$
don't seem to fit any nice pattern, so there doesn't seem to be any obvious closed-form formula. $\square$

### Exercises

**10.2.1** I have a 10-foot flagpole. I have 3 different types of 2-foot flags and 2 different types of 1-foot flags. I have billions of each of the types of flags. Find the number of ways I can arrange flags to exactly fill the 10-foot flagpole (where the orders of the flags matter, and while flags of the same type are indistinguishable, flags of different types are distinguishable).

**10.2.2** Let $a_{1}, a_{2}, \ldots$ be a sequence with the following properties:
(i) $a_{1}=1$, and
(ii) $a_{2 n}=n\left(a_{n}\right)$ for any positive integer $n$.

What is the value of $a_{2^{100}}$?

**10.2.3** How many 6-digit base-4 numbers have the property that they contain at least one 1 and that the first 1 is to the left of the first 0 (or there is no 0)?

**10.2.4** Let $a_{1}=p$ and $a_{2}=q$, where $p$ and $q$ are positive integers, and let $a_{n}=a_{n-1} a_{n-2}$ for all $n \geq 3$. Find a formula for $a_{n}$ in terms of $n, p$, and $q$. **Hints:** 197

**10.2.5** Call a set of integers spacy if it contains no more than one out of any three consecutive integers. How many subsets of $\{1,2,3, \ldots, 12\}$ are spacy? (Source: AMC) **Hints:** 231

**10.2.6** $\star$ Find the number of 10-digit binary sequences that have exactly one pair of consecutive 0's. **Hints:** 59

## 10.3 Linear Recurrences

Problems

**Problem 10.5:** We wish to find a closed-form formula for the recurrence where $a_{1}=1, a_{2}=2$, and $a_{n}=a_{n-1}+6 a_{n-2}$ for all $n>2$.
(a) Ignore the initial conditions for $a_{1}$ and $a_{2}$. Let $a_{n}=c^{n}$ for some unknown constant $c$. Plug this into the recurrence relation and solve for $c$.
(b) You should have found in part (a) that there is more than one value of $c$ that works. How can we combine the different values of $c$ into a common solution?
(c) In (a) and (b), you did not use the conditions $a_{1}=1$ and $a_{2}=2$. Use these conditions to finish the problem.

**Problem 10.6:** Find a closed-form formula for the recurrence $a_{n}=4 a_{n-1}-4 a_{n-2}$ for all $n>2$, with initial conditions $a_{1}=1$ and $a_{2}=3$.

In Problem 10.2, we saw a small piece of the general theory for finding formulas for recurrences. In this section, we'll explore this theory in a bit more detail, and introduce some terminology.

> **Important:** It is not necessary to memorize this terminology. It is more important to understand the underlying concepts.

We're not going to try to cover completely the general theory of recurrence relations -- doing so would require more algebra than we wish to get into in this book. Instead, we'll focus on a couple of key examples.

**Problem 10.5:** Find a closed formula for the recurrence where $a_{1}=1, a_{2}=2$, and $a_{n}=a_{n-1}+6 a_{n-2}$ for all $n>2$.

*Solution for Problem 10.5:* As we did when we found the closed-form formula for the recurrence in Problem 10.2, we start this problem by trying a solution of the form $c^{n}$ for some unknown constant $c$. We plug this into the recurrence to get
$$c^{n}=c^{n-1}+6 c^{n-2} .$$

Dividing by $c^{n-2}$ and bringing all the terms to one side gives
$$c^{2}-c-6=0 .$$

Factoring gives us $(c-3)(c+2)=0$, so the roots are $c=3$ and $c=-2$.
Therefore, we know that for any constants $\lambda_{1}$ and $\lambda_{2}$,
$$a_{n}=\lambda_{1} 3^{n}+\lambda_{2}(-2)^{n}$$
satisfies the recurrence. To find a solution to the recurrence that also satisfies the initial conditions $a_{1}=1$ and $a_{2}=2$, we substitute $n=1$ and $n=2$ into the above equation to get the system of linear equations:
$$\begin{array}{l}
1=3 \lambda_{1}-2 \lambda_{2}, \\
2=9 \lambda_{1}+4 \lambda_{2} .
\end{array}$$

Multiplying the top equation by 2 and adding gives $4=15 \lambda_{1}$, so $\lambda_{1}=\frac{4}{15}$, and plugging this back in gives $\lambda_{2}=-\frac{1}{10}$.

Therefore our solution is
$$a_{n}=\frac{4}{15}(3)^{n}-\frac{1}{10}(-2)^{n} .$$

As a quick check, we can compute $a_{3}=a_{2}+6 a_{1}=8$, and check that
$$\frac{4}{15}(3)^{3}-\frac{1}{10}(-2)^{3}=\frac{4}{15}(27)-\frac{1}{10}(-8)=\frac{36}{5}+\frac{4}{5}=\frac{40}{5}=8 .$$

We can use this same method as a general procedure to solve recurrences of the form $a_{n}=p a_{n-1}+q a_{n-2}$, where $p$ and $q$ are constants. Such recurrences are called linear recurrences, since each term of the recurrence is an element of the sequence (such as $a_{n}$ or $a_{n-1}$) multiplied by a constant.

We first look for solutions that are exponentials of the form $c^{n}$, which we can plug into the recurrence to get
$$c^{n}=p c^{n-1}+q c^{n-2}$$

We divide by $c^{n-2}$ and move all terms to one side to get
$$c^{2}-p c-q=0$$

This is called the characteristic equation of the recurrence. We solve this to get roots $c_{1}$ and $c_{2}$. Then, if $c_{1} \neq c_{2}$, we have that
$$a_{n}=\lambda_{1} c_{1}^{n}+\lambda_{2} c_{2}^{n}$$
for some constants $\lambda_{1}$ and $\lambda_{2}$. This is called the general solution of the recurrence. Finally, we use the initial conditions on $a_{1}$ and $a_{2}$ to solve for the $\lambda$'s.

The next problem explores what we do if the roots of the characteristic equation are equal; that is, if $c_{1}=c_{2}$ in the above discussion.

**Problem 10.6:** Find a closed-form formula for the recursion $a_{n}=4 a_{n-1}-4 a_{n-2}$ for all $n>2$, with initial conditions $a_{1}=1$ and $a_{2}=3$.

*Solution for Problem 10.6:* It's a linear recurrence relation, so we start by forming the characteristic polynomial:
$$c^{2}-4 c+4=0$$

This factors as $(c-2)^{2}=0$, so we have a double root at $c=2$. What do we do now?

> **Bogus Solution:** If we try to simply set
> $$a_{n}=\lambda 2^{n},$$
> we plug in $a_{1}=1$ and see that $\lambda=\frac{1}{2}$, so it looks like $a_{n}=\frac{1}{2}\left(2^{n}\right)=2^{n-1}$.

But this doesn't work, since $a_{2}=3 \neq 2^{1}$.
Let's compute a few terms of the sequence, to see if there's an easily-observed pattern:
$$\begin{aligned}
a_{1} & =1 \\
a_{2} & =3 \\
a_{3} & =4(3-1)=8 \\
a_{4} & =4(8-3)=20 \\
a_{5} & =4(20-8)=48 \\
a_{6} & =4(48-20)=112 \\
& \vdots
\end{aligned}$$

We suspect that $2^{n}$ might somehow be involved, so let's divide each term by $2^{n}$:
$$\frac{a_{1}}{2}=\frac{1}{2}, \quad \frac{a_{2}}{4}=\frac{3}{4}, \quad \frac{a_{3}}{8}=1, \quad \frac{a_{4}}{16}=\frac{5}{4}, \quad \frac{a_{5}}{32}=\frac{3}{2}, \quad \frac{a_{6}}{64}=\frac{7}{4}, \quad \ldots$$

It appears that every time $n$ increases by $1, a_{n} / 2^{n}$ increases by $\frac{1}{4}$. In particular, we can conjecture that
$$\frac{a_{n}}{2^{n}}=\frac{n+1}{4} \quad \Rightarrow \quad a_{n}=\frac{n+1}{4}\left(2^{n}\right) .$$

We see that there is an $n 2^{n}$ term in our solution. In fact, this is what happens in general. If we have a double root of our characteristic equation, then we will get a term with a factor of $n$ in the general solution. In this problem, our general solution is
$$a_{n}=\lambda_{1} 2^{n}+\lambda_{2} n 2^{n} .$$

Now we can plug in our initial values and get a system of linear equations:
$$\begin{array}{l}
1=2 \lambda_{1}+2 \lambda_{2} \\
3=4 \lambda_{1}+8 \lambda_{2}
\end{array}$$

Solving this system gives $\lambda_{1}=\frac{1}{4}$ and $\lambda_{2}=\frac{1}{4}$, so our solution is
$$a_{n}=\frac{1}{4} 2^{n}+\frac{1}{4} n 2^{n}=\frac{1}{4}(1+n) 2^{n} .$$

Here is the general statement of what we observed in the previous problem:

> **Important:** If $c$ is a double root of the characteristic equation, then the general solution will have terms of the form
> $$\lambda_{1} c^{n}+\lambda_{2} n c^{n} .$$

Of course, we have not proved that this always works. It is not terribly difficult to algebraically show that this is always the general solution of a recurrence with a double root, but we will leave the details of the proof as an Exercise.

### Exercises

**10.3.1** Find a formula for $a_{n}$ where $a_{n}=-2 a_{n-1}+15 a_{n-2}$, with initial conditions $a_{0}=0$ and $a_{1}=1$.

**10.3.2** Find a formula for $a_{n}$ where $a_{n}=4 a_{n-1}-3 a_{n-2}$, with initial conditions $a_{0}=1$ and $a_{1}=1$.

**10.3.3** Find a formula for $a_{n}$ where $a_{n}=6 a_{n-1}-9 a_{n-2}$, with initial conditions $a_{0}=1$ and $a_{1}=4$.

**10.3.4** Prove that, if $a_{n}=p a_{n-1}+q a_{n-2}$ is a recurrence such that the characteristic equation has a double root $c$, then
$$a_{n}=\lambda_{1} c^{n}+\lambda_{2} n c^{n}$$
is a solution to the recurrence. **Hints:** 4

**10.3.5** Find a formula for $a_{n}$ where $a_{n}=2 a_{n-1}-5 a_{n-2}$, with initial conditions $a_{1}=2$ and $a_{2}=1$.

**10.3.6** $\star$ Find a closed-form formula for the recurrence $a_{n}=2 a_{n-1}+a_{n-2}-2 a_{n-3}$ with initial conditions $a_{0}=0, a_{1}=1$, and $a_{2}=3$. **Hints:** 165

## 10.4 A Hard Recursion Problem

Problems

**Problem 10.7:** I have 2048 letters numbered 1 to 2048. I have to address every single one. Originally they're stacked in order with \#1 on top. To make the task a bit less mind-numbing, I address every other one, starting with \#1. When I address a letter, I put it in my outbox. The ones I skip I stack as I skip them (so \#2 is on the bottom of the stack after my first pass). After I finish my first pass, I have 1024 letters which are not addressed; \#2048 is on top, \#2 is on the bottom. I then repeat my procedure over and over until there's only one letter left. What number is that letter? (Source: AIME)

In the real world, we're not usually just given a simple recurrence relation and told to solve it. Recursion is usually hidden within a problem, and the recursion may not be so easy to see or write down. Let's do an example of a problem in which a recursion is clearly present, but precisely describing that recursion is somewhat difficult.

**Problem 10.7:** I have 2048 letters numbered 1 to 2048. I have to address every single one. Originally they're stacked in order with \#1 on top. To make the task a bit less mind-numbing, I address every other one, starting with \#1. When I address a letter, I put it in my outbox. The ones I skip I stack as I skip them (so \#2 is on the bottom of the stack after my first pass). After I finish my first pass, I have 1024 letters which are not addressed; \#2048 is on top, \#2 is on the bottom. I then repeat my procedure over and over until there's only one letter left. What number is that letter? (Source: AIME)

*Solution for Problem 10.7:* We could try to brute-force it, writing out the stack at each step. However that sounds like a very long process, and the potential for error is huge. So instead, as we often do, we can try to get a feel for the problem by playing with smaller cases. Since the number of letters gets halved on every iteration of the procedure, it makes sense to just look at stacks with sizes that are powers of 2.

If we start with 1 letter, then obviously \#1 is the last letter remaining. Let's denote by $a_{n}$ the number of the last letter remaining if we start with a stack of $2^{n}$ letters numbered from \#1 to \#$2^n$. So we've established that $a_{0}=1$, and we're trying to find $a_{11}$.

If we start with 2 letters, then I address \#1, and \#2 is left over. So $a_{1}=2$.
If we start with 4 letters, on the first pass I address \#1 and \#3 and am left with a stack with \#4 on top and \#2 on the bottom. On the second pass, I address \#4, and \#2 is the last letter remaining. So $a_{2}=2$.

For a stack with 8 letters, I had better start using a chart. In each stack, I cross off the letters that I sign, and then the next stack is the uncrossed letters, in reverse order. We see from the chart that letter \#6 is the last letter remaining, so $a_{3}=6$.

I can try to keep going to 16 letters, but now's a good time to start looking for a shortcut. Let's just list the stack after doing the first pass for 16 letters. It will be a stack with just the even-numbered letters remaining, with \#16 at the top and \#2 at the bottom.

I don't need to keep going, because I can take advantage of recursion! I know that in the 8-letter problem, the $6^{\text{th}}$ letter from the top is the last one remaining. So I know that in my stack, the $6^{\text{th}}$ letter from the top is the one last remaining! This just happens to be letter \#6, so we know that $a_{4}=6$.

As $n$ increases, we could keep listing the stacks, but as the stacks get larger it quickly gets tedious to do so. However, because we have an iterative process (in which every step of the process is essentially a smaller version of the previous step), we think of using recursion. Can we determine a formula for $a_{n}$ in terms of $a_{n-1}$?

In our exploratory work above, we saw that $a_{4}$ was the number of the letter that was in the $6^{\text{th}}$ position after the first pass. But $a_{3}=6$, so we can also say that $a_{4}$ was the number of the letter that was in the $\left(a_{3}\right)^{\text{rd}}$ position after the first pass. Extending this logic to the general case, we know that $a_{n}$ will be the number of the letter in the $\left(a_{n-1}\right)^{\text{th}}$ position after we do our first pass.

> **Concept:** Try to use your experimentation as a guide for creating a description or formula for the general problem. This is what scientists and mathematicians do: they perform specific experiments to try to understand a general theory.

We still need to convert the phrase "$\left(a_{n-1}\right)^{\text{th}}$ position" into a formula for the number of that letter.
One observation that should be apparent from working out the smaller cases is that the letters remaining after the first pass through the stack are exactly the even-numbered letters, and they are stacked in reverse order, with letter $\# 2^{n}$ at the top and letter $\# 2$ at the bottom. We want the $\left(a_{n-1}\right)^{\text{th}}$ letter in this stack. This is also the letter that is $2^{n-1}-a_{n-1}+1$ from the bottom (make sure you see why we need to add 1 here). Therefore, it is letter number $2\left(2^{n-1}-a_{n-1}+1\right)$.

We have just established our recurrence relation -- it's
$$a_{n}=2\left(2^{n-1}-a_{n-1}+1\right),$$
with initial condition $a_{0}=1$. We can now plug-and-chug with this recurrence to get our value of $a_{11}$. For practice -- and to check our work -- we'll start at $a_{0}$, even though we've already computed the first few values of $a$.
$$\begin{array}{l}
a_{0}=1 \\
a_{1}=2\left(2^{0}-a_{0}+1\right)=2(1-1+1)=2 \\
a_{2}=2\left(2^{1}-a_{1}+1\right)=2(2-2+1)=2 \\
a_{3}=2\left(2^{2}-a_{2}+1\right)=2(4-2+1)=6 \\
a_{4}=2\left(2^{3}-a_{3}+1\right)=2(8-6+1)=6 \\
a_{5}=2\left(2^{4}-a_{4}+1\right)=2(16-6+1)=22
\end{array}$$

$$\begin{aligned}
a_{6} & =2\left(2^{5}-a_{5}+1\right)=2(32-22+1)=22 \\
a_{7} & =2\left(2^{6}-a_{6}+1\right)=2(64-22+1)=86 \\
a_{8} & =2\left(2^{7}-a_{7}+1\right)=2(128-86+1)=86 \\
a_{9} & =2\left(2^{8}-a_{8}+1\right)=2(256-86+1)=342 \\
a_{10} & =2\left(2^{9}-a_{9}+1\right)=2(512-342+1)=342 \\
a_{11} & =2\left(2^{10}-a_{10}+1\right)=2(1024-342+1)=1366
\end{aligned}$$

Therefore, envelope \#1366 will be the last one remaining. $\square$

### Exercises

**10.4.1** $\star$ Surely you noticed the pattern that $a_{k}=a_{k+1}$ whenever $k$ is odd. Can you come up with an explanation for that pattern? **Hints:** 57

**10.4.2** $\star$ Can you find a closed-form formula for $a_{n}$? **Hints:** 255, 99

## 10.5 Problems Involving Catalan Numbers

Problems

**Problem 10.8:** In how many ways can 10 people sitting around a circular table simultaneously shake hands (so that there are 5 handshakes going on), such that no two people cross arms? For example, the handshake arrangement on the left side below is valid, but the arrangement on the right side is invalid.

Valid

Invalid
(a) Compute by hand the number of handshake arrangements for 2, 4, or 6 people sitting around a table.
(b) It's a bit hard to do it by hand for 8 people (you can try if you like), so we'll look for a more clever approach. Pick one person (out of the 8); how many people can he shake hands with?
(c) For each possible handshake for the first person in (b), in how many ways can the rest of the table shake hands?
(d) Use your answers from (b) and (c) to count the number of 8-person handshake arrangements.
(e) Can you extend your reasoning from (b)-(d) above to solve the 10-person problem?

**Problem 10.9:** How many ways are there to arrange 5 open parentheses "(" and 5 closed parentheses ")" such that the parentheses "balance," meaning that, as we read left-to-right, there are never more )'s than ('s? For example, the arrangement $((()())())$ is valid, but the arrangement $(()()))(()$ is invalid.
(a) Compute by hand the number of arrangements for 1, 2, and 3 pairs of parentheses. Do your answers look familiar?
(b) Try to find a 1-1 correspondence between arrangements of $n$ pairs of parentheses and handshake arrangements of $2 n$ people (from Problem 10.8).

**Problem 10.10:** How many 10-step paths are there from $(0,0)$ to $(5,5)$ on the grid below?
(a) It may be tempting to answer $\frac{1}{2}\binom{10}{5}=126$. Explain why this is incorrect.
(b) Compute by hand the number of paths on the half-grid to $(1,1),(2,2)$, and $(3,3)$. Notice anything familiar?
(c) Try to find a 1-1 correspondence between solutions to this problem and solutions to one of the two previous problems.

**Problem 10.11:** In how many ways can a convex heptagon (a 7-sided polygon) be triangulated? (To triangulate a polygon means to draw enough diagonals to divide it into a bunch of triangles, as in the example shown at right.)

We'll explore several problems that look very different on the surface, but that actually all have the same underlying structure. As we work through these problems, try to keep them all in the back of your mind, with an eye towards the features in the various problems that are similar.

> **Extra!** Eugène Catalan (1814-1894). The Catalan numbers (which we will be exploring in this section) are named after the $19^{\text{th}}$-century mathematician Eugène Catalan. He is also known for his conjecture (made in 1844) that 8 and 9 are the only consecutive positive integers that are perfect powers ($8=2^{3}$ and $9=3^{2}$). This conjecture remained unproven until 2002, when it was proved by Preda Mihăilescu.

**Problem 10.8:** In how many ways can 10 people sitting around a circular table simultaneously shake hands (so that there are 5 handshakes going on), such that no two people cross arms? For example, the handshake arrangement on the left side below is valid, but the arrangement on the right side is invalid.

Valid

Invalid

*Solution for Problem 10.8:* As we often do, we can experiment on smaller versions of the same problem in order to get some idea for what's going on in general.

If there are 2 people, then there is obviously only one way for them to shake hands.
If there are 3 people, then there's no way that they can all shake hands, because there will always be an odd person left out. In general, we must always have an even number of people.

If there are 4 people, then there are 3 ways for them to shake hands (pick one of the people, and choose one of the other 3 people to shake hands with him; the other two people are then forced to shake with each other). But one of these ways is illegal: the pairs of people sitting across from each other cannot shake hands, since their arms would cross. So there are only 2 legal handshake configurations. In the figure below, we see the two legal handshake configurations on the left, and the $3^{\text{rd}}$ (illegal) configuration on the right.

If there are 6 people, then things get a bit more complicated. The first thing to note is that no one can shake hands with the person sitting 2 positions away from them on the left or on the right, because if they did, they'd "cut off" a person who would not be able to shake hands with anyone.

This leaves us with two cases.
Case 1: Some pair of people who are directly across from each other shake hands. There can only be one such pair, since two or more such pairs would cross each other at the center of the table. There are 3 choices for a pair of opposite people, and once we have chosen such a pair, the rest of the handshakes are fixed (the two people on each side of the central handshake must shake with each other). These three cases are shown in the figure below:

Case 2: Everybody shakes hands with one of his/her neighbors. There are two possibilities, depending on whether a specific person shakes hands to the left or to the right, as shown in the figure below:

So there are a total of $3+2=5$ ways for 6 people to legally shake hands.
When we get up to 8 people, it's starting to get too complicated to list all the configurations. So let's look at it from a particular person's point-of-view. As in the 6-person case above, we cannot leave an odd number of people on either side of this person's handshake. So our initial person cannot shake hands with anybody that is an even number of people away. In the figure to the right, we show a circled initial person, and his allowed handshakes are shown by dashed lines. Note that each of these handshakes ends at a person who is an odd number of people away from our initial (circled) person.

If the initial person shakes hands with a neighbor, we can think of the remaining 6 people as being in a smaller circle, as in the figure below:

These 6 remaining people have 5 ways to shake, just as in the 6-person problem. Since the initial person has 2 neighbors with whom to shake, this means that there are $2(5)=10$ handshake arrangements that start with our initial person shaking hands with a neighbor.

Otherwise, our initial person has to shake with a person who is 3 positions to his left or right. Once this is done, the two people who are "cut off" from the rest must shake with each other, and the other 4 people form a 4-person mini-table that can shake in 2 ways:

This gives another $2(2)=4$ handshake arrangements, since there are 2 choices of the person that is 3 away from the original person, and then 2 choices to finish the handshaking at the 4-person mini-table.

Therefore, there are $10+4=14$ ways for 8 people to shake hands.
Finally, we can use this same strategy for 10 people. Choose an initial person. This person has 5 choices for whom to shake hands with, as shown in the picture to the right. If he shakes with one of his neighbors (2 choices), then the remaining 8 people form a mini-table that can shake in 14 ways. If he shakes with a person 3 positions away (2 choices), then 2 people are cut off (and must shake), and the other 6 people form a mini-table that can shake in 5 ways. If he shakes with the person directly opposite (1 choice), then each side of the table has a group of 4 people, each of which can shake in 2 ways.

Therefore, the number of handshake arrangements for 10 people is
$$2(14)+2(5)+1(2)(2)=28+10+4=42 .$$

Before we go on, let's list the numbers that we found while working through the previous problem:

| Number of people | 2 | 4 | 6 | 8 | 10 |
|---|---|---|---|---|---|
| Number of handshake configurations | 1 | 2 | 5 | 14 | 42 |

Keep these numbers in mind as we continue through this section. $\square$

**Problem 10.9:** How many ways are there to arrange 5 open parentheses "(" and 5 closed parentheses ")" such that the parentheses "balance," meaning that, as we read left-to-right, there are never more )'s than ('s? For example, the arrangement $((()())())$ is valid, but the arrangement $(()()))(()$ is invalid.

*Solution for Problem 10.9:* As we often do, let's experiment with small values.
If we have 1 set of parentheses, then we only have one possibility: ().
If we have 2 sets of parentheses, we can either nest them as $(())$, or we can list both pairs one after the other as $()(). $ So there are 2 possibilities.

If we have 3 sets of parentheses, then a little experimentation will show that there are 5 possibilities:
$$()()(), \quad (())(), \quad ()(()), \quad (()()), \quad ((())).$$

Hmmm..., $1,2,5, \ldots$. Do you recognize these numbers? They are the same numbers that we got for the number of non-crossing handshakes of people sitting at a round table in Problem 10.8. Perhaps there is a connection between the two problems.

> **Concept:** When you see the same answer for two different problems, look for a connection, or better yet, for a 1-1 correspondence between them.

Since the parentheses come in pairs, it's natural to think that in any 1-1 correspondence between parenthesis-arrangements and valid handshakes around a table, each set of parentheses will represent two people shaking hands. The fact that the parentheses must be properly nested will somehow correspond to the condition that handshakes cannot cross.

For instance, we can list all of the arrangements of 3 pairs of parentheses, and their corresponding handshake arrangements. We'll label both the parentheses and the people with the letters A through F, and note how each pair of parentheses corresponds to a pair of people that are shaking hands.

Let's see this further in an example with 5 sets of parentheses and 10 people around a table. We'll label the people around the table A through J, and the parentheses will also be labeled with A through J as we read from left to right. Each matching pair of parentheses corresponds to a handshake. A sample correspondence is shown on the next page.

This leads to a 1-1 correspondence
$$\left\{\begin{array}{l}
\text { parenthesis arrangements of } \\
n \text { pairs of parentheses }
\end{array}\right\} \Leftrightarrow\left\{\begin{array}{l}
\text { handshake arrangements of } \\
2 n \text { people around a table }
\end{array}\right\} .$$

Thus the answer to our problem is the same as the number of handshake arrangements of 10 people, which is 42.

That's two problems so far involving the sequence $1,2,5,14,42, \ldots$. You should therefore not be surprised by what you will find in the next problem. $\square$

**Problem 10.10:** How many 10-step paths are there from $(0,0)$ to $(5,5)$ on the grid below?

*Solution for Problem 10.10:* The first thing that we notice is that the grid shown is exactly the part of the full $5 \times 5$ grid that is below the main diagonal, as shown below:

This might suggest the following quick "solution":

> **Bogus Solution:** We know that there are $\binom{10}{5}=252$ paths on the full grid. Since we only have the lower-half of the grid to work with, that means that we have $\frac{252}{2}=126$ paths on the lower-half of the grid.

This is of course absurd, as there are many paths that pass through both halves of the grid.

So how can we count the paths that only go below the main diagonal?
Once again, let's count the paths in some smaller cases.
If the half-grid is $1 \times 1$, then there's only one path.

If the half-grid is $2 \times 2$, then there are 2 paths.

If the half-grid is $3 \times 3$, then there are 5 paths.

There are those numbers again: $1,2,5, \ldots$. So we'll once again look for a 1-1 correspondence between this problem and one of the previous problems. Since each path from $(0,0)$ to $(n, n)$ consists of $n$ moves up and $n$ moves to the right, we think to try to find a correspondence between these paths and lists of $n$ "("s and $n$ ")"s.

Indeed, we can make a 1-1 correspondence
$$\{\text{balanced expressions with } n \text{ pairs of parentheses}\} \leftrightarrow \{\text{paths on an } n \times n \text{ grid below the diagonal}\}$$
by letting each "(" represent a move to the right and each ")" represent a move up. As long as there are more "("s than ")"s, there will be more rights than ups, and the path will never cross above the main diagonal of the $n \times n$ grid.

Therefore, there are 42 paths on the $5 \times 5$ half-grid, since there are 42 possible nested expressions with 5 pairs of parentheses. $\square$

You can probably guess ahead of time what the answer to the next problem will be!

**Problem 10.11:** In how many ways can a convex heptagon (a 7-sided polygon) be triangulated? (To triangulate a polygon means to draw enough diagonals to divide it into a bunch of triangles, as in the example shown at right.)

*Solution for Problem 10.11:* As we often do, we can build up to a solution by looking at smaller cases. There's only 1 way to triangulate a triangle: do nothing, because it's already triangulated! There are 2 ways to triangulate a convex quadrilateral: draw in either diagonal.

Triangulating a pentagon is the first tricky case. The easiest way to think about it is to pick an edge, and think about the possibilities for that edge. For example, we look at the bottom edge in the regular pentagon shown below, and we see that it can be a part of one of three possible triangles in some triangulation:

In the middle pentagon shown above, we see that the triangulation is already finished. In the left and right pentagons, we still need to draw in a diagonal of the remaining quadrilateral region, so there are 2 choices for how to finish each of those triangulations. Therefore, there are a total of $2+1+2=5$ possible triangulations of the pentagon.

Hmmm...1, 2, and 5 ways to triangulate triangles, quadrilaterals, and pentagons. We should not be surprised if we find 14 ways to triangulate a hexagon! Given a hexagon, we fix an edge and draw the possible triangulations:

*Figure 10.1: Four possibilities to triangulate a hexagon*

In the left and right hexagons in Figure 10.1, we have 5 ways to finish the triangulation by triangulating the pentagon region that remains. In the middle two hexagons in Figure 10.1, we have 2 ways to finish the triangulation by triangulating the quadrilateral region that remains. Therefore there are $5+2+2+5=14$ ways to triangulate a hexagon. (No surprise!)

Finally, there are five ways to start the triangulation of a heptagon from a fixed edge:

We see that there are $14+5+4+5+14=42$ ways to finish the triangulation (note that the center heptagon above has 4 ways since each of the two remaining quadrilaterals must be triangulated in one of 2 ways).

We saw the sequence
$$1,2,5,14,42, \ldots$$
in each of the four problems in this section. These are the Catalan numbers. $\square$

### Exercises

**10.5.1** In how many ways can an octagon be triangulated?

**10.5.2** Compute the number of ways to place 5 indistinguishable balls into 5 distinguishable boxes $B_{1}, B_{2}, \ldots, B_{5}$ such that boxes $B_{1}$ through $B_{i}$ have a total of no more than $i$ balls (for all $1 \leq i \leq 5$).

**10.5.3** How many 5-digit numbers are such that the digits, as read left-to-right, are nondecreasing, and that the $i^{\text{th}}$ digit from the left is at most $i$? (For example, 12235 is such a number.) **Hints:** 263

**10.5.4** $\star$ In how many ways can the shape at the far left be tiled with 4 rectangular tiles, such that each tile has integer side lengths (where a side length of 1 corresponds to a side of one of the constituent squares)? A sample such tiling is shown at left. **Hints:** 284, 325

**10.5.5** $\star$ Determine the number of paths from $(0,0)$ to $(6,6)$ in the grid at right, in which every step is either up or to the right, that pass through none of the points $(1,1),(3,3)$, or $(5,5)$ (these points are marked with large X's in the grid). **Hints:** 90, 55

## 10.6 Formulas for the Catalan Numbers

Problems

**Problem 10.12:** Can you write a recurrence relation for the Catalan numbers?

**Problem 10.13:** Compare the $n^{\text{th}}$ Catalan number with the binomial coefficient $\binom{2 n}{n}$. Do you notice any pattern?

**Problem 10.14:** Find a 1-1 correspondence between:
$$\left\{\begin{array}{l}
\text { paths from }(0,0) \text { to }(n, n) \text { that go above the } \\
\text { main diagonal }
\end{array}\right\} \quad \leftrightarrow \quad \{\text { paths from }(0,0) \text { to }(n-1, n+1)\} .$$

**Problem 10.15:** Find a formula for the $n^{\text{th}}$ Catalan number.

As we've seen in the problems in the previous section, the $n^{\text{th}}$ Catalan number can be defined as:
- the number of ways that $2 n$ people sitting around a table can shake hands, so that no two handshakes cross arms;
- the number of ways to write $n$ ('s and $n$ )'s such that the parentheses are balanced;
- the number of $2 n$-step paths on a rectangular grid from $(0,0)$ to $(n, n)$ that do not cross above the main diagonal;
- the number of ways to triangulate a convex $(n+2)$-gon.

It would be nice if we could easily compute the Catalan numbers. For now, let's focus on the recursive definition.

**Problem 10.12:** What is the recurrence relation for the Catalan numbers?

*Solution for Problem 10.12:* We've actually already seen it in the problems in the previous section. For each of the problems in the previous section, we can break down the problem of size $n$ into cases, where each case is composed of two smaller problems whose sizes add to $n-1$.

For instance, in Problem 10.8, we start with a table with $2 n$ people. Once we place the initial handshake, we are left with two smaller tables with $2(n-1)$ people combined.

In Problem 10.9, we can look at the first parenthesis on the left and its corresponding closing parenthesis. This splits the rest of the parentheses into two groups: those that are inside this first pair, and those that are to the right of this pair. For example, in the following 10-pair nesting, the first set of parentheses (in bold) splits the rest of the parentheses into a 6-pair group (inside the bold parentheses) and a 3-pair group (to the right of the bold parentheses):
$$(((())(())())(())()$$

The first set of parentheses will always split the remaining $n-1$ pairs into two groups of balanced parentheses, although one of the groups may be empty.

We can use the 1-1 correspondence between Problem 10.9 and Problem 10.10 to see how to set up the recursion for the paths on the half-grid from $(0,0)$ to $(n, n)$. The idea is that the end of the first complete set of parentheses corresponds to the place where the path first touches the diagonal after leaving $(0,0)$. For example, we show a 5-parentheses nesting and its corresponding path in the figure below. The first set of parentheses is shown in bold, and it corresponds to the path's first touching of the main diagonal at $(2,2)$.

The path is now broken into 2 paths on 2 smaller half-grids.
In all of these problems, the solution is the $n^{\text{th}}$ Catalan number $C_{n}$, and we arrive at the solution by breaking up the problem into a sum of two smaller problems. Specifically, we see that $C_{n}$ is the sum of all possible products of the form $C_{k} C_{l}$ where $k+l=n-1$. That is,
$$C_{n}=C_{0} C_{n-1}+C_{1} C_{n-2}+\cdots+C_{n-1} C_{0}=\sum_{k=0}^{n-1} C_{k} C_{n-1-k}$$

The sequence starts at $C_{0}=1$.

We can once again verify this recursion for the numbers that we've already computed:
$$\begin{array}{l}
C_{0}=1, \\
C_{1}=C_{0} C_{0}=1, \\
C_{2}=C_{0} C_{1}+C_{1} C_{0}=1+1=2, \\
C_{3}=C_{0} C_{2}+C_{1} C_{1}+C_{2} C_{0}=2+1+2=5, \\
C_{4}=C_{0} C_{3}+C_{1} C_{2}+C_{2} C_{1}+C_{3} C_{0}=5+2+2+5=14, \\
C_{5}=C_{0} C_{4}+C_{1} C_{3}+C_{2} C_{2}+C_{3} C_{1}+C_{4} C_{0}=14+5+4+5+14=42 .
\end{array}$$

Let's continue and compute the next couple of Catalan numbers:
$$\begin{array}{l}
C_{6}=C_{0} C_{5}+C_{1} C_{4}+C_{2} C_{3}+C_{3} C_{2}+C_{4} C_{1}+C_{5} C_{0}=42+14+10+10+14+42=132 \\
C_{7}=C_{0} C_{6}+C_{1} C_{5}+C_{2} C_{4}+C_{3} C_{3}+C_{4} C_{2}+C_{5} C_{1}+C_{6} C_{0}=132+42+28+25+28+42+132=429
\end{array}$$

So now we have a recursive formula for the Catalan numbers. However, it is somewhat unsatisfying. Not only is it recursive, but each Catalan number depends on all of the preceding Catalan numbers, not just the one or two immediately prior. It would be much nicer to have a closed-form formula into which we could plug some value of $n$ and have $C_{n}$ just pop out. But where can we begin to find such a formula?

Problem 10.10 looks most promising, as it's most related to a problem that we feel like we understand well and know how to find a formula for, namely paths on a grid from $(0,0)$ to $(n, n)$. We know that without any restrictions, there are $\binom{2 n}{n}$ such paths. So that's a good place to start. $\square$

**Problem 10.13:** Compare the $n^{\text{th}}$ Catalan number with the binomial coefficient $\binom{2 n}{n}$. Do you notice any pattern?

*Solution for Problem 10.13:* Let's list the first 7 Catalan numbers and the first 7 values of $\binom{2 n}{n}$ and see if we notice anything.

| $n$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| $C_{n}$ | 1 | 2 | 5 | 14 | 42 | 132 | 429 |
| $\binom{2n}{n}$ | 2 | 6 | 20 | 70 | 252 | 924 | 3432 |

It's not too clear how to find a pattern between these two rows of numbers, but the one column that might jump out at you is the $n=4$ column with the numbers 14 and 70, since $70=5(14)$. This might cause you to notice that $\binom{2 n}{n}$ always appears to be a multiple of $C_{n}$. Let's expand our chart:

| $n$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| $C_{n}$ | 1 | 2 | 5 | 14 | 42 | 132 | 429 |
| $\binom{2n}{n}$ | 2 | 6 | 20 | 70 | 252 | 924 | 3432 |
| $\frac{\binom{2n}{n}}{C_{n}}$ | 2 | 3 | 4 | 5 | 6 | 7 | 8 |

Now we have strong experimental evidence that $C_{n}=\frac{1}{n+1}\binom{2 n}{n}$.

Of course, observing a pattern is not a proof. Let's further examine the "paths on a grid" problem and see what else we might determine. We know that $\binom{2 n}{n}$ counts the number of paths from $(0,0)$ to $(n, n)$ on a rectangular grid. We also know that $C_{n}$ counts the number of these paths that don't go above the diagonal. So $\binom{2 n}{n}-C_{n}$ counts the number of paths that do go above the diagonal. Since we suspect that $C_{n}=\frac{1}{n+1}\binom{2 n}{n}$, we suspect that the number of paths that go above the diagonal should be:
$$\binom{2 n}{n}-\frac{1}{n+1}\binom{2 n}{n}=\frac{n}{n+1}\binom{2 n}{n} .$$

We do a bit of algebraic manipulation with this quantity:
$$\frac{n}{n+1}\binom{2 n}{n}=\frac{n(2 n)!}{(n+1) n!n!}=\frac{(2 n)!}{(n+1)!(n-1)!}=\binom{2 n}{n-1} .$$

This last quantity gives us an idea for a 1-1 correspondence: $\square$

**Problem 10.14:** Find a 1-1 correspondence between:
$$\left\{\begin{array}{l}
\text { paths from }(0,0) \text { to }(n, n) \text { that go above the } \\
\text { main diagonal }
\end{array}\right\} \Leftrightarrow \quad \{\text{paths from }(0,0) \text{ to }(n-1, n+1)\} .$$

*Solution for Problem 10.14:* This can be a bit tricky to see, so let's play with the $n=2$ case.
There are $\binom{4}{2}=6$ paths from $(0,0)$ to $(2,2)$, and we know that $C_{2}=2$ of them stay on or below the main diagonal, so the other 4 go above the diagonal. We also know that there are $\binom{4}{1}=4$ paths from $(0,0)$ to $(1,3)$. (Good -- there are the same number of paths in each category, which is a necessity for there to be a 1-1 correspondence.)

Let's draw the 4 paths in each category, and see if we can match them up. (I'm going to help you out and list them in the order that we will match them -- see if you can find the correspondence.)

In each column, let's start at $(0,0)$, and let's mark (with a circle) the point on each path where the two paths differ. In other words, the path from $(0,0)$ to the circled point is the same in both paths, but after the circled point, one path goes up whereas the other goes right.

We see that in each column, the path from $(0,0)$ to the circled point in both pictures is the same. However, what's more interesting is what happens after the circled point. Compare the paths after the circled point in both pictures of a column. They're mirror images of each other!

To be more precise, let's list the paths using "r" for a step to the right and "u" for a step up. We'll place in bold all of the steps after the circled point.

| Paths from $(0,0)$ to $(2,2)$ that go above the main diagonal | uurr | urur | urru | ruur |
|---|---|---|---|---|
| Paths from $(0,0)$ to $(1,3)$ | uruu | uuru | uuur | ruuu |

Note that the unbolded parts of the paths -- the parts between $(0,0)$ and the circled point -- are identical, and the bolded parts of the paths -- the parts between the circled point and the end -- are exactly reversed.

This suggests a general strategy for finding a 1-1 correspondence. Given a path from $(0,0)$ to $(n, n)$ that goes above the diagonal, circle the first point at which the path crosses above the diagonal. Then reverse all steps past the circled point: change ups to rights and rights to ups.

Here's an example where $n=5$. The original path is shown as solid, and the new path (after the transformation described above) is shown as dashed.

Note that the solid path, before the circled point, has one more up step than right step. After the circled point, the solid path has one more right step than up step (since the circled point lies one "up" step above the diagonal). After the reversal transformation, the dashed path has, after the circled point, one more up step than right step. Hence, starting at $(0,0)$, the combined new path has 2 more up steps than right steps. Since it still has $2 n$ steps in total, it must have $n+1$ up steps and $n-1$ right steps, and thus the path ends at $(n-1, n+1)$.

This process is clearly reversible, and hence we have a 1-1 correspondence:
$$\left\{\begin{array}{l}
\text { paths from }(0,0) \text { to }(n, n) \text { that go above the } \\
\text { main diagonal }
\end{array}\right\} \quad \leftrightarrow \quad \{\text{paths from }(0,0) \text{ to }(n-1, n+1)\} .$$

$\square$

**Problem 10.15:** Find a formula for the $n^{\text{th}}$ Catalan number.

*Solution for Problem 10.15:* We know that the $n^{\text{th}}$ Catalan number is the number of paths from $(0,0)$ to $(n, n)$ that don't go above the diagonal. However, we know from Problem 10.14 that the paths that do go above the diagonal are in 1-1 correspondence with paths to $(n-1, n+1)$. Since there are $\binom{2 n}{n}$ paths from $(0,0)$ to $(n, n)$ and $\binom{2 n}{n-1}$ paths from $(0,0)$ to $(n-1, n+1)$, we have that
$$C_{n}=\binom{2 n}{n}-\binom{2 n}{n-1} .$$

This does not exactly look like what we conjectured in Problem 10.13, so let's try to simplify it a bit. We start by writing out the expressions for the binomial coefficients:
$$C_{n}=\frac{(2 n)!}{n!n!}-\frac{(2 n)!}{(n-1)!(n+1)!} .$$

We can factor out like terms and simplify:
$$C_{n}=\frac{(2 n)!}{(n-1)!n!}\left(\frac{1}{n}-\frac{1}{n+1}\right)=\frac{(2 n)!}{(n-1)!n!} \cdot \frac{1}{n(n+1)}=\frac{(2 n)!}{(n+1)!n!} .$$

Removing an $(n+1)$ term from the denominator gives us our result:
$$C_{n}=\frac{1}{n+1}\left(\frac{(2 n)!}{n!n!}\right)=\frac{1}{n+1}\binom{2 n}{n} .$$
$\square$

> **Important:** The formula for the $n^{\text{th}}$ Catalan number is
> $$C_{n}=\frac{1}{n+1}\binom{2 n}{n} .$$

### Exercises

**10.6.1** Compute $C_{8}$ both recursively and by the closed-form formula, and verify that they match.

**10.6.2** In how many ways can identical coins be placed in one or more rows on a flat surface, such that there are $n$ coins in the bottom row, and each coin (above the bottom row) is tangent to two coins directly underneath it? The possible configurations for $n=3$ are shown on the next page. **Hints:** 60

**10.6.3** Brazil defeats Germany in a wild World Cup final by the score of 8 to 6. Assuming the 14 goals were equally likely to be scored in any order, find the probability that the score was never tied (except at 0-0). **Hints:** 110

**10.6.4** We form a rooted binary tree as follows. Starting with a root node, we can draw 2 branches (but not 1) from the root to new nodes. From each of these new nodes we can draw 2 branches (but not 1) to new nodes, and so on. Each node either has exactly 2 branches (in which case we call it an internal node) or 0 branches (in which case we call it a leaf). The possibilities with 3 internal nodes are shown below. Prove that the number of rooted binary trees with $n$ internal nodes is the $n^{\text{th}}$ Catalan number. **Hints:** 211

**10.6.5** $\star$ Determine all values of $n$ such that $C_{n}$ is odd. **Hints:** 343, 124, 329

## 10.7 Summary

- Recursion is the name for the general concept of constructing later terms in a sequence from earlier terms.
- In a way, recursion is the opposite of constructive counting. In constructive counting, we think about how we would build the items that we're trying to count. In recursion, we think about how we would break up the items that we're trying to count into smaller pieces.
- Some simple recurrences can be solved by hand, by determining the recursive formula and then simply number-crunching to get the answer that you want.
- Linear recursions are solved in three steps:
  1. Assume that the solution is an exponential, to get the characteristic equation.
  2. Find the roots of the characteristic equation, to get the general solution as a sum of exponential terms with unknown constants.
  3. Use the initial conditions to solve for the constants in the general solution.

- The Catalan numbers $C_{n}$ are given by the following recurrence, where $C_{0}=1$:
$$C_{n}=C_{0} C_{n-1}+C_{1} C_{n-2}+\cdots+C_{n-1} C_{0}=\sum_{k=0}^{n-1} C_{k} C_{n-1-k}$$

They are also given by the closed-form formula $C_{n}=\frac{1}{n+1}\binom{2 n}{n}$.

Also keep in mind the following problem-solving concepts:

> **Concept:** Experiment with smaller examples in order to get a feel for a hard problem. Try to use your experimentation as a guide for creating a description or formula for the general problem. This is what scientists and mathematicians do: they perform specific experiments to try to understand a general theory.

> **Concept:** If a solution method doesn't seem to be getting you anywhere, don't be afraid to start over and try a completely different approach.

> **Concept:** After solving a recurrence (or any problem for that matter), it is often a good idea to plug in some small values to check your work.

> **Concept:** When you see the same answer for two different problems, look for a connection, or better yet, for a 1-1 correspondence between them.

<div class="problems"></div>

## Review Problems

**10.16** A teacher wishes to split his $2 n$ students into $n$ pairs. Use recursion to find $a_{n}$, the number of ways he can form the pairs.

**10.17**
(a) If we draw $n$ lines in the plane, what is the largest number of different regions we can create (in terms of $n$)?
(b) If we draw $n$ circles in the plane, what is the largest number of different regions we can create (in terms of $n$)?
(c) If we draw $n$ pairs of parallel lines in the plane, what is the largest number of different regions we can create (in terms of $n$)?

**10.18** Find a closed-form formula for the recurrence $a_{n}=2 a_{n-1}+a_{n-2}$ for all $n \geq 2$, with the initial conditions $a_{0}=2$ and $a_{1}=3$.

**10.19** A solitaire game is played as follows. Six distinct pairs of matched tiles are placed in a bag. The player randomly draws tiles one at a time from the bag and retains them, except that matching tiles are put aside as soon as they appear in the player's hand. The game ends if the player ever holds three tiles, no two of which match; otherwise the drawing continues until the bag is empty. Find the probability that the player wins the game (by emptying the bag). (Source: AIME)

**10.20** In how many ways can a $3 \times 10$ rectangle be tiled with tiles of size $1 \times 2$?

**10.21** A collection of 8 cubes consists of one cube with edge-length $k$ for each integer $1 \leq k \leq 8$. A tower is to be built using all 8 cubes according to the following rules:
- Any cube may be the bottom cube in the tower.
- The cube immediately on top of a cube with edge-length $k$ must have edge-length at most $k+2$.

How many different towers can be constructed? (Source: AIME)

**10.22** Define a half-rectangular array of positive integers (shown below) by placing a 1 in the top row, and then letting every subsequent number be the sum of the number immediately above and the number immediately to the left. (If a number is missing, treat it as 0.) If the top row is Row 0, then Row $n$ has $n+1$ entries. Prove that the last entry in Row $n$ is the $n^{\text{th}}$ Catalan number $C_{n}$, for all $n \geq 0$.
$$\begin{array}{llllll}
1 & & & & & \\
1 & 1 & & & & \\
1 & 2 & 2 & & & \\
1 & 3 & 5 & 5 & & \\
1 & 4 & 9 & 14 & 14 & \\
1 & 5 & 14 & 28 & 42 & 42 \\
\end{array}$$

## Challenge Problems

**10.23** We form a word using only $A$'s, $B$'s and $C$'s. Suppose we can never have an $A$ next to a $C$. Find the number of 8-letter words that can be formed. **Hints:** 81

**10.24** A mail carrier delivers mail to the 19 houses on the east side of Elm Street. The carrier notices that no two adjacent houses ever get mail on the same day, but that there are never more than two houses in a row that get no mail on the same day. How many different subsets of houses that get mail on any particular day are possible? (Source: AIME) **Hints:** 196

**10.25** We have the coins $C_{1}, C_{2}, \ldots, C_{n}$. For each $k, C_{k}$ is biased so that, when tossed, it has probability $1 /(2 k+1)$ of showing heads. If $n$ coins are tossed, what is the probability that the number of heads is odd? (Source: Putnam) **Hints:** 70

**10.26** For any positive integer $n$, prove that the number of positive integers whose digit-sums are $2 n$ and whose digits are all 1, 3, or 4, is a perfect square. **Hints:** 248, 264

**10.27** We are given a $2 \times n$ array of nodes, where $n$ is a positive integer. A valid connection of the array is the addition of 1-unit-long horizontal and vertical edges between nodes, such that each node is connected to every other node via the edges, and there are no loops of any size. We give some examples for $n=3$:

Valid

Valid

Invalid: loop

Invalid: not connected

Let $T_{n}$ denote the number of valid connections of the $2 \times n$ array. Find $T_{10}$. (Source: USAMTS) **Hints:** 330

**10.28** Consider a regular decagon (10-sided polygon) with center $O$. We color, with one of 3 colors, each of the ten triangles formed by connecting $O$ to adjacent vertices of the decagon. How many ways can we perform the coloring such that no two adjacent triangles are the same color? **Hints:** 166, 168

**10.29** $\star$ We construct sequences of numbers as follows: start with
$$S_{1}=1,1$$
and form each subsequent sequence by placing a new term between each term in the previous sequence equal to the sum of the two terms it's being put between:
$$\begin{array}{l}
S_{2}=1,2,1 \\
S_{3}=1,3,2,3,1 \\
S_{4}=1,4,3,5,2,5,3,4,1
\end{array}$$
and so on.
(a) What is the largest element of $S_{n}$? **Hints:** 104, 172
(b) Find a relationship between the number of odd terms and the number of even terms in the sequence $S_{n}$ for even $n$. **Hints:** 285, 333

(Source: ARML)

**10.30** $\star$ A double-good nesting of order $n$ is an arrangement of $2 n$ ")"s and $n$ "("s such that as we read left-to-right, the number of ")"s that have appeared at any point is no more than 2 times the number of "("s that have appeared to that point. For example, the complete list of the double-good nestings of order 2 is:

$())()\quad ()()\quad (())$

Find the number of double-good nestings of order $n$. **Hints:** 148, 8, 246

**10.31** $\star$ Suppose that Germany and Brazil play a soccer rematch in which there are $2 n$ goals scored and that the final score is Brazil $n+m$, Germany $n-m$. How many possible sequences of goals are there such that Germany is never more than $2 m$ goals behind? **Hints:** 348, 128

**10.32** $\star$ Count the number of sequences of integers $a_{1}, a_{2}, a_{3}, a_{4}, a_{5}$ with $a_{i} \leq 1$ for all $i$ such that all partial sums $\left(a_{1}, a_{1}+a_{2}, a_{1}+a_{2}+a_{3}, a_{1}+a_{2}+a_{3}+a_{4}, a_{1}+a_{2}+a_{3}+a_{4}+a_{5}\right)$ are nonnegative. (Source: HMANT) **Hints:** 241, 72

> **Extra!** **General theory of linear recurrences.**
> We can use methods similar to those of Section 10.3 to solve arbitrary linear recurrences of the form
> $$a_{n}=p_{1} a_{n-1}+p_{2} a_{n-2}+\cdots+p_{k} a_{n-k}$$
> where $p_{1}, p_{2}, \ldots, p_{k}$ are constants. We substitute $a_{n}=c^{n}$ to get the characteristic equation of the form
> $$c^{k}-p_{1} c^{k-1}-p_{2} c^{k-2}-\cdots-p_{k}=0$$
>
> Suppose that this characteristic equation has roots $r_{1}, r_{2}, \ldots, r_{j}$ with multiplicities $m_{1}, m_{2}, \ldots, m_{j}$; in other words, the characteristic equation factors as
> $$\left(c-r_{1}\right)^{m_{1}}\left(c-r_{2}\right)^{m_{2}} \cdots\left(c-r_{j}\right)^{m_{j}}=0$$
>
> Each root $r_{i}$ contributes a term to the general solution of the form
> $$\left(\lambda_{i1}+\lambda_{i2} n+\lambda_{i3} n^{2}+\cdots+\lambda_{im_{i}} n^{(m_{i}-1)}\right)\left(r_{i}\right)^{n}$$
> so that the general solution is of the form
> $$a_{n}=\sum_{i=1}^{j}\left(\sum_{s=1}^{m_{i}} \lambda_{is} n^{s-1}\right)\left(r_{i}\right)^{n}$$
>
> Note that there are $k$ constants $\lambda_{is}$ in this expression, since the multiplicities of the roots must sum to $k$. Given $k$ initial values of $a_{n}$, we can always solve the resulting system of linear equations for the $\lambda_{is}$'s. This works regardless of whether the roots are real or complex.
> Proving that this works for any linear recurrence requires advanced algebraic techniques and some knowledge of linear algebra.
