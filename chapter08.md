# Chapter 8: Mathematical Induction

*Of course I have played outdoor games. I once played dominoes in an open air cafe in Paris. - Oscar Wilde*

This short chapter will introduce a proof tool called mathematical induction.
The principle of mathematical induction (often called just induction) is one of the fundamental proof methods that we use to prove statements about positive integers. The classic metaphor used to describe mathematical induction is a row of dominos all standing on end:

If we tip the first domino over:
and if each domino, as it falls, knocks over the next domino in line:
then ultimately, all of the dominos will fall over:

This is the basis of mathematical induction. Suppose that we wish to prove some mathematical statement that involves a positive integer $n$. Each "domino" represents the statement for a particular value of $n$ : the first domino is the statement where $n=1$, the second domino is the statement where $n=2$, and so on. If we can prove that the first statement (where $n=1$ ) is true, and that each statement implies the next one, then we can knock all the dominos down, and thus prove that the statement is true for all positive integers $n$.

In this chapter we'll formally state the principle of mathematical induction, and use it in several examples. Mathematical induction is one of the most common proof techniques that we use in counting problems, and you should master it until it becomes almost second nature.

Let's begin with a simple example:

**Problem 8.1:** Prove, using mathematical induction, that for any positive integer $n$, the sum of the first $n$ positive integers equals $\frac{n(n+1)}{2}$.

*Solution for Problem 8.1:* This proof, as with every proof that uses mathematical induction, consists of two parts.
- A base case (this is analogous to "knocking over the first domino")
- An inductive step (this is analogous to "proving that each domino knocks over the next one")

So let's do these two steps.
Base case: We need to prove the statement for $n=1$. The sum of the first 1 positive integers is just 1 , and indeed, this equals
$$\frac{1(1+1)}{2}=\frac{2}{2}=1$$

Inductive step: We assume that the statement is true for some positive integer $k$; that is, we assume that the sum of the first $k$ positive integers is $\frac{k(k+1)}{2}$. This assumption is called the inductive hypothesis. Now we wish to show that the statement is also true for $k+1$, so we compute the sum of the first $k+1$ positive integers. Since we will want to use our inductive hypothesis, we break up the sum of the first $k+1$ positive integers into the sum of the first $k$ positive integers plus $k+1$ :
$$1+2+\cdots+k+(k+1)=(1+2+\cdots+k)+(k+1) .$$

Now we can use our inductive hypothesis. We have assumed that the sum of the first $k$ positive integers is $\frac{k(k+1)}{2}$, so we can substitute it into the previous equation:
$$1+2+\cdots+(k+1)=\frac{k(k+1)}{2}+(k+1)$$

The rest is just algebra:
$$1+2+\cdots+(k+1)=\frac{k(k+1)}{2}+(k+1)=\frac{k(k+1)+2(k+1)}{2}=\frac{(k+1)(k+2)}{2}=\frac{(k+1)((k+1)+1)}{2} .$$

So we see that the original statement, that the sum of the first $n$ positive integers is equal to $\frac{n(n+1)}{2}$, is true for $n=k+1$.

We have completed both of the necessary steps for an induction proof, so we have proved that the statement is true for all positive integers $n$.

The important thing to remember about a mathematical induction proof is that your proof must contain two separate parts: the verification of the base case, and the proof of the inductive step.

> **Important:** We can use mathematical induction when we wish to prove a statement $\mathcal{S}(n)$ that depends on a positive integer $n$. The proof consists of two steps:
> 1. Prove $\mathcal{S}(1)$.
> 2. Prove that $S(k)$ implies $\mathcal{S}(k+1)$ for any positive integer $k$.

For example, in Problem 8.1 above, the statement $\mathcal{S}(n)$ was "the sum of the first $n$ positive integers is equal to $\frac{n(n+1)}{2}$." Our base case established this for $n=1$, and our inductive step established that the statement for $n=k$ implied the statement for $n=k+1$.

Now that you've seen how mathematical induction works, try a few problems:

## Problems

**Problem 8.2:** Prove that for any positive integer $n$,
$$1^{3}+2^{3}+\cdots+n^{3}=(1+2+\cdots+n)^{2} .$$

**Problem 8.3:** Prove that the sum of the interior angles of a convex $n$-sided polygon is $180(n-2)$ degrees. (You may assume that the sum of the interior angles of a triangle is $180^{\circ}$.)

