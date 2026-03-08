# Chapter 12: Combinatorial Identities

> To be idle requires a strong sense of personal identity. - Robert Louis Stevenson

## 12.1 Introduction

In this chapter, we'll discuss some combinatorial identities. Some of these you should hopefully already know, and some will likely be new to you.

While more advanced combinatorial identities aren't often used to solve problems (though sometimes they are the problem), mastering combinatorial identities requires a very deep understanding of what our common counting tools really mean in terms of counting, as opposed to just knowing how to perform computations.

## 12.2 Basic Identities

### Problems

**Problem 12.1:** Prove that
$$\binom{n}{r}=\binom{n}{n-r}$$
for all positive integers $n$ and all integers $0 \leq r \leq n$, using
(a) a committee-forming argument: show that both sides of the identity count, in a different way, the number of ways to form a certain committee.
(b) a block-walking argument: show that both sides count, in a different way, the number of certain types of paths on a grid or on Pascal's Triangle.
(c) algebra: show algebraically that the two sides are equal.

"smaller" in some sense. We notice that $\frac{8}{b}$ is a factor of every term on the LHS, so let's factor it out of the LHS:
$$\frac{a}{b}\left(1+\frac{(a-1)}{(b-1)}+\cdots+\frac{(a-1)!}{(b-1) \cdots(b-a+1)}\right) .$$

Aha-if we can use an inductive hypothesis on everything in the parenthesis except for the initial 1, we see that this would be equal to:
$$\begin{aligned}
\frac{a}{b}\left(1+\frac{a-1}{(b-1)-(a-1)+1}\right) & =\frac{a}{b}\left(1+\frac{a-1}{b-a+1}\right) \\
& =\frac{a}{b}\left(\frac{b}{b-a+1}\right) \\
& =\frac{a}{b-a+1}
\end{aligned}$$

Now we see how to proceed. We can prove the identity by induction on $b$. The base case is when $b=1$, in which case we must have $a=1$ and the identity is simply $\frac{1}{1}=\frac{1}{1-1+1}=1$, which is true. And we have proven the inductive step above: if the identity is true for $b-1$, then it is true for $b$ as well. Thus the identity holds for all $b$.

> WARNING!! Don't stop here! Don't forget to answer the original question!

Finally, we can answer the question as originally posed: we have $a=19$ and $b=99$, so by the identity that we have just proven, the answer is $\frac{19}{99-19+1}=\frac{19}{81}$.

> Concept: The type of exploration that we did in Problem 12.10 is very much how an actual mathematician goes about problem solving. We started with an ugly expression, we tried some simple examples, and this led to a nice conjecture. But further exploration-in particular, exploration of the extreme cases-quickly shot this conjecture down. More systematic exploration led us to a more accurate conjecture that fit all of the cases that we had examined. Then, with a goal in sight, we were able to fashion a proof.

## 12.3 Exercises

12.3.1 Prove the following:
$$\binom{\binom{n}{2}}{2}=3\binom{n+1}{4}$$
(a) Algebraically.
(b) ★ With a counting argument. Hints: 334, 134

12.3.2 Find a counting argument to prove that $1 \times 1!+2 \times 2!+3 \times 3!+\cdots+n \times n!=(n+1)!-1$. Hints: 63

12.3.3 Evaluate
$$17\binom{20}{0}+16\binom{20}{1}+15\binom{20}{2}+\cdots+0\binom{20}{17}+(-1)\binom{20}{18}+(-2)\binom{20}{19}+(-3)\binom{20}{20} .$$

12.3.4 Explain why Vandermonde's identity is still valid even if $r>m$ or $r>n$.

12.3.5 ★ During our exploration of the example where $\boldsymbol{a}=\mathbf{4}$ in our solution to Problem 12.10, we saw the following sums (for $b=6$ and $b=7$):
$$\begin{array}{l}
\frac{4}{6}+\frac{12}{30}+\frac{24}{120}+\frac{24}{360}=\frac{2}{3}+\frac{2}{5}+\frac{1}{5}+\frac{1}{15}=\frac{4}{3} \\
\frac{4}{7}+\frac{12}{42}+\frac{24}{210}+\frac{24}{840}=\frac{4}{7}+\frac{2}{7}+\frac{4}{35}+\frac{1}{35}=1=\frac{4}{4}
\end{array}$$

If we had written these fractions over a common denominator, we would have seen the following:
$$\begin{array}{l}
\frac{4}{6}+\frac{12}{30}+\frac{24}{120}+\frac{24}{360}=\frac{2}{3}+\frac{2}{5}+\frac{1}{5}+\frac{1}{15}=\frac{10+6+3+1}{15} \\
\frac{4}{7}+\frac{12}{42}+\frac{24}{210}+\frac{24}{840}=\frac{4}{7}+\frac{2}{7}+\frac{4}{35}+\frac{1}{35}=\frac{20+10+4+1}{35}
\end{array}$$
(a) Look in Pascal's Triangle for the terms in the numerators and the (common) denominators of the last fractions in each row above. Use a combinatorial identity to simplify the sums in the numerators. Hints: 189
(b) Generalize this for arbitrary $a$ and $b$, and use this to present another solution to the problem.

## 12.4 Summary

> There are three general methods for proving combinatorial identities:
> 1. Algebra
> 2. A block-walking argument
> 3. A committee-forming argument

One or more of these methods (especially algebra) may also involve mathematical induction.
- When trying to prove identities by committee-forming arguments:
  - Usually try to find a counting explanation for the simpler side first.
  - A single coefficient of the form $\left({ }_{r}^{n}\right)$ means that a good place to start is choosing $r$ items from a set of $n$ items.
  - A sum of coefficients may mean trying a casework argument.
