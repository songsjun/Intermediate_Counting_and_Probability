# Chapter 9: Fibonacci Numbers

*The good, of course, is always beautiful, and the beautiful never lacks proportion. - Plato*

## 9.1 Introduction

$$1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987, \ldots$$

What is special about the above sequence of numbers? This sequence is one of the most famous sequences of positive integers in all of mathematics. If you've seen it before, you probably know how these numbers are generated, but if not, I don't want to spoil the surprise!

In this chapter, we'll explore some of the fascinating properties of this sequence.

## 9.2 A Motivating Problem

### Problems

**Problem 9.1:** Mike is climbing a flight of 10 stairs. With each step, he will climb either 1 or 2 stairs. In how many different ways can he climb the flight of stairs?
(a) Try it for 1, 2, 3, or 4 stairs. Your results should appear in the list of numbers above.
(b) Solve the problem by casework, where the cases depend on the number of 2-stair steps that Mike takes.
(c) Let $f(n)$ be the number of ways to climb $n$ steps. How is $f(n)$ related to $f(n-1)$ and $f(n-2)$ ?
(d) Solve the problem by writing an expression for $f(n)$ in terms of $f(n-1)$ and $f(n-2)$, and using this expression, together with your values for $f(1)$ and $f(2)$ from part (a), to compute $f(10)$.

We'll start our investigation of the special sequence listed on the previous page by looking at a problem whose answer is related to the sequence.

**Problem 9.1:** Mike is climbing a flight of 10 stairs. With each step, he will climb either 1 or 2 stairs. In how many different ways can he climb the flight of stairs?

*Solution for Problem 9.1:* We could count this directly with some casework. Let's do that first for practice.
In order to climb 10 stairs, Mike can take $0,1,2,3,4$, or 5 2-stair steps (with the rest being 1 -stair steps).

If he takes 0 2-stair steps and 10 1-stair steps, there is $\binom{10}{0}=1$ way to reach the top.
If he takes 1 2-stair step and 8 1-stair steps, then we have 9 total steps to arrange, and must choose 1 of them to be the 2 -stair step. Therefore, there are $\binom{9}{1}=9$ ways to reach the top.

If he takes 2 2-stair steps and 6 1-stair steps, then we have 8 steps to arrange, and must choose 2 of them to be the 2 -stair steps. Therefore, there are $\binom{8}{2}=28$ ways to reach the top.

If he takes 3 2-stair steps and 4 1-stair steps, then there are $\binom{7}{3}=35$ ways to reach the top.
If he takes 4 2-stair steps and 2 1-stair steps, then there are $\binom{6}{4}=15$ ways to reach the top.
If he takes 5 2-stair steps and 0 1-stair steps, then there is $\binom{5}{5}=1$ way to reach the top.
Therefore, there are $1+9+28+35+15+1=89$ ways in which Mike can climb the stairs.
That was simple enough. But there's another way that we can think about the problem.
Consider Mike's final step. Either Mike took a 1 -stair step from the $9^{\text {th }}$ stair, or he took a 2 -stair step from the $8^{\text {th }}$ stair. This means that we have a 1-1 correspondence:
$$\{\text { Ways to climb } 10 \text { stairs }\} \leftrightarrow\{\text { Ways to climb } 9 \text { stairs }\} \cup\{\text { Ways to climb } 8 \text { stairs }\} .$$

Therefore, when we count, we get
(Number of ways to climb 10 stairs) = (Number of ways to climb 9 stairs)
\+ (Number of ways to climb 8 stairs).
If we let $f(n)$ denote the number of ways to climb $n$ stairs, then this means that $f(10)=f(9)+f(8)$.
This works for any number of stairs (as long as there are more than 2 ). In general, for any positive integer $n>2$, we have the equation $f(n)=f(n-1)+f(n-2)$. In this way, we can build up to the number of ways to climb 10 stairs by counting the number of ways to climb a smaller number of stairs.

We start by noting that $f(1)=1$ and $f(2)=2$. If there is only 1 stair, then the only way to climb it is via a 1 -stair step. If there are 2 stairs, then we have 2 choices: Mike can take two 1 -stair steps, or he can take a single 2 -stair step.

> **Extra!** You don't have to see the whole staircase, just take the first step. - Martin Luther King, Jr.

Now we can count the number of ways to climb larger staircases:
$$\begin{array}{l}
f(3)=f(2)+f(1)=2+1=3, \\
f(4)=f(3)+f(2)=3+2=5, \\
f(5)=f(4)+f(3)=5+3=8, \\
f(6)=f(5)+f(4)=8+5=13, \\
f(7)=f(6)+f(5)=13+8=21, \\
f(8)=f(7)+f(6)=21+13=34, \\
f(9)=f(8)+f(7)=34+21=55, \\
f(10)=f(9)+f(8)=55+34=89 .
\end{array}$$

Once again, we see that there are 89 ways to climb a 10-stair staircase.
If we list $f(1), f(2), f(3), \ldots$, then we (almost) get the sequence that opened this chapter:
$$1,2,3,5,8,13,21,34,55,89, \ldots .$$

Each number in the sequence (after the first two) is the sum of the two numbers immediately before it: $2=1+1,3=2+1,5=3+2$, and so on.

The only thing that's different from the sequence on page 172 is that the sequence on page 172 has an extra 1 at the start. We can add this 1 to our example, though, without any difficulty. If there are 0 stairs, then there's only 1 way to climb this staircase: do nothing! So $f(0)=1$ makes sense. Also note that $f(2)=f(1)+f(0)=1+1=2$, so that our equation $f(n)=f(n-1)+f(n-2)$ holds for all positive integers $n \geq 2$.

When we add this first 1 to our sequence, we get the sequence that we first saw at the start of the chapter:
$$1,1,2,3,5,8,13,21,34,55,89, \ldots .$$

These numbers are called the Fibonacci numbers, in honor of the Italian mathematician Leonardo of Pisa, whose nickname was "Fibonacci," and who first published the sequence of numbers in his Liber abaci in 1202.

We've seen that each Fibonacci number is the sum of the previous two Fibonacci numbers. We can write this using a more formal definition.

