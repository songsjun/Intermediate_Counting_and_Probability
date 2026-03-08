# Chapter 14: Generating Functions

> You must try to generate happiness within yourself. -Ernie Banks

## 14.1 Introduction

In this chapter, we will explore a really clever algebraic device called a generating function. Generating functions allow us to use powerful algebra techniques to approach difficult counting problems.

Suppose that $a_{0}, a_{1}, a_{2}, \ldots$ is a sequence of numbers. The corresponding generating function for this sequence is
$$f(x)=a_{0}+a_{1} x+a_{2} x^{2}+\cdots$$

That is, the coefficient of $x^{k}$ is the $k^{\text {th}}$ term of the sequence. If the original sequence is finite, then the generating function is just a polynomial, but if the sequence is infinite, then the generating function is an "infinite polynomial," more properly called a power series.

Here are some examples:
- If our sequence is $1,5,10,10,5,1$-Row 5 of Pascal's Triangle-then the generating function is
$$1+5 x+10 x^{2}+10 x^{3}+5 x^{4}+x^{5}$$

Notice that this is equal to $(1+x)^{5}$ by the Binomial Theorem. We will explore this relationship further in Section 14.3.
- If our sequence is $1,3,6,10,15,21, \ldots$-the triangular numbers, or all the numbers of the form $\binom{k}{2}$ for positive integers $k \geq 2$-then the generating function is
$$1+3 x+6 x^{2}+10 x^{3}+15 x^{4}+21 x^{5}+\cdots$$

In Section 14.4, we will see some special properties of this generating function.
- If our sequence is $0,1,1,2,3,5,8,13, \ldots$-the Fibonacci numbers-then the generating function is
$$x+x^{2}+2 x^{3}+3 x^{4}+5 x^{5}+8 x^{6}+13 x^{7}+\cdots$$

Although this seems rather unwieldy, it does have some nice properties, as we will see in Section 14.6 ★.

## 14.2 Basic Examples of Generating Functions

### Problems

All of these problems are easy. But try to answer them using generating functions.

**Problem 14.1:** There are three urns on a table. One has 2 red balls, one has 2 green balls, and one has 3 blue balls. Balls of the same color are indistinguishable. In how many ways can I choose 4 balls from the urns?

**Problem 14.2:** As in Problem 14.1, there are three urns on a table: one has 2 red balls, one has 2 green balls, and one has 3 blue balls. But now, all balls of the same color are distinguishable. In how many ways can I choose 4 balls from the urns?

**Problem 14.3:** In how many ways can we roll three dice to get the sum 9?

**Problem 14.4:** Suppose that I have two weird dice. One die has on three faces, on two faces, and on the sixth face. The other die has on one face, $\square$ on four faces, and six face. If I roll both dice, what is the probability that the sum is greater than 6 but less than 10?

In simple problems in which we are counting the number of possibilities across multiple events, generating functions provide a useful tool for keeping track of the number of possibilities. This is a bit confusing to describe in words, but hopefully some simple examples will illustrate what we mean.

All of the problems in this section are very easy, and could easily be solved by counting methods that you already know. We present them here for illustrative purposes, as their transparency hopefully makes it easy to see what's going on when we introduce generating functions.

**Problem 14.1:** There are three urns on a table. One has 2 red balls, one has 2 green balls, and one has 3 blue balls. Balls of the same color are indistinguishable. In how many ways can I choose 4 balls from the urns?

*Solution for Problem 14.1:* Of course, this is an easy problem, and we could just list the possibilities in a table, as shown on the next page:

> Extra! Not without a shudder may the human hand reach into the mysterious urn of destiny.
> - Friedrich Schiller

But, by definition, $F_{k}=F_{k-1}+F_{k-2}$, so the above coefficient is zero! Hence, we have shown that
$$g(x)=\left(1-x-x^{2}\right)\left(x+x^{2}+2 x^{3}+3 x^{4}+5 x^{5}+8 x^{6}+\cdots\right)=x$$
and thus the generating function for the Fibonacci numbers is $x /\left(1-x-x^{2}\right)$.
This generating function may seem like just an amusing curiosity, but it does have some uses; in particular, it gives us another way to find the closed-form formula for the Fibonacci numbers.

**Problem 14.18:** Use the generating function from the previous problem to find a closed-form formula for the $n^{\text {th }}$ Fibonacci number.

*Solution for Problem 14.18:* We really don't know how to deal with a quadratic term in the denominator But we do have some confidence with our ability to deal with linear terms. So let's start by factoring the denominator into linear factors. By the quadratic formula, the roots of $x^{2}+x-1$ are
$$\frac{-1 \pm \sqrt{5}}{2} .$$