- The identities from Section 12.2 in Problems 12.1-12.6 are the most common, and you should be familiar with all of them.
- Use identities that you already know to prove new identities.

Also remember these important problem-solving techniques:

> Concept: Experiment with small values to try to see a pattern. Look to write numbers in terms of binomial coefficients.

> Concept: In expressions that include big numbers, often it is easier to consider a more general form of the expression, in which we replace the big numbers with variables. Then, once we've simplified the general expression, we can simply plug in our big numbers in place of the variables to get our answer.

> Concept: Don't jump to conclusions. Check lots of different types of examples until you're fairly sure about your conjectures, then try to prove them. There are few things more frustrating than expending a lot of energy trying to prove things that aren't true.

## Review Problems

**Problem 12.11:** Find a closed-form expression for
$$\sum_{k=0}^{n}\binom{n}{k}\binom{m}{k} .$$

**Problem 12.12:** Show that
$$\sum_{k=1}^{n}\binom{n}{k}\binom{n}{k-1}=\binom{2 n}{n-1} .$$

**Problem 12.13:** Prove that
$$(n-r)\binom{n}{r}=n\binom{n-1}{r}$$
(a) using a counting argument.
(b) using algebra.

**Problem 12.14:** Prove that
$$\binom{n}{1}+6\binom{n}{2}+6\binom{n}{3}=n^{3}$$
(a) using algebra.
(b) using a counting argument.

**Problem 12.15:** Prove that for any positive integers $p$ and $q$,
$$\binom{q+2}{2}\binom{p}{0}+\binom{q+1}{1}\binom{p+1}{1}+\binom{q}{0}\binom{p+2}{2}=\binom{p+q+3}{2} .$$
(Source: Mandelbrot)

**Problem 12.16:** Find a closed-form expression for
$$\sum_{i=0}^{\left\lfloor\frac{1}{2}\right\rfloor}\binom{n}{i},$$
where $\lfloor x\rfloor$ is the greatest integer less than or equal to $x$.

## Challenge Problems

**Problem 12.17:** The geometric mean of a set of $n$ positive numbers is the positive $n^{\text {th }}$ root of the product of the $n$ numbers. Consider each non-empty subset of the set $\left\{a_{1}, a_{2}, \ldots, a_{n}\right\}$, where all the $a_{i}$ are positive. Suppose we take the geometric mean of each of these subsets. Then we take the geometric mean of these geometric means. Show that this geometric mean equals the geometric mean of the numbers $\left\{a_{1}, a_{2}, \ldots, a_{n}\right\}$. (Source: Canada) Hints: 132, 69

**Problem 12.18:** Find a closed form for even $n$:
$$\sum_{k=0}^{n / 2}\left[2^{2 k} \cdot 2 k\binom{n}{2 k}\right] .$$

Hints: 160

**Problem 12.19:** Find
$$\sum_{k=0}^{49}(-1)^{k}\binom{99}{2 k}$$
(Source: AMC) Hints: 212, 93

**Problem 12.20:** ★ Prove that
$$\sum_{i=0}^{n} 2^{i}\binom{n}{i}\binom{n-i}{\lfloor(n-i) / 2\rfloor}=\binom{2 n+1}{n}$$
where $\lfloor x\rfloor$ is the greatest integer less than or equal to $x$. Hints: 114, 280

**Problem 12.21:** \* For any positive integer $n$, compute the sum
$$\binom{n}{0}+\binom{n}{3}+\binom{n}{6}+\cdots$$

Hints: 286, 97

**Problem 12.22:** ★ For any positive integers $0<k \leq n$, define the number $\left\{\begin{array}{l}n \\ k\end{array}\right\}$ to be the number of ways to partition the set $(1,2, \ldots, n)$ into $k$ non-empty disjoint subsets. These numbers are called the Stirling numbers of the second kind (there are also Stirling numbers of the first kind, but we're not going to discuss them here). For example, $\left\{\begin{array}{l}4 \\ 3\end{array}\right\}=6$, because we have the following 6 partitions of $(1,2,3,4)$ into 3 disjoint non-empty subsets:

\begin{tabular}{lll}
$\{1\},\{2\},\{3,4\}$ & $\{1\},\{3\},\{2,4\}$ & $\{1\},\{4\},\{2,3\}$ \\
$\{2\},\{3\},\{1,4\}$ & $\{2\},\{4\},(1,3\}$ & $\{3\},\{4\},\{1,2\}$
\end{tabular}

(a) Find simple formulas for $\left\{\begin{array}{l}n \\ 1\end{array}\right\}$ and $\left\{\begin{array}{l}n \\ n\end{array}\right\}$.
(b) Find simple formulas for $\left\{\begin{array}{l}n \\ 2\end{array}\right\}$ and $\left\{\begin{array}{c}n \\ n-1\end{array}\right\}$.
(c) Prove the Pascal-like identity
$$\left\{\begin{array}{c}
n \\
k-1
\end{array}\right\}+k\left\{\begin{array}{l}
n \\
k
\end{array}\right\}=\left\{\begin{array}{c}
n+1 \\
k
\end{array}\right\},$$
for all $1<k \leq n$.
(d) ★ Prove that
$$\left\{\begin{array}{l}
n \\
k
\end{array}\right\}=\frac{1}{k!} \sum_{j=0}^{k}(-1)^{j}\binom{k}{j}(k-j)^{n},$$
via the use of a suitable counting argument. Hints: 259, 42, 296