**Problem 8.4:** Let $n$ be a positive integer. One square of a $2^{n} \times 2^{n}$ chessboard is removed. Prove that the remaining chessboard can be tiled with 3-square L-shaped tiles like the one shown at right.

**Problem 8.5:** We start with a pile of 25 stones. We divide the stones into two piles (however we wish), and write the product of the numbers of stones in the two piles on the blackboard. (For example, we might choose to divide the stones into piles of 11 and 14 , in which case we would write 154 on the board.) We now choose one of the remaining piles, divide it into two smaller piles in any manner we choose, and again write the product of the numbers of stones in the two new piles on the blackboard. We repeat this process until we have 25 piles of 1 stone each. Prove that at the end of this process, no matter what choices we make along the way, the sum of the numbers written on the board will be 300.

**Problem 8.6:** In a large field, $n$ people are standing so that for each person, the distances to all the other people are different. At a given signal, each person fires a water pistol and hits the person who is closest to them. When $n$ is odd, prove that there is at least one person who is left dry.

## Solutions

**Problem 8.2:** Prove that for any positive integer $n$,
$$1^{3}+2^{3}+\cdots+n^{3}=(1+2+\cdots+n)^{2}$$

*Solution for Problem 8.2:* Once again, we have a statement that is claimed for all positive integers $n$. Then is your cue to think about using induction.

> **Concept:** Whenever you have a statement that depends on a positive integer $n$, consider mathematical induction as a possible method of proving the statement.

Let's prove the problem statement using induction.
Base case: We see immediately that $1^{3}=(1)^{2}$.
Inductive step: Assume that $1^{3}+2^{3}+\cdots+k^{3}=(1+2+\cdots+k)^{2}$ (recall that this is called the inductive hypothesis). We now evaluate $1^{3}+2^{3}+\cdots+k^{3}+(k+1)^{3}$. Since we want to use the inductive hypothesis, we should try to rewrite this expression in terms of an expression present in the inductive hypothesis:
$$1^{3}+2^{3}+\cdots+k^{3}+(k+1)^{3}=\left(1^{3}+2^{3}+\cdots+k^{3}\right)+(k+1)^{3} .$$

Now we can apply the inductive hypothesis to replace $\left(1^{3}+2^{3}+\cdots+k^{3}\right)$ :
$$\left(1^{3}+2^{3}+\cdots+k^{3}\right)+(k+1)^{3}=(1+2+\cdots+k)^{2}+(k+1)^{3} .$$

We need to simplify the right side, so we apply the result from Problem 8.1 and a bit of algebra:
$$(1+2+\cdots+k)^{2}+(k+1)^{3}=\left(\frac{k(k+1)}{2}\right)^{2}+(k+1)^{3}=\frac{k^{2}(k+1)^{2}+4(k+1)^{3}}{4}=\frac{k^{4}+6 k^{3}+13 k^{2}+12 k+4}{4}$$

It would be nice if that numerator factored. Usually, factoring a degree 4 polynomial is a bit of a chore. However, here we have a huge clue. Remember that at the end of the day, we want the right side to equal $(1+2+\cdots+(k+1))^{2}$, and that this is equal to $\left(\frac{(k+1)(k+2)}{2}\right)^{2}$. So we hope that the numerator factors as $(k+1)^{2}(k+2)^{2}$. Indeed, it does:
$$\frac{k^{4}+6 k^{3}+13 k^{2}+12 k+4}{4}=\frac{\left(k^{2}+2 k+1\right)\left(k^{2}+4 k+4\right)}{4}=\left(\frac{(k+1)(k+2)}{2}\right)^{2}$$

Finally, we use Problem 8.1 again to finish:
$$1^{3}+2^{3}+\cdots+k^{3}+(k+1)^{3}=\left(\frac{(k+1)(k+2)}{2}\right)^{2}=(1+2+\cdots+k+(k+1))^{2} .$$

We have proven our base case and our inductive step, so the result is true for all positive integers $n$.

Induction can be used in geometric problems too! Anything that depends on a positive integer $n$ is potentially a candidate for mathematical induction.

**Problem 8.3:** Prove that the sum of the interior angles of a convex $n$-sided polygon is $180(n-2)$ degrees. (You may assume that the sum of the interior angles of a triangle is $180^{\circ}$.)