Let's call these roots $\phi_{1}=(-1+\sqrt{5}) / 2$ and $\phi_{2}=(-1-\sqrt{5}) / 2$. Then we can rewrite our generating function as
$$\frac{\boldsymbol{x}}{1-x-x^{2}}=\frac{-\boldsymbol{x}}{x^{2}+x-1}=\frac{-\boldsymbol{x}}{\left(\phi_{1}-x\right)\left(\phi_{2}-x\right)} .$$
(Note that the numerator is now $-x$, so that the sign of the expression is correct.)
We're still not terribly happy with the way this looks. What we'd really like is to break up this function into the form
$$x\left(\frac{A}{\phi_{1}-x}+\frac{B}{\phi_{2}-x}\right),$$
where $A$ and $B$ are some constants. This is called a partial fraction decomposition. To determine what $A$ and $B$ should be, we place the sum of the fractions over a common denominator:
$$\frac{A}{\phi_{1}-x}+\frac{B}{\phi_{2}-x}=\frac{A\left(\phi_{2}-x\right)+B\left(\phi_{1}-x\right)}{\left(\phi_{1}-x\right)\left(\phi_{2}-x\right)} .$$

Since we want this to match our original generating function, we must have
$$A\left(\phi_{2}-x\right)+B\left(\phi_{1}-x\right)=-1 .$$

This gives us a system of linear equations in $A$ and $B$:
$$\begin{aligned}
\phi_{2} A+\phi_{1} B & =-1, \\
-A-B & =0 .
\end{aligned}$$

By the second equation, we see that $B=-A$, and plugging this into the first equation gives us
$$\left(\phi_{2}-\phi_{1}\right) A=-1$$

So $A=1 /\left(\phi_{1}-\phi_{2}\right)$. Remembering the definitions of $\phi_{1}$ and $\phi_{2}$, we see that $\phi_{1}-\phi_{2}=\sqrt{5}$, so $A=1 / \sqrt{5}$.

Therefore, our generating function for the Fibonacci numbers can be written as
$$\frac{x}{\sqrt{5}}\left(\frac{1}{\phi_{1}-x}-\frac{1}{\phi_{2}-x}\right) .$$

For any constant $a$, note that
$$\begin{aligned}
\frac{1}{\alpha-x} & =\frac{1 / \alpha}{1-x / \alpha} \\
& =\frac{1}{\alpha}\left(1+\frac{x}{\alpha}+\frac{x^{2}}{\alpha^{2}}+\cdots\right) \\
& =\frac{1}{\alpha}+\frac{1}{\alpha^{2}} x+\frac{1}{\alpha^{3}} x^{2}+\cdots
\end{aligned}$$

In particular, the coefficient of $x^{n}$ in $1 /(\alpha-x)$ is $1 / \alpha^{n+1}$. Therefore, the coefficient of $x^{n}$ in our generating function, which is the $n^{\text {th }}$ Fibonacci number, is
$$\frac{1}{\sqrt{5}}\left(\left(\frac{1}{\phi_{1}}\right)^{n}-\left(\frac{1}{\phi_{2}}\right)^{n}\right) .$$

With a little algebraic manipulation, we can simplify this to
$$\frac{1}{\sqrt{5}}\left(\left(\frac{1+\sqrt{5}}{2}\right)^{n}-\left(\frac{1-\sqrt{5}}{2}\right)^{n}\right),$$
which is exactly Binet's Formula (as we first saw in Section 9.4).

## 14.7 Summary

- Generating functions allow us to use algebraic techniques to solve a variety of counting problems.
- A generating function is an polynomial of the form
$$f(x)=a_{0}+a_{1} x+a_{2} x^{2}+\cdots$$

We think of the coefficient $a_{k}$ of $x^{k}$ as counting something that depends on a parameter $k$.
- For simple problems, generating functions give us a convenient way of keeping track of a lot of information at once. Another way to think of this is that generating functions allow us to do casework by doing all of the cases at once.
- Often the key step in using generating functions is finding the most efficient algebraic way to compute the coefficient(s) that you need.
- One of the most commonly-used generating functions is for distributions of indistinguishable items. This function is $\frac{1}{(1-x)^{n}}$, and the coefficient of $x^{k}$ in $\frac{1}{(1-x)^{n}}$ is $\binom{n-1+k}{k}$, which counts the number of ways to distribute $k$ items into $n$ boxes (where some box(es) may remain empty).
- Many distribution problems with ugly-looking casework can be solved much more simply by using generating functions.

> Important: Generating functions are very valuable for problems involving partitions. The generating function for the number of partitions of a positive integer $n$ is
> $$\left(1+x+x^{2}+\cdots\right)\left(1+x^{2}+x^{4}+\cdots\right)\left(1+x^{3}+x^{6}+\cdots\right) \cdots=\frac{1}{(1-x)\left(1-x^{2}\right)\left(1-x^{3}\right) \cdots}=\prod_{k=1}^{\infty} \frac{1}{1-x^{k}}$$

- The generating function for the Fibonacci numbers is
$$f(x)=\frac{x}{1-x-x^{2}}$$
and we can use this as another method for proving Binet's Formula.