We typically denote sequences using a variable with a subscript, such as
$$a_{1}, a_{2}, a_{3}, \ldots$$

Thus, $a_{1}$ is the first number in the sequence, $a_{2}$ is the second number in the sequence, and so on. Sometimes we'll start our lists with $a_{0}$ instead of $a_{1}$, so that our sequence would be
$$a_{0}, a_{1}, a_{2}, \ldots$$

The Fibonacci numbers are defined by $F_{1}=1, F_{2}=1$, and $F_{n}=F_{n-1}+F_{n-2}$ for all positive integers $n>2$. So, for example,

$$\begin{array}{l}
F_{3}=F_{2}+F_{1}=1+1=2 \\
F_{4}=F_{3}+F_{2}=2+1=3 \\
F_{5}=F_{4}+F_{3}=3+2=5 \\
F_{6}=F_{5}+F_{4}=5+3=8 \\
F_{7}=F_{6}+F_{5}=8+5=13 \\
\text { etc. }
\end{array}$$

Sometimes, it is convenient to have a value of $F_{0}$, so we also define $F_{0}=0$. Note that $1=F_{2}=F_{1}+F_{0}= 1+0$, so this definition is consistent.

Relating this notation to our solution to Problem 9.1, we see that the number of ways that Mike can climb $n$ steps is $F_{n+1}\left(\right.$ not $\left.F_{n}\right)$.

## 9.3 Some Fibonacci Problems

### Problems

**Problem 9.2:** An adult pair of rabbits is in an enclosed yard. Every month, every adult pair of rabbits produces a pair of offspring, which grows to adulthood in 2 months and then begins itself to produce offspring. (Assume that rabbits never die.)
(a) Make a table of the number of adult pairs of rabbits, the number of child pairs of rabbits, and the total number of pairs of rabbits, for each month of the year.
(b) Do you see any patterns in your table from part (a)?
(c) How does your table relate to Fibonacci numbers?
(d) Prove your results.

**Problem 9.3:** How many subsets of $\{1,2, \ldots, n\}$ have no two consecutive integers as elements? (For example, the subset $\{1,3,4,8\}$ has the consecutive integers 3 and 4 as elements, but the subset $\{2,4,7,9\}$ has no two consecutive integers as elements.)
(a) List and count all of the valid subsets for $n=1,2,3,4$.
(b) Do you notice the pattern (again)?
(c) Establish a 1-1 correspondence:
$$\begin{array}{c}
\left\{\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n\} \text { with no } \\
\text { two consecutive elements }
\end{array}\right\} \\
\left(\left\{\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n-1\} \text { with } \\
\text { no two consecutive elements }
\end{array}\right\} \cup\left\{\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n-2\} \text { with } \\
\text { no two consecutive elements }
\end{array}\right\}\right) \cdot
\end{array}$$

Use this correspondence to answer the original problem.

**Problem 9.4:** In how many ways can we tile a $2 \times n$ checkerboard with $n$ tiles of size $1 \times 2$, such that each tile covers exactly two squares? An example with $n=6$ is shown below.

**Problem 9.5:** Prove that for any $k \geq 1$,
$$F_{1}+F_{3}+F_{5}+\cdots+F_{2 k+1}=F_{2 k+2} .$$

**Problem 9.6:** Prove that for all positive integers $n \geq 1$,
$$F_{1}^{2}+F_{2}^{2}+\cdots+F_{n}^{2}=F_{n} F_{n+1} .$$

As we will see in this section, the Fibonacci numbers pop up in a lot of different contexts in counting problems. We'll start with a classic example.

**Problem 9.2:** An adult pair of rabbits is in an enclosed yard. Every month, every adult pair of rabbits produces a pair of offspring, which grows to adulthood in 2 months and then begins itself to produce offspring. How many pairs of rabbits will there be after a year? (Assume that rabbits never die.)

*Solution for Problem 9.2:* We can experiment and make a table. We use the facts that every month:
- Every adult pair has a pair of newborn offspring;
- Every pair of newborns from last month becomes a pair of child rabbits this month;
- Every pair of child rabbits from last month becomes a pair of adult rabbits this month.

Using these facts, we can generate a table:

> **Extra!**
> Leonardo of Pisa a.k.a. Fibonacci
> It is not universally agreed upon how Leonardo of Pisa got the nickname "Fibonacci." It is generally thought to be a shortening of "filius Bonacci," which means "son of Bonacci," although it is unclear whether Bonacci was a family name or simply a nickname (meaning perhaps "lucky" or "good natured"). The Fibonacci numbers were not named after Fibonacci until long after his death, by the $19^{\text {th }}$-century French mathematician Edouard Lucas (who also has a series of numbers named after him, as you will see in an Exercise later in the chapter). See the book's links page on page vi for links to sources for the above and more complete biographical information on Fibonacci.

| Month | # of adult pairs | # of child pairs | # of newborn pairs | Total |
|-------|-----------------|-----------------|-------------------|-------|
| 0 | 1 | 0 | 0 | 1 |
| 1 | 1 | 0 | 1 | 2 |
| 2 | 1 | 1 | 1 | 3 |
| 3 | 2 | 1 | 2 | 5 |
| 4 | 3 | 2 | 3 | 8 |
| 5 | 5 | 3 | 5 | 13 |
| 6 | 8 | 5 | 8 | 21 |
| 7 | 13 | 8 | 13 | 34 |
| 8 | 21 | 13 | 21 | 55 |
| 9 | 34 | 21 | 34 | 89 |
| 10 | 55 | 34 | 55 | 144 |
| 11 | 89 | 55 | 89 | 233 |
| 12 | 144 | 89 | 144 | 377 |