*Solution for Problem 8.3:* We already have the base case $n=3$, since the problem told us we can assume that the sum of a triangle's angles is $180=180(3-2)$. (Note: we'll omit the degree symbol and the word "degrees" in our solution; you can assume that all angle quantities are in degrees.) So we can proceed directly to the inductive step.

We assume that for some integer $k \geq 3$, the sum of the interior angles of a $k$-sided polygon is $180(k-2)$. Now we want to compute the sum of the interior angles of a $(k+1)$-sided polygon. How are we going to get a $k$-sided polygon from a $(k+1)$-sided polygon?

We can lop off a vertex!
For example, in the first picture in Figure 8.1 below, we have a 7 -sided polygon. We can draw a diagonal between vertices that are two sides apart, as shown in the middle diagram. This splits the polygon into a triangle and a 6-sided polygon, as in the right diagram below.

Figure 8.1: Splitting a 7-gon into a triangle and a 6-gon

Note that the sum of the angles of the 7 -sided polygon is equal to the sum of the angles of the triangle (which is 180 ) plus the sum of the angles of the 6 -sided polygon (which is $180(4)=720$ ). Therefore, the sum of the angles in the 7-sided polygon is $180+720=900=180(5)$.
We can do this for any $(k+1)$-sided polygon. We draw a diagonal between two vertices that are 2 edges apart on the polygon, splitting the $(k+1)$-sided polygon into a triangle and a $k$-sided polygon. (The dashed lines in Figure 8.2 below indicate that the polygon has an arbitrary number of sides.)

Figure 8.2: Splitting a $(k+1)$-gon into a triangle and a $k$-gon

We know that the sum of the angles of the triangle is 180 , and by the inductive hypothesis, we know the sum of the angles of the $k$-sided polygon is $180(k-2)$. Therefore, the sum of the angles in the $(k+1)$-sided polygon is the sum of these, which is
$$180+180(k-2)=180(k-1)=180((k+1)-2),$$
proving the assertion.

**Problem 8.4:** Let $n$ be a positive integer. One square of a $2^{n} \times 2^{n}$ chessboard is removed. Prove that the remaining chessboard can be tiled with 3 -square L -shaped tiles like the one shown at right.

*Solution for Problem 8.4:* As we've seen before, we have a statement that we must prove to be true for all positive integers. This makes it a good candidate for induction.

Base case: If we take a $2^{1} \times 2^{1}$ chessboard-that is, a $2 \times 2$ chessboard-and remove a square, what's left will be exactly the same shape as an L -shaped tile (although perhaps rotated). So we can simply place a single tile to cover the board, and we're done.

Inductive step: Assume that we can tile any $2^{k} \times 2^{k}$ chessboard with any square removed, where $k \geq 1$ is a positive integer. We'll consider a $2^{k+1} \times 2^{k+1}$ chessboard with a square removed, and see if we can tile it.

We need to reduce the $2^{k+1} \times 2^{k+1}$ problem down to the $2^{k} \times 2^{k}$ problem, which we assume (by the inductive hypothesis) that we can solve. What's the easiest way to do that? It seems like the easiest way is to divide our $2^{k+1} \times 2^{k+1}$ board into 4 boards of size $2^{k} \times 2^{k}$ by slicing it horizontally and vertically through the middle.

But only one of our four $2^{k} \times 2^{k}$ boards is going to have a square missing; the other three will be complete. We can use the inductive hypothesis to tile whichever quadrant contains the missing square, but what do we do about the other three? If only each of them had a square missing.... Is there a systematic way we can remove a square from each of the three complete $2^{k} \times 2^{k}$ boards?

Yes! "Remove" the squares closest to the center of the original $2^{k+1} \times 2^{k+1}$ board by covering them with a tile, as shown in the picture to the right. Now we're set! We place that tile in the center, and what's left is four boards of size $2^{k} \times 2^{k}$, each with a square missing. We can tile them, using the inductive hypothesis, and when we do so the result is a tiling of the original $2^{k+1} \times 2^{k+1}$ board.

Therefore, by induction, for all positive integers $n$, we can tile a $2^{n} \times 2^{n}$ board with any square removed.