## Review Problems

**Problem 14.19:** Find the coefficient of $x^{10}$ in the expansion of each of the following:
(a) $\frac{1}{1-x}$
(b) $\frac{1}{1-x^{2}}$
(c) $\frac{1}{(1-x)^{2}}$
(d) $\left(1+x^{5}\right)^{5}$
(e) $\left(1+x+x^{2}+x^{3}+x^{4}+x^{5}+x^{6}\right)^{6}$
(f) $\frac{1}{\left(1-x^{2}\right)^{3}}$

**Problem 14.20:** Find the number of ways to place 25 people into three rooms with at least 1 person in each room. (Solve using generating functions.)

**Problem 14.21:** How many ways are there to distribute eight identical toys among four children if the first child gets at least two toys? (Solve using generating functions.)

**Problem 14.22:** Find the generating function for the number of ways to give $n$ cents change using U.S. pennies, Canadian pennies, British pennies, U.S. nickels, and Canadian nickels. (Assume each "penny" is worth 1 cent and each "nickel" is worth 5 cents, regardless of the country of origin.)

**Problem 14.23:** Three of my friends and I are going to split the bill for dinner. Sara and I will each contribute an odd number of dollars, while Krishna contributes a number of dollars that is a multiple of 3. Shyster will either contribute nothing, or steal one or two dollars. In how many ways can we pay a $\$ 30$ bill?

**Problem 14.24:** I have a bowl with 31 candies. Ten of the candies are indistinguishable and the other 21 are all different (and different from the first 10). In how many ways can I choose 10 of the candies?

**Problem 14.25:** Superman has super-strength and can carry any number of boulders, but insists on carrying an odd number. Batman can carry up to 40 boulders. Mighty Mouse can only carry up to 2 boulders. Batman or Mighty Mouse might go empty-handed.
(a) How many ways can the three distribute exactly 37 boulders to carry?
(b) How many ways can the three distribute exactly 87 boulders to carry?

**Problem 14.26:** How many solutions in positive integers are there to the equation $y_{1}+y_{2}+y_{3}+y_{4}=30$ such that no $y_{i}$ is greater than 12?

**Problem 14.27:** The expression
$$(x+y+z)^{2006}+(x-y-z)^{2006}$$
is simplified by expanding it and combining like terms. How many terms are in the simplified expression? (Source: AMC)

## Challenge Problems

**Problem 14.28:** Compute
$$\sum_{k=0}^{\infty} k\left(\frac{1}{3}\right)^{k}$$
using generating functions. Hints: 48, 234

**Problem 14.29:** Define $Q(n, k)$ to be the coefficient of $x^{k}$ in the expansion of $\left(1+x+x^{2}+x^{3}\right)^{n}$. Prove that
$$Q(n, k)=\sum_{j=0}^{k}\binom{n}{j}\binom{n}{k-2 j}$$
where $\left({ }_{r}^{n}\right)=0$ if $r<0$. (Source: Putnam) Hints: 21

**Problem 14.30:** ★ We can generalize the Binomial Theorem to negative powers. Specifically, for any positive integer $n$, we can write
$$(x+y)^{-n}=a_{0} x^{-n}+a_{1} x^{-(n+1)} y+a_{2} x^{-(n+2)} y^{2}+\cdots$$
for some coefficients $a_{k}$, provided that $\left|\frac{y}{x}\right|<1$.
(a) Prove that $a_{k}=(-1)^{k}\binom{n+k-1}{k}$. Hints: 77, 50
(b) Explain why it makes sense to write $a_{k}=\binom{-n}{k}$. Hints: 18

**Problem 14.31:** \* Let $k$ be a positive integer. Prove that there are exactly $k$ ordered pairs $(x, y)$ of nonnegative integers that satisfy any one of the following equations:
$$\begin{aligned}
x+3 y & =2 k-1, \\
3 x+5 y & =2 k-3, \\
\vdots & \\
(2 k-1) x+(2 k+1) y & =1 .
\end{aligned}$$
(For example, if $k=2$, then there are two equations $x+3 y=3$ and $3 x+5 y=1$. The 2 solutions are $(3,0)$ and ( 0,1 ); notice that both satisfy the first equation.) (Source: Mandelbrot) Hints: 184, 86, 111

**Problem 14.32:** \*
(a) Let
$$C(x)=1+x+2 x^{2}+5 x^{3}+14 x^{4}+\cdots$$
be the generating function for the Catalan numbers, so that the coefficient of $x^{n}$ is the $n^{\text {th }}$ Catalan number. Prove that
$$C(x)=x(C(x))^{2}+1 .$$

Hints: 230
(b) ★ Prove that
$$C(x)=\frac{1-\sqrt{1-4 x}}{2 x} .$$

Hints: 100
(c) ★ Use the generating function to find a closed-form formula for the $n^{\text {th }}$ Catalan number. Hints: 324