So we see that there will be 377 pairs of rabbits after a year. (I hope it's a big yard!)
Note that our table has Fibonacci numbers all over the place! There ought to be a reason why.
Since the rabbits never die, all of the rabbits alive in month $n-1$ will live on to month $n$. But new rabbits are also born in month $n$. Therefore,
$$\begin{array}{r}
(\text{# of pairs of rabbits in month } n)=(\# \text { of pairs rabbits in month } n-1) \\
+(\# \text { of newborn pairs of rabbits in month } n) .
\end{array}$$

How many pairs of rabbits are born? All adult pairs produce offspring. The adults are precisely those rabbits that were alive two months ago. So we can write
(# of pairs of rabbits in month $n$) = (# of pairs of rabbits in month $n-1$ )
\+ (# of pairs of rabbits in month $n-2$ ).
So if we let $r_{n}$ denote the number of pairs of rabbits in month $n$, we have the equation
$$r_{n}=r_{n-1}+r_{n-2} .$$

That looks like Fibonacci numbers!
We could very easily stumble into a common mistake here.

> **Bogus Solution:** Our above work shows that the number of pairs of rabbits in month $n$ is the $n^{\text {th }}$ Fibonacci number. Therefore, after a year, we get the $12^{\text {th }}$ Fibonacci number $F_{12}$.

This doesn't work because the Fibonacci numbers are defined starting with $F_{1}=F_{2}=1$. Here, we're starting with $r_{0}=1$ and $r_{1}=2$. So our number of pairs of rabbits are the Fibonacci numbers, but they're all shifted. To be exact, $r_{n}=F_{n+2}$. This means that the answer to our rabbit problem is the $14^{\text {th }}$ Fibonacci number, $F_{14}$, which is 377 .

> **Sidenote:** Problem 9.2 is exactly the problem that Fibonacci himself first studied in his work Liber abaci in 1202. One translation of the original problem from Liber abaci reads:
>
> A certain man put a pair of rabbits in a place surrounded on all sides by a wall. How many pairs of rabbits can be produced from that pair in a year if it is supposed that every month each pair begets a new pair which from the second month on becomes productive?
> (Source: MacTutor History of Mathematics)

**Problem 9.3:** How many subsets of $\{1,2, \ldots, n\}$ have no two consecutive integers as elements?

*Solution for Problem 9.3:* One idea might be to do a nasty PIE calculation to compute the number of subsets that do have at least two consecutive elements. But try it for about 5 minutes and you'll see that it's pretty ugly.

Another idea: try some small values of $n$, and look for a pattern.

> **Concept:** When trying to find or prove something for all positive integers $n$, try some small values of $n$, and look for a pattern.

If $n=1$, then there are 2 valid subsets: $\emptyset$ and $\{1\}$. (Don't forget about $\emptyset!$ )
If $n=2$, then there are 3 valid subsets: $\emptyset,\{1\}$, and $\{2\}$.
If $n=3$, then there are 5 valid subsets: $\emptyset,\{1\},\{2\},\{3\}$, and $\{1,3\}$.
If $n=4$, then there are 8 valid subsets: $\emptyset,\{1\},\{2\},\{3\},\{4\},\{1,3\},\{1,4\}$, and $\{2,4\}$.
So far, for $n=1,2,3,4, \ldots$, we have $2,3,5,8 \ldots$-those are Fibonacci numbers!
Let $s_{n}$ denote what we're trying to count: the number of subsets of $\{1,2, \ldots, n\}$ with no two consecutive elements. It sure looks like the $s_{n}$ are the Fibonacci numbers, meaning that we want to try to show that
$$s_{n}=s_{n-1}+s_{n-2}$$
for all $n>2$.
So let's think about it a little bit more carefully. Is there any way that we can build the valid subsets of $\{1,2, \ldots, n\}$ from the valid subsets of $\{1,2, \ldots, n-1\}$ and $\{1,2, \ldots, n-2\}$ ?

Let's go back to our example and list the subsets for $n=2,3,4$ :

| $n$ | Valid subsets of $\{1,2, \ldots, n\}$ |
|-----|--------------------------------------|
| 2 | $\emptyset,\{1\},\{2\}$ |
| 3 | $\emptyset,\{1\},\{2\},\{3\},\{1,3\}$ |
| 4 | $\emptyset,\{1\},\{2\},\{3\},\{4\},\{1,3\},\{1,4\},\{2,4\}$ |

Notice that all of the subsets in the $n=3$ list are also in the $n=4$ list. The leftovers in the $n=4$ list (that aren't in the $n=3$ list) are $\{4\},\{1,4\}$, and $\{2,4\}$. Compare these with the subsets in the $n=2$ list. They're the same subsets, but with a 4 added.

This observation can be generalized to any $n \geq 3$, as follows. Every subset of $\{1,2, \ldots, n\}$ either contains $n$ or doesn't contain $n$. A subset that doesn't contain $n$ is a subset of $\{1,2, \ldots, n-1\}$. A subset that does contain $n$ is not allowed to contain $n-1$ (since it can't contain two consecutive elements), so the remaining elements form a subset of $\{1,2, \ldots, n-2\}$.

Therefore, we've established a 1-1 correspondence:
$$\begin{array}{l}
\left.\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n\} \text { with no } \\
\text { two consecutive elements }
\end{array}\right\} \leftrightarrow\left(\left\{\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n-1\} \text { with } \\
\text { no two consecutive elements }
\end{array}\right\} \cup\left\{\begin{array}{l}
\text { Subsets of }\{1,2, \ldots, n-2\} \text { with } \\
\text { no two consecutive elements }
\end{array}\right\}\right) \text {. }
\end{array}$$

The above correspondence means that
$$s_{n}=s_{n-1}+s_{n-2}$$
for all $n>2$. Look familiar?
Beware! As in Problem 9.2, don't jump to the conclusion that the answer is the $n^{\text {th }}$ Fibonacci number. We still need to check the initial conditions. We already listed the subsets for $n=1$ and $n=2$ and found that $s_{1}=2$ and $s_{2}=3$. Therefore, we see that $s_{n}=F_{n+2}$, so the answer is the $(n+2)^{\text {nd }}$ Fibonacci number.

> **Sidenote:** Since the answers to Problems 9.2 and 9.3 were the same, can you find a natural 1-1 correspondence between
> $$\{\text { Pairs of rabbits after } n \text { months }\} \leftrightarrow\left\{\begin{array}{l}
> \text { Subsets of }\{1,2, \ldots, n\} \text { with no } \\
> \text { two consecutive elements }
> \end{array}\right\} ?$$
>
> The answer is on page 191.

**Problem 9.4:** In how many ways can we tile a $2 \times n$ checkerboard with $n$ tiles of size $1 \times 2$, such that each tile covers exactly two squares? An example with $n=6$ is shown below.

*Solution for Problem 9.4:* As we often do, let's start with a few small examples to get an idea of what the solution might be.

There's only 1 way to tile a $2 \times 1$ board.

There are 2 ways to tile a $2 \times 2$ board.

There are 3 ways to tile a $2 \times 3$ board.

There are 5 ways to tile a $2 \times 4$ board.

Hmmm... the first four values of $n$ give us $1,2,3,5$ possible tilings. So the answer might be the Fibonacci numbers. With this goal in mind, we try to think about how tilings of the $2 \times n$ board can be built from tilings of the $2 \times(n-1)$ and $2 \times(n-2)$ boards.

Suppose $n>2$, and think about how we might place the tile which covers the lower-left square. There are two cases.

Case 1: Place the tile vertically. Then we must tile the remaining $2 \times(n-1)$ board.

Case 2: Place the tile horizontally. Then we must also place a horizontal tile covering the upper-left square (since that's the only way to cover that square). What's left is a $2 \times(n-2)$ board that we must tile.

So we see that
(# of ways to tile a $2 \times n$ board) = (# of ways to tile a $2 \times(n-1)$ board)
\+ (# of ways to tile a $2 \times(n-2)$ board).
If we let $t_{n}$ denote the number of ways to tile a $2 \times n$ board, then we see the familiar equation
$$t_{n}=t_{n-1}+t_{n-2} .$$

Once again, Fibonacci numbers! But as usual, we need to check the initial conditions.
There's only one way to tile a $2 \times 1$ board, so $t_{1}=1$. There are two ways to tile a $2 \times 2$ board (either place both tiles horizontally or both tiles vertically), so $t_{2}=2$.

Since $t_{1}=F_{2}, t_{2}=F_{3}$, and $t_{n}=t_{n-1}+t_{n-2}$, we see that in general, $t_{n}=F_{n+1}$, which is the $(n+1)^{\text {st }}$ Fibonacci number.

The Fibonacci numbers satisfy lots and lots of identities. Here's a fairly simple one:

**Problem 9.5:** Prove that for any $k \geq 1$,
$$F_{1}+F_{3}+F_{5}+\cdots+F_{2 k+1}=F_{2 k+2} .$$

*Solution for Problem 9.5:* Just to convince ourselves that the result is actually true, let's check it for $k=4$ :
$$F_{1}+F_{3}+F_{5}+F_{7}+F_{9}=1+2+5+13+34=55=F_{10} .$$

Let's play with our example and see if we can determine why it works.

> **Concept:** Before tackling the general case of an identity or equation, it often helps to play with a simple example or two, in order to get a feel for what's going on.

If we start collapsing the sum from left-to-right, something interesting happens:
$$\begin{aligned}
1+2+5+13+34 & =3+5+13+34 \\
& =8+13+34 \\
& =21+34 \\
& =55
\end{aligned}$$

Notice that the first terms of each intermediate sum are the "missing" Fibonacci numbers. For example, $3=F_{4}, 8=F_{6}$, and $21=F_{8}$.

Now let's look at the general case. To get the ball rolling, we need to use the fact that $F_{1}=F_{2}=1$. Then the sum collapses, just like in our example.
$$\begin{array}{rrr}
F_{1}+F_{3}+F_{5}+F_{7}+\cdots+F_{2 k+1} & = & F_{2}+F_{3}+F_{5}+F_{7}+\cdots+F_{2 k+1} \\
& = & F_{4}+F_{5}+F_{7}+\cdots+F_{2 k+1} \\
& = & F_{6}+F_{7}+\cdots+F_{2 k+1} \\
& \vdots & \\
& = & F_{2 k}+F_{2 k+1} \\
& = & F_{2 k+2} .
\end{array}$$

We can also prove the result more formally using mathematical induction.
Base case: If $k=1$, then
$$F_{1}+F_{3}=1+2=3=F_{4} .$$

So the result holds for $k=1$.
Inductive step: Assume that the result holds for some positive integer $k$. We will attempt to prove the result for $k+1$ :
$$\begin{aligned}
F_{1}+F_{3}+\cdots+F_{2(k+1)+1} & =\left(F_{1}+F_{3}+\cdots+F_{2 k+1}\right)+F_{2 k+3} \\
& =F_{2 k+2}+F_{2 k+3} \\
& =F_{2 k+4}
\end{aligned}$$
where the last step $F_{2 k+2}+F_{2 k+3}=F_{2 k+4}$ comes from the definition of the Fibonacci numbers.
Therefore, the result is true by induction.
Let's see a more complicated Fibonacci identity.

**Problem 9.6:** Prove that for all positive integers $n \geq 1$,
$$F_{1}^{2}+F_{2}^{2}+\cdots+F_{n}^{2}=F_{n} F_{n+1} .$$

*Solution for Problem 9.6:* There are two basic ways we can approach this: we can try to work algebraically with an induction proof, or we can try to look for a clever counting argument. Let's do the induction proof here.
Base case: If we let $n=1$, we get $F_{1}^{2}=1^{2}=1=(1)(1)=F_{1} F_{2}$, so the base case holds.
Inductive step: Assume that the identity is true for some positive integer $k$. We will write the left side of the identity for $k+1$ :
$$F_{1}^{2}+F_{2}^{2}+\cdots+F_{k}^{2}+F_{k+1}^{2} .$$

All but the final term of this expression can be replaced by $F_{k} F_{k+1}$ using the inductive hypothesis, so we have:
$$F_{1}^{2}+\cdots+F_{k}^{2}+F_{k+1}^{2}=F_{k} F_{k+1}+F_{k+1}^{2} .$$

The right side of the above can be factored as $\left(F_{k}+F_{k+1}\right) F_{k+1}$. And what is that expression inside the parentheses? It's $F_{k}+F_{k+1}$, which by the definition of the Fibonacci numbers is equal to $F_{k+2}$. Therefore the whole expression is simply $F_{k+2} F_{k+1}$, and thus we have proved that
$$F_{1}^{2}+\cdots+F_{k+1}^{2}=F_{k+1} F_{k+2} .$$

Hence, by induction, the result is proved.
Although the algebraic induction proof was relatively straightforward, it didn't really provide any insight into why the identity is true. For a deeper understanding, we can try to find a counting argument that proves the identity. We'll leave this for you as an Exercise.

You'll get a chance to see more Fibonacci identities in the Exercises and Challenge Problems. We'll also revisit identities in general in Chapter 12.

### Exercises

**9.3.1** Norman wishes to buy a can of soda costing 75 cents from a vending machine. He has an unlimited supply of identical nickels (worth 5 cents each) and dimes (worth 10 cents each). In how many different orders can he insert coins into the machine to pay for his soda?

**9.3.2** Three sheets of glass are arranged in parallel. A light ray passes through the top sheet, reflects a number of times between the sheets, and exits the glass. For example, the diagram below shows the possible paths that the ray can take, if it reflects exactly 3 times:

How many different paths can the ray take if it reflects exactly 9 times?

**9.3.3** Suppose you toss a fair coin 10 times. What is the probability that you do not get two heads in a row? Hints: 45, 147

**9.3.4** Prove that $F_{n}$ is a multiple of 3 if and only if $n$ is a multiple of 4 . Hints: 304

**9.3.5** Prove that for any $k \geq 1$,
$$1+F_{2}+F_{4}+F_{6}+\cdots+F_{2 k}=F_{2 k+1}$$

**9.3.6** A subset $S$ of $\{1,2, \ldots, n\}$ is called selfish if $\#(S) \in S$. A selfish subset is called minimal if none of its proper subsets are selfish. Find the number of minimal selfish subsets of $\{1,2, \ldots, n\}$. (Source: Putnam) Hints: 310

**9.3.7\*** Find a counting argument to prove the identity from Problem 9.6. Hints: 142, 199

## 9.4 A Formula for the Fibonacci Numbers

Note: the problems in this section are somewhat algebraically intense and can be a bit abstract. If you are having difficulty with these problems, you may wish to skip ahead to Chapter 10 and then come back to this section after you've learned more about the general theory of recursions.

### Problems

**Problem 9.7:** In this problem, we work out a formula for the Fibonacci numbers.
(a) List the first several Fibonacci numbers, and compute the ratios between successive Fibonacci numbers. Do you notice these ratios approaching a common value?
(b) Suppose that $a_{n}=c^{n}$ satisfies the recursion $a_{n}=a_{n-1}+a_{n-2}$ for some constant $c$. Find the possible values of $c$.
(c) Show that $a_{n}=\lambda_{1} c_{1}^{n}+\lambda_{2} c_{2}^{n}$ satisfies the recursion from part (b), where $c_{1}$ and $c_{2}$ are the values you found in part (b), and $\lambda_{1}$ and $\lambda_{2}$ are arbitrary constants.
(d) Find a formula for the $n^{\text {th }}$ Fibonacci number, by using the known values of $a_{1}$ and $a_{2}$ to solve for $\lambda_{1}$ and $\lambda_{2}$ in part (c).

**Problem 9.8:** Is there a simpler formula for the Fibonacci numbers? (Here, you are allowed to use the nearest integer function: $[x]$ is the integer closest to $x$, so that for example $[1.2]=1$ and $[1.7]=2$. By convention, we always round towards even numbers, so that $[1.5]=[2.5]=2$.)

**Problem 9.9:** Prove that
$$F_{n-1} F_{n+1}-F_{n}^{2}=(-1)^{n}$$
where $F_{n}$ is the $n^{\text {th }}$ Fibonacci number.

As we have seen, the Fibonacci numbers are given by the recursion
$$F_{n}=F_{n-1}+F_{n-2}$$

for all $n>2$, where $F_{1}=1$ and $F_{2}=1$. Although we can now go ahead and list arbitrarily many Fibonacci numbers using this recursion, it's a bit of a pain to calculate, say, the $100^{\text {th }}$ Fibonacci number, because we'd have to list out the first 99 Fibonacci numbers in order to find the $100^{\text {th }}$. It'd be awfully nice if there were just a formula for $F_{n}$ that we could plug $n=100$ into and get the $100^{\text {th }}$ Fibonacci number right away.

The good news is that there is such a formula! The bad news is that, on first glance, it's really messy. Let's work it out.

**Problem 9.7:** Find a formula for $F_{n}$, the $n^{\text {th }}$ Fibonacci number, where $F_{1}=F_{2}=1$ and $F_{n}=F_{n-1}+F_{n-2}$ for all $n>2$.

*Solution for Problem 9.7:* Let's list the first twelve Fibonacci numbers:
$$1,1,2,3,5,8,13,21,34,55,89,144, \ldots$$

Where can we even begin our search for a general formula?
We can start by drawing a graph of the Fibonacci numbers $F_{n}$ as a function of $n$; the graph is shown at the right. Note that the $y$-axis is scaled differently than the $x$-axis, since otherwise the graph wouldn't fit. We see that $F_{n}$ grows fast. Really fast. And the fastest-growing "nice" functions that we know of are exponential functions (hence the phrase "exponential growth"). So our strategy is to suppose that the Fibonacci numbers satisfy an exponential expression, and hope that we get lucky. Looking at the ratio of successive Fibonacci numbers (rounded to three decimal places), we suspect that we will get lucky:

| $n$ | $F_{n} / F_{n-1}$ | Decimal |
|-----|-------------------|---------|
| 2 | $1 / 1$ | 1.000 |
| 3 | $2 / 1$ | 2.000 |
| 4 | $3 / 2$ | 1.500 |
| 5 | $5 / 3$ | 1.667 |
| 6 | $8 / 5$ | 1.600 |
| 7 | $13 / 8$ | 1.625 |
| 8 | $21 / 13$ | 1.615 |
| 9 | $34 / 21$ | 1.619 |
| 10 | $55 / 34$ | 1.618 |
| 11 | $89 / 55$ | 1.618 |
| 12 | $144 / 89$ | 1.618 |

We see that the ratio between consecutive terms of the Fibonacci sequence appears to converge to about 1.618. This means that the Fibonacci sequence appears to converge toward a geometric sequence with ratio about 1.618. Let's see if we can make this statement more precise.

Specifically, we let $a_{n}=c^{n}$ for some unknown constant $c$. If we plug this into our recurrence relation for the Fibonacci numbers, we get
$$a_{n}=a_{n-1}+a_{n-2} \quad \Rightarrow \quad c^{n}=c^{n-1}+c^{n-2} .$$

Since $c \neq 0$ (otherwise it would be a pretty stupid formula), we can divide by $c^{n-2}$ to get $c^{2}=c+1$.
Good, we know how to solve this! If we rewrite it as $c^{2}-c-1=0$, we can use the quadratic formula:
$$c=\frac{1 \pm \sqrt{5}}{2}$$

This gives us two possible candidates for $c$ :
$$c_{1}=\frac{1+\sqrt{5}}{2}, \quad c_{2}=\frac{1-\sqrt{5}}{2} .$$

Note that $c_{1} \approx 1.618$ and $c_{2} \approx-0.618$; in particular, $c_{1}$ seems to match the ratio of consecutive Fibonacci numbers that we found in our earlier experimentation.

How do we know which value, $c_{1}$ or $c_{2}$, to use, or if either one works? Based on our calculations above, we know that $a_{n}=c_{1}^{n}$ and $a_{n}=c_{2}^{n}$ each satisfy the relation $a_{n}=a_{n-1}+a_{n-2}$. Unfortunately, neither satisfies the initial conditions $a_{1}=a_{2}=1$. So how do we fix it?

We observe that any $a_{n}$ of the form
$$a_{n}=\lambda_{1} c_{1}^{n}+\lambda_{2} c_{2}^{n}$$
where $\lambda_{1}$ and $\lambda_{2}$ are constants, satisfies the recurrence relation. ( $\lambda$ is the greek letter lambda, which is often used to represent unknown constants.) To see this, we simply plug it in for $a_{n}, a_{n-1}$, and $a_{n-2}$ in our recurrence relation, and verify that it holds:
$$\begin{aligned}
a_{n}=\lambda_{1} c_{1}^{n}+\lambda_{2} c_{2}^{n} & =\lambda_{1}\left(c_{1}^{n-1}+c_{1}^{n-2}\right)+\lambda_{2}\left(c_{2}^{n-1}+c_{2}^{n-2}\right) \\
& =\lambda_{1} c_{1}^{n-1}+\lambda_{2} c_{2}^{n-1}+\lambda_{1} c_{1}^{n-2}+\lambda_{2} c_{2}^{n-2} \\
& =a_{n-1}+a_{n-2}
\end{aligned}$$

Now we have a plan: use the above expression for $a_{n}$, plug in the initial conditions, and solve for the unknown constants $\lambda_{1}$ and $\lambda_{2}$.
$$\begin{array}{l}
1=\lambda_{1} c_{1}+\lambda_{2} c_{2} \\
1=\lambda_{1} c_{1}^{2}+\lambda_{2} c_{2}^{2}
\end{array}$$
We're going to have to get our hands dirty a bit, and plug in $c_{1}$ and $c_{2}$. Let's clear the denominators while we're at it.
$$\begin{array}{l}
2=\lambda_{1}(1+\sqrt{5})+\lambda_{2}(1-\sqrt{5}) \\
4=\lambda_{1}(1+\sqrt{5})^{2}+\lambda_{2}(1-\sqrt{5})^{2}
\end{array}$$
This is probably not the prettiest system of linear equations that you've ever seen.

Fortunately, we can use a little trick to make the system a lot simpler. Extend the sequence back one term to $a_{0}=0$. Then our system (using $a_{0}=0$ and $a_{1}=1$ ) becomes:
$$\begin{array}{l}
0=\lambda_{1} c_{1}^{0}+\lambda_{2} c_{2}^{0}, \\
1=\lambda_{1} c_{1}+\lambda_{2} c_{2} .
\end{array}$$

This simplifies quite nicely:
$$\begin{array}{l}
0=\lambda_{1}+\lambda_{2} \\
2=\lambda_{1}(1+\sqrt{5})+\lambda_{2}(1-\sqrt{5})
\end{array}$$

Now solving is fairly simple (if a bit messy). The first equation gives us $\lambda_{2}=-\lambda_{1}$, and substituting this into the second equation gives:
$$2=\lambda_{1}(-(1-\sqrt{5})+(1+\sqrt{5})) .$$

This simplifies to
$$\lambda_{1}=\frac{2}{2 \sqrt{5}}=\frac{1}{\sqrt{5}} .$$

Then plugging $\lambda_{1}$ back into $0=\lambda_{1}+\lambda_{2}$, we see that
$$\lambda_{2}=-\frac{1}{\sqrt{5}}$$

Thus we conclude that
$$a_{n}=\frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n}-\frac{1}{\sqrt{5}}\left(\frac{1-\sqrt{5}}{2}\right)^{n} .$$

We can make it a little bit nicer by factoring, and we leave it in the final (relatively) nice form:
$$a_{n}=\frac{(1+\sqrt{5})^{n}-(1-\sqrt{5})^{n}}{2^{n} \sqrt{5}}$$

> **Important:** A closed formula for the $n^{\text {th}}$ Fibonacci number $F_{n}$ is
> $$F_{n}=\frac{(1+\sqrt{5})^{n}-(1-\sqrt{5})^{n}}{2^{n} \sqrt{5}}$$

This formula is known as Binet's formula for the Fibonacci numbers, as it was derived by the French mathematician Jacques Binet in the mid-1800s (although it was certainly known earlier).

For example, let's compute $F_{4}$ and verify that indeed we get $F_{4}=3$. If nothing else, this is good practice in using the Binomial Theorem.
$$F_{4}=\frac{(1+\sqrt{5})^{4}-(1-\sqrt{5})^{4}}{2^{4} \sqrt{5}}=\frac{(1+4 \sqrt{5}+30+20 \sqrt{5}+25)-(1-4 \sqrt{5}+30-20 \sqrt{5}+25)}{16 \sqrt{5}}=\frac{48 \sqrt{5}}{16 \sqrt{5}}=3 .$$

This may seem like a very weird formula for a sequence of integers! But look carefully-when we compute $(1+\sqrt{5})^{n}-(1-\sqrt{5})^{n}$, all of the terms without a $\sqrt{5}$ in them will cancel out. All of the remaining terms will have odd powers of $\sqrt{5}$, and thus the $\sqrt{5}$ will get cancelled out by the $\sqrt{5}$ term in the denominator, so the final result will be a rational number. (In fact it will be an integer: the powers of 2 will cancel as well, though this is a lot harder to see right away.)

Although this formula works, it's still messy to use in practice. For example, this is not a practical way to calculate $F_{100}$, since we'd have to expand $(1+\sqrt{5})^{100}$.

**Problem 9.8:** Is there a simpler formula for the Fibonacci numbers?

*Solution for Problem 9.8:* To be fair, the answer to this question depends on how we define "simpler."
Let's take another look at our formula:
$$F_{n}=\frac{(1+\sqrt{5})^{n}-(1-\sqrt{5})^{n}}{2^{n} \sqrt{5}}$$

Let's break it up into its two terms, and put the $2^{n}$ inside the numerator's exponentials:
$$F_{n}=\frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n}-\frac{1}{\sqrt{5}}\left(\frac{1-\sqrt{5}}{2}\right)^{n} .$$

Take a look at that second term. Not very big, is it?
In fact, when $n$ is large, it's really tiny. Note that $1-\sqrt{5} \approx-1.24$, so $(1-\sqrt{5}) / 2 \approx-0.62$. So we have
$$F_{n} \approx \frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n}-\frac{(-0.62)^{n}}{\sqrt{5}}$$

That term at the right end always has absolute value less than $\frac{1}{2}$. It becomes much, much smaller as $n$ gets larger, but even where $n=0$, it's $1 / \sqrt{5} \approx 0.447$, which is less than 0.5 . Therefore, since we know that $F_{n}$ is an integer, we conclude that $F_{n}$ is whatever integer is closest to the left term, since the right term only alters the value of $F_{n}$ by at most $\frac{1}{2}$.

Let $[x]$ denote the closest integer to $x$. For example, $[1.2]=1$ and $[1.8]=2$. Basically, we're rounding $x$ to the nearest integer. By convention, if we're exactly halfway between two integers, we always round towards the even integer, so for example, $[1.5]=[2.5]=2$. Then our discussion above establishes that
$$F_{n}=\left[\frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n}\right] .$$

> **Sidenote:**
> The number
> $$\phi=\frac{1+\sqrt{5}}{2} \approx 1.618033989 \ldots$$
> is a very special irrational number. It is called the golden ratio.
>
> The golden ratio has many nice properties. We have already seen that the golden ratio is the value to which the ratio of successive Fibonacci numbers converges, and also that the golden ratio is the positive root of $x^{2}-x-1=0$. The golden ratio can also be written as a continued square root as
> $$\phi=\sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+\cdots}}}}$$
>
> The ratio is also considered an aesthetically-pleasing ratio of side lengths of a rectangle. For example, the large rectangle at right has the golden ratio as the ratio of its side lengths. Note how we can remove a square from the figure and get a smaller rectangle with the same ratio of side lengths-can you figure out why this is so?

Now at least we can use our calculator or computer to determine large Fibonacci numbers. But the real power of Binet's formula is in proving some nontrivial Fibonacci identities. Here's an example:

**Problem 9.9:** Prove that
$$F_{n-1} F_{n+1}-F_{n}^{2}=(-1)^{n}$$
where $F_{n}$ is the $n^{\text {th }}$ Fibonacci number.

*Solution for Problem 9.9:* In order to simplify the algebra, let $v=1+\sqrt{5}$ and $\mu=1-\sqrt{5}$.

> **Concept:** If the same "ugly" term pops up a lot in an algebraic computation, consider assigning it a variable name so that your algebra is easier to read and write.

Now we can calculate:
$$\begin{aligned}
F_{n-1} F_{n+1}-F_{n}^{2} & =\left(\frac{v^{n-1}-\mu^{n-1}}{2^{n-1} \sqrt{5}}\right)\left(\frac{v^{n+1}-\mu^{n+1}}{2^{n+1} \sqrt{5}}\right)-\left(\frac{v^{n}-\mu^{n}}{2^{n} \sqrt{5}}\right)^{2} \\
& =\frac{\left(v^{n-1}-\mu^{n-1}\right)\left(v^{n+1}-\mu^{n+1}\right)-\left(v^{n}-\mu^{n}\right)^{2}}{2^{2 n}(5)} \\
& =\frac{\left(v^{2 n}-v^{n-1} \mu^{n+1}-v^{n+1} \mu^{n-1}+\mu^{2 n}\right)-\left(v^{2 n}-2 v^{n} \mu^{n}+\mu^{2 n}\right)}{2^{2 n}(5)} \\
& =\frac{v^{n-1} \mu^{n-1}\left(-v^{2}-\mu^{2}+2 v \mu\right)}{2^{2 n}(5)} \\
& =-\frac{v^{n-1} \mu^{n-1}(v-\mu)^{2}}{2^{2 n}(5)} .
\end{aligned}$$

Now we note that $v \mu=(1+\sqrt{5})(1-\sqrt{5})=-4$ and $v-\mu=(1+\sqrt{5})-(1-\sqrt{5})=2 \sqrt{5}$. Therefore we have
$$F_{n-1} F_{n+1}-F_{n}^{2}=-\frac{(-4)^{n-1}(2 \sqrt{5})^{2}}{2^{2 n}(5)}=-\frac{(-1)^{n-1} 2^{2 n}(5)}{2^{2 n}(5)}=(-1)^{n} .$$

Certainly we could prove this identity via other means, but the formula makes it fairly straightforward to prove by just plugging-and-chugging with algebra.

### Exercises

**9.4.1** Prove, using Binet's formula, that for all $n>0$,
$$F_{2 n-1}=F_{n}^{2}+F_{n-1}^{2}$$

**9.4.2** Use Binet's formula to find a simple approximation for the number of digits in $F_{n}$.

**9.4.3\*** The Lucas numbers are defined by $L_{0}=2, L_{1}=1$, and $L_{n}=L_{n-1}+L_{n-2}$ for all $n \geq 2$.
(a) Use a procedure similar to Problem 9.7 to find a formula for $L_{n}$.
(b) Prove that $F_{2 n}=F_{n} L_{n}$. Hints: 269
(c) Prove that $L_{n}^{2}-5 F_{n}^{2}=4(-1)^{n}$. Hints: 20
(d)\* Prove that, except for 1, 2, and 3, no positive integer is both a Fibonacci number and a Lucas number. Hints: 51, 267

## 9.5 Summary

- The Fibonacci numbers are the sequence of numbers
$$0,1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987, \ldots$$
where each number (after the first two) is the sum of the two preceding numbers.
- A more formal definition is that $F_{0}=0, F_{1}=1$, and $F_{n}=F_{n-1}+F_{n-2}$ for all $n \geq 2$.
- Many counting problems have the Fibonacci numbers as their solution, especially those in which we can relate a problem of size $n$ to the same problem of size $n-1$ and $n-2$.
- A closed formula for the $n^{\text {th }}$ Fibonacci number $F_{n}$ is
$$F_{n}=\frac{(1+\sqrt{5})^{n}-(1-\sqrt{5})^{n}}{2^{n} \sqrt{5}}$$

Here are some general problem-solving concepts:

> **Concept:** When trying to find or prove something for all positive integers $n$, try some small values of $n$, and look for a pattern.

> **Concept:** Before tackling the general case of an identity or equation, it often helps to play with a simple example or two, in order to get a feel for what's going on.

> **Concept:** If the same "ugly" term pops up a lot in an algebraic computation, consider assigning it a variable name so that your algebra is easier to read and write.

## Review Problems

**9.10** The parking lot outside our building has 12 parking spaces. Compact cars can easily fit within a single space, but SUVs take up 2 spaces. In how many different ways can the lot be filled?

**9.11** For any positive integer $n$, determine the number of ordered sums of positive integers greater than 1 summing to $n$. (For example, if $n=6$, then the sums are $6,4+2,2+4,3+3$, and $2+2+2$.)

**9.12**
(a) Fourteen people sit in a row of 14 chairs, one person per chair. At the sound of a bell, they all are allowed to change seats, but each person is permitted to move no farther than one seat from her original chair. Each person is not required to move, and there must be one person per chair in the rearrangement. The bell sounds; how many rearrangements can the people form?
(b) What is the answer if the 14 people are sitting in chairs around a round table?

**9.13** On the planet Venus, female Venusians have a mother and a father, but male Venusians have only a mother. For any positive integer $n$, how many $n$-generation ancestors does a male Venusian have? (1-generation ancestors are parents, 2-generation ancestors are grandparents, 3-generation ancestors are great grandparents, and so on.)

**9.14** Prove that for any $k \geq 1$,
$$F_{1}+F_{2}+F_{3}+F_{4}+\cdots+F_{k}=F_{k+2}-1 .$$

**9.15** How many $n$-digit base- 4 numbers are there that start with the digit 3 and in which each digit is exactly one more or one less than the previous digit? (For example, 321010121 is such a 9 -digit number.)

**9.16** How many paths are there from hex $A$ to hex $B$ in the diagram below, if each step of a path must be to a hex immediately adjacent on the right? (A sample such path is shown.)

## Challenge Problems

**9.17** A large elementary school class goes on a field trip to see a play. The front row of the theater has 11 seats. No boy wants to sit between 2 girls (or sit at the end of the row next to a girl) and no girl wants to sit between 2 boys (or sit at the end of the row next to a boy). In how many ways can the row of seats be assigned to boys and girls? Hints: 251

**9.18** In Problem 9.1, we saw using casework that the answer to the 10-stair problem was
$$\binom{10}{0}+\binom{9}{1}+\binom{8}{2}+\binom{7}{3}+\binom{6}{4}+\binom{5}{5}=89,$$
and that this was also equal to the Fibonacci number $F_{11}$. Can you generalize and prove this result? Hints: 156

**9.19** Simplify the product
$$\prod_{k=2}^{100}\left(\frac{F_{k}}{F_{k-1}}-\frac{F_{k}}{F_{k+1}}\right) .$$

(Source: Mandelbrot) Hints: 23

**9.20** Find the value of the infinite sum
$$\frac{1}{3}+\frac{1}{9}+\frac{2}{27}+\cdots+\frac{F_{n}}{3^{n}}+\cdots$$

(Source: Mandelbrot) Hints: 188

**9.21** For any nonnegative real number $x$, let $\langle x\rangle$ denote the fractional part of $x$; that is, $\langle x\rangle=x-\lfloor x\rfloor$, where $\lfloor x\rfloor$ denotes the greatest integer less than or equal to $x$. Suppose that $a$ is a positive real number with $2<a^{2}<3$ such that $\left\langle a^{-1}\right\rangle=\left\langle a^{2}\right\rangle$. Find $a^{12}-144 a^{-1}$. (Source: AIME) Hints: 213, 35

> **Sidenote:** Recall the problem on page 179. The answer is that a subset of $\{1,2, \ldots, n\}$ represents a particular pair's "family tree." For example, if $n=12$ and the subset is $\{2,4,7,11\}$, then the pair corresponding to this subset was born in month 11, its parents were born in month 7 , its grandparents were born in month 4 , and its great grandparents were born in month 2 (to the original pair). Note that, in particular, the subset $\emptyset$ corresponds to the original pair of rabbits. We leave it to you to fill in the missing details of this correspondence, and also to determine why the condition "no two consecutive elements" on the subset is necessary.