Sometimes the result for $k$ is not enough to prove the result for $k+1$. We say that we are using strong induction when we must assume the result for all $1 \leq i \leq k$ in order to prove the result for $k+1$. The informal way to think of strong induction is that it takes the combined strength of all of the first $k$ dominos in order to knock over the $(k+1)^{\text {st }}$ domino. Strong induction is not that common, but as we will see in the next problem, it is occasionally necessary.

**Problem 8.5:** We start with a pile of 25 stones. We divide the stones into two piles (however we wish), and write the product of the numbers of stones in the two piles on the blackboard. (For example, we might choose to divide the stones into piles of 11 and 14 , in which case we would write 154 on the board.) We now choose one of the remaining piles, divide it into two smaller piles in any manner we choose, and again write the product of the numbers of stones in the two new piles on the blackboard. We repeat this process until we have 25 piles of 1 stone each. Prove that at the end of this process, no matter what choices we make along the way, the sum of the numbers written on the board will be 300 .

*Solution for Problem 8.5:* We might first try to figure out where that " 300 " comes from. To this end, we can experiment a bit with the most "extreme" choices that we can make when dividing the stones. One extreme way of dividing the stones is to always split the stones so that one of the new piles contains just a single stone. In other words, we divide the 25 stones initially into piles of 1 and 24 , then divide the 24 -stone pile into piles of 1 and 23 , and so on. If we do this, then the numbers that get written on the blackboard are $24,23, \ldots, 1$, and their sum is
$$24+23+\cdots+1=\frac{(25)(24)}{2}=\binom{25}{2}=300$$

Aha, there's the 300.
The difficulty is that there doesn't seem to be any obvious direct way to approach this problem. (It turns out that there's a really clever counting argument that proves that the sum must be 300 . But it's fairly difficult to see. We'll present it at the end of the solution.) But perhaps we can prove the more general version of the problem. In particular, what if we began with $n$ stones? Then based on our experimentation above, we would expect the sum at the end to be $\binom{n}{2}$. Indeed, if we did the same extreme pile-splitting with $n$ stones-that is, at every step, created a new pile with a single stone in it-then the numbers that get written on the blackboard would be $n-1, n-2, \ldots, 1$, and their sum is
$$(n-1)+(n-2)+(n-3)+\cdots+1=\frac{(n-1) n}{2}=\binom{n}{2}$$

So we'd like to prove that if we start with $n$ stones, we will end up with a sum of $\binom{n}{2}$, no matter how we go about dividing the stones at each step. Since we have a statement for all positive integers $n$, we might think to try induction. However, the difficulty is that the initial pile can be divided into two piles of any size. In particular, there is no way of getting from the problem of size $n-1$ to the problem of size $n$, so we'll need to use a somewhat stronger version of the inductive hypothesis.

But let's begin with the base case. When $n=1$, we have only 1 stone, and nothing to divide. So no numbers get written on the blackboard, and the sum of no numbers is $0=\binom{1}{2}$. (We know that $\binom{1}{2}=0$, since $\binom{1}{2}$ counts the number of ways to choose 2 items from a set of 1 item. It is impossible to choose 2 items from a set of 1 item, so there are 0 ways to make such a choice.)

For the inductive step, we assume that the result holds for all piles of size less than $k$, for some integer $k>1$. This is stronger than our usual inductive hypothesis of assuming that the result holds for a pile of size $k-1$. We now consider a pile of size $k$. The initial step splits the pile into a pile of size $j$ (where $1 \leq j<k$ ) and a pile of size $k-j$, so that the number $j(k-j)$ is the first number written on the board.

Consider all of the numbers that we write on the board as the $j$-stone pile is repeatedly split until these $j$ stones are in piles of 1 stone each. By the inductive hypothesis, the sum of these numbers is $\binom{j}{2}$. Similarly, as we repeatedly split the $(k-j)$-stone pile into piles of 1 stone each, the sum of numbers written is $\binom{k-j}{2}$. These numbers may get written in any order on the blackboard (since we might choose to split the piles in any order), but the order that the numbers are written on the board does not alter the sum.

Therefore, the total of the numbers on the blackboard will be
$$j(k-j)+\binom{j}{2}+\binom{k-j}{2} .$$

We can simplify this expression:
$$\begin{aligned}
j(k-j)+\binom{j}{2}+\binom{k-j}{2} & =j(k-j)+\frac{j(j-1)}{2}+\frac{(k-j)(k-j-1)}{2} \\
& =\frac{2 j k-2 j^{2}+j^{2}-j+k^{2}-j k-k-j k+j^{2}+j}{2} \\
& =\frac{k^{2}-k}{2} \\
& =\frac{k(k-1)}{2}=\binom{k}{2} .
\end{aligned}$$

In particular, note that all of the $j$ terms canceled, meaning that the sum doesn't depend on the initial choice of a split into two piles.

Thus, by induction, if we start with $n$ stones, then we will end up with a sum of $\binom{n}{2}$. In particular when $n=25$, the sum is $\binom{25}{2}=300$.

The previous problem is an example of recursion, which we will see more of in Chapter 10.
As we mentioned, there is a very clever counting solution to the problem that does not require induction. Again, suppose we start with a pile of $n$ stones. We connect every pair of stones by a string. Since there are $\binom{n}{2}$ pairs of stones, we will need $\binom{n}{2}$ strings.

Suppose we divide the $n$ stones into a pile of $j$ stones and a pile of $n-j$ stones, for some integer $0<j<n$. We then cut all of the strings between stones in different piles. Notice that $j(n-j)$ strings get cut, which is exactly the number that gets written on the blackboard.

We continue splitting piles and cutting strings between stones in different piles. Again, note that at each split, the number of strings being cut always equals the number written on the blackboard.

At the end of the process, each stone is in its own pile, so all of the $\binom{n}{2}$ strings have been cut. But the total number of strings that have been cut equals the sum of the numbers on the blackboard! So the sum of the numbers on the blackboard must be $\binom{n}{2}$.

**Problem 8.6:** In a large field, $n$ people are standing so that for each person, the distances to all the other people are different. At a given signal, each person fires a water pistol and hits the person who is closest to them. When $n$ is odd, prove that there is at least one person who is left dry.

*Solution for Problem 8.6:* We are trying to prove a statement for all odd positive integers, so we'll consider using induction.

The result is clearly true for the base case $n=1$ : if there is only one person, then there is nobody else to shoot at him, so he must remain dry.

Since we want to prove this result only for odd positive integers, we'll slightly modify our inductive step. We will assume that the result is true for some odd positive integer $n=k$, and try to prove the result for $n=k+2$. This basically skips over all the cases where $n$ is an even positive integer, and instead shows that the result for one odd integer implies the result for the next odd integer.

Consider a group of $k+2$ people with water pistols. There are two people that we know will definitely not stay dry: let $A$ and $B$ be the pair of people who are closest to each other, so $A$ and $B$ end up firing at each other.

We now have two possibilities: either one of the remaining $k$ people also fires at $A$ or $B$, or none of them do. If one of the remaining $k$ people also fires at $A$ or $B$, then this leaves at most $k-1$ shooting at those $k$ people, therefore one of the $k$ people will be left dry.

On the other hand, if none of the $k$ people fire at $A$ or $B$, then we have a group of $k$ people, all of whom fire at each other. But now we can use our inductive hypothesis! By the induction hypothesis, one of these $k$ people must be left dry.

In either case, we have a person who is left dry. Therefore, the result is true for $n=k+2$, and by induction, it is true for all odd positive integers $n$.

## Summary

- We can use mathematical induction when we wish to prove a statement $S(n)$ that depends on a positive integer $n$. The proof consists of two steps:
  1. Prove $\mathcal{S}(1)$.
  2. Prove that $S(k)$ implies $S(k+1)$ for any positive integer $k$.

> **Concept:** Whenever you have a statement that depends on a positive integer $n$, consider mathematical induction as a possible method of proving the statement.

## Review Problems

**8.7** Prove that the sum of the first $n$ positive odd integers is $n^{2}$.

**8.8** Prove, by induction, the formula for a geometric series:
$$a+a r+a r^{2}+\cdots+a r^{n-1}=a \frac{r^{n}-1}{r-1}$$

**8.9** Prove that
$$1^{2}+2^{2}+\cdots+n^{2}=\frac{n(n+1)(2 n+1)}{6}$$
for all positive integers $n$.

**8.10** Prove that $7^{n}-1$ is a multiple of 6 for all positive integers $n$.

**8.11** Prove that
$$2!\cdot 4!\cdots \cdots(2 n)!\geq((n+1)!)^{n}$$
for all positive integers $n$.

**8.12** $2 n$ points (where $n>1$ is a positive integer) are given in space, such that no 3 of them are on a line. We draw $n^{2}+1$ line segments connecting pairs of these points. Prove that there must exist a triangle whose vertices are 3 of the points and whose sides are 3 of the drawn segments.

**8.13** A plane is divided into regions by a finite number of lines. Show that it is possible to color the resulting regions with two colors, white and black, so that any two bordering regions are of opposite colors. (Two regions border if and only if their common boundary is a line segment; in particular regions that only meet at a single point do not border.)

## Challenge Problems

**8.14** Prove the generalized triangle inequality: if $x_{1}, x_{2}, \ldots, x_{n}$ are real numbers, then
$$\left|x_{1}+x_{2}+\cdots+x_{n}\right| \leq\left|x_{1}\right|+\left|x_{2}\right|+\cdots+\left|x_{n}\right|$$

Hints: 40, 2

**8.15** Prove that $2^{2^{n}}+3^{2^{n}}+5^{2^{n}}$ is divisible by 19 for all positive integers $n$. Hints: 174

**8.16** For any set $T$ whose elements are positive integers, define $f(T)$ to be the square of the product of the elements of $T$. For example, if $T=\{1,3,6\}$, then $f(T)=(1 \cdot 3 \cdot 6)^{2}=18^{2}=324$.

For any positive integer $n$, consider all nonempty subsets $S$ of $\{1,2, \ldots, n\}$ that do not contain two consecutive integers. Prove that the sum of all the $f(S)$'s of these subsets is $(n+1)!-1$. Hints: 268

**8.17\*** An international conference consists of $n$ representatives from each of $n$ different countries. Prove that the $n^{2}$ people can be seated around a large round table such that, if $A$ and $B$ are two distinct representatives from the same country, then the people sitting to the immediate left of $A$ and to the immediate left of $B$ are from different countries. Hints: 335, 38

**8.18\*** Suppose there are $n$ identical cars at different points on a circular track, and that each car needs exactly 1 gallon of gas to make it around the track. Initially, the total amount of gas in all of the cars' fuel tanks is exactly 1 gallon. Show that there is one car that can make it counterclockwise around the track by collecting all of the gasoline from each car that it passes as it moves. Hints: 71, 41

**8.19\*** Pick's Theorem states that given a polygon in the coordinate plane, whose vertices are all lattice points (that is, points with integer coordinates), the area of the polygon is given by the formula
$$I+\frac{B}{2}-1,$$
where $I$ is the number of lattice points on the interior of the polygon, and $B$ is the number of lattice points on the boundary of the polygon. For example,
in the picture to the right, the triangle has 13 lattice points in its interior, and 6 lattice points on the boundary, so the area is $13+6 / 2-1=15$.

Assume that Pick's Theorem is true for triangles whose vertices are lattice points. (For an extra challenge, you can try to prove this, but the proof is messy and involves a lot of cases.) Prove that Pick's Theorem is true for all polygons whose vertices are lattice points, by induction on the number of vertices of the polygon. Hints: 122, 228

**8.20\*** Let $S_{2002}$ be a set with 2002 elements, and let $N$ be an integer with $0 \leq N \leq 2^{2002}$. Prove that it is possible to color every subset of $S$ either black or white so that the following conditions hold:
1. the union of any two white subsets is white;
2. the union of any two black subsets is black;
3. there are exactly $N$ white subsets.

(Source: USAMO) Hints: 336, 315

**8.21\*** An $n \times n$ matrix whose entries come from the set $S=\{1,2, \ldots, 2 n-1\}$ is called a silver matrix if, for each $i=1,2, \ldots, n$, the $i^{\text {th }}$ row and the $i^{\text {th }}$ column together contain all elements of $S$. For example, the matrix to the right is a silver matrix for $n=4$. Show that silver matrices exist for infinitely many values of $n$. (Source: IMO)
$$\left(\begin{array}{llll}
1 & 2 & 5 & 6 \\
3 & 1 & 7 & 5 \\
4 & 6 & 1 & 2 \\
7 & 4 & 3 & 1
\end{array}\right)$$
Hints: 237, 9, 291
