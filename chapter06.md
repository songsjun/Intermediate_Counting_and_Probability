# Chapter 6: Constructive Expectation

*Life is so constructed, that the event does not, cannot, will not, match the expectation. - Charlotte Bronte*

## 6.1 Introduction

Recall that expected value is essentially a weighted average, where the values of different outcomes of an event are weighted based on their probability. If every outcome is equally likely, then the expected value is just the average of the possible outcomes.

In many situations, we can just use our basic definition of expected value:
$$E(X)=\sum_{i} P\left(X_{i}\right) V\left(X_{i}\right),$$
where $P\left(X_{i}\right)$ is the probability of event $X_{i}$ occurring, and $V\left(X_{i}\right)$ is the value of outcome $X_{i}$.
However, often it is quite difficult to list all of the possible outcomes directly, determine their probabilities and values, and compute the expectation in the usual manner. Instead, for many problems, we can take a more constructive approach to computing expectation.

The key fact that we will use is that we can sum expected values across different events. What we mean by this is that if we have a series of events that occur in succession, then the expected value of the sum of the outcomes of the events is equal to the sum of the expected values of the outcomes of the individual events. This is true even if the events are not independent of one another. This is a powerful tool that lets us find expected values of complicated events by breaking them down into more manageable sub-events.

This is a bit hard to describe in words, but hopefully a few problems will make the concept clear.

> **Extra!** High achievement always takes place in the framework of high expectation. - Charles Kettering

## 6.2 Basic Examples

### Problems

**Problem 6.1:** We simultaneously flip a penny, a nickel, a dime, and a quarter.
(a) List all 16 possible outcomes and the total value of the coins that land heads-up. What is the expected value of this total?
(b) Separately compute the expected values of each coin's contribution to the total.
(c) Sum your answers for (b) and compare this sum to your answer from (a).

**Problem 6.2:**
(a) We roll a pair of dice. What is the expected value of the total of the dice?
(b) We simultaneously roll 10 dice. What is the expected value of the total of the dice?

**Problem 6.3:** In the Showcase Showdown on the immensely popular TV game show The Price Is Right, if a contestant spins $\$ 1$ on the Big Wheel, she wins $\$ 1,000$ and gets a bonus spin in which she has a $1 / 20$ chance of winning an additional $\$ 10,000$ and a $1 / 10$ chance of winning an additional $\$ 5,000$. Suppose that a contestant has a $1 / 10$ chance of spinning $\$ 1$. What is the expected value of the contestant's winnings?

**Problem 6.4:** If $X$ and $Y$ are independent events, show that $E(X+Y)=E(X)+E(Y)$.

We can often exploit the fact that we may sum expected values across multiple events. Let's see a classic example of this.

**Problem 6.1:** We simultaneously flip a penny, a nickel, a dime, and a quarter. What is the expected value of the sum of the values of the coins that land heads-up?

*Solution for Problem 6.1:* Since each of the four coins are equally likely to come up heads or tails, there are $2^{4}=16$ equally likely outcomes. We can find the expected value by simply averaging the values of all the possible outcomes. For this, we can make a chart:

\begin{tabular}{|r|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline Penny & T & H & T & H & T & H & T & H & T & H & T & H & T & H & T & H \\
\hline Nickel & T & T & H & H & T & T & H & H & T & T & H & H & T & T & H & H \\
\hline Dime & T & T & T & T & H & H & H & H & T & T & T & T & H & H & H & H \\
\hline Quarter & T & T & T & T & T & T & T & T & H & H & H & H & H & H & H & H \\
\hline \hline Total & 0 & 1 & 5 & 6 & 10 & 11 & 15 & 16 & 25 & 26 & 30 & 31 & 35 & 36 & 40 & 41 \\
\hline
\end{tabular}

So we see that the expected value is
$$\frac{0+1+5+6+10+11+15+16+25+26+30+31+35+36+40+41}{16}=\frac{328}{16}=20.5 .$$

However, we could have done this more simply by looking at each coin separately. The penny has an expected value of $\frac{1}{2}(0)+\frac{1}{2}(1)=\frac{1}{2}$. Similarly, the nickel has expected value $\frac{5}{2}$, the dime has expected value $\frac{10}{2}=5$, and the quarter has expected value $\frac{25}{2}$. Therefore, the expected value when we flip them all is $\frac{1}{2}+\frac{5}{2}+5+\frac{25}{2}=\frac{41}{2}=20.5$.

> **Concept:** The expected value of a sum of events is the sum of the expected values of the individual events.

**Problem 6.2:**
(a) We roll a pair of dice. What is the expected value of the total of the dice?
(b) We simultaneously roll 10 dice. What is the expected value of the total of the dice?

*Solution for Problem 6.2:* Rather than list all 36 possible outcomes for the pair of dice, we can use the fact that the expected value for a roll of a single die is $\frac{1}{6}(1+2+3+4+5+6)=3.5$. Therefore, the expected value of the total of two dice is $2(3.5)=7$, and the expected value of the total of 10 dice is $10(3.5)=35$. $\square$

**Problem 6.3:** In the Showcase Showdown on the immensely popular TV game show The Price Is Right, if a contestant spins $\$ 1$ on the Big Wheel, she wins $\$ 1,000$ and gets a bonus spin in which she has a $1 / 20$ chance of winning an additional $\$ 10,000$ and a $1 / 10$ chance of winning an additional $\$ 5,000$. Suppose that a contestant has a $1 / 10$ chance of spinning $\$ 1$. What is the expected value of the contestant's winnings?

*Solution for Problem 6.3:* There are four possible outcomes:
- The contestant wins nothing with probability $\frac{9}{10}$.
- The contestant wins $\$ 1,000$ with probability $\frac{1}{10} \cdot \frac{17}{20}=\frac{17}{200}$.
- The contestant wins $\$ 6,000$ with probability $\frac{1}{10} \cdot \frac{1}{10}=\frac{1}{100}$.
- The contestant wins $\$ 11,000$ with probability $\frac{1}{10} \cdot \frac{1}{20}=\frac{1}{200}$.

Therefore, the expected value of her win is:
$$\frac{9}{10}(\$ 0)+\frac{17}{200}(\$ 1000)+\frac{1}{100}(\$ 6000)+\frac{1}{200}(\$ 11000)=\frac{17(\$ 1000)+2(\$ 6000)+\$ 11000}{200}=\frac{\$ 40000}{200}=\$ 200 .$$

We can do this more simply by calculating the expected value of the regular spin and the bonus spin separately. The regular spin has expected value $\frac{1}{10}(\$ 1000)=\$ 100$. The bonus spin has expected value $\frac{1}{10}(\$ 5000)+\frac{1}{20}(\$ 10000)=\$ 1000$, but we have to remember that the contestant only gets the bonus spin with probability $\frac{1}{10}$. Therefore, the overall expected value is $\$ 100+\frac{1}{10}(\$ 1000)=\$ 100+\$ 100=\$ 200$.

Note that in Problem 6.3, the two events that we are summing are not independent: the player only gets a bonus spin if she wins on the regular spin, so the bonus outcome is dependent on the regular outcome. Nonetheless, we saw that we could still sum the individual expected values to get the overall expected value.

Now that you've seen a few examples, you hopefully have a good feel for what we're doing. We are computing the expected value of the sum of outcomes of individual events, and we have seen (so far) that we can do this by summing the expected values of the individual events. Let's try to make this into a formal statement, and see if we can prove it.

**Problem 6.4:** If $X$ and $Y$ are independent events, show that $E(X+Y)=E(X)+E(Y)$.

> **WARNING!!** This proof is somewhat algebraically intense. Don't worry if you don't see every detail on the first reading.

*Solution for Problem 6.4:* We'll need to write formulas for the expected values of $X$ and $Y$, and for that, we'll need to introduce some notation. (Also, we're only going to consider the situation in which both Y and $Y$ have a finite number of possible outcomes; if $X$ and $Y$ have infinitely many outcomes, the result is still true, but it is somewhat difficult to prove.)

Suppose that $X$ has $m$ possible outcomes, which have probabilities $p_{1}, p_{2}, \ldots, p_{m}$ and values $x_{1}, x_{2}, \ldots, x_{m}$. This means that $p_{1}+p_{2}+\cdots+p_{m}=1$ and that
$$E(X)=p_{1} x_{1}+p_{2} x_{2}+\cdots+p_{m} x_{m}=\sum_{i=1}^{m} p_{i} x_{i}$$

Similarly, suppose that $Y$ has $n$ possible outcomes, which have probabilities $q_{1}, q_{2}, \ldots, q_{n}$ and values 25. $1 / 2, \ldots, y_{n}$. This means that $q_{1}+q_{2}+\cdots+q_{n}=1$ and that
$$E(Y)=q_{1} y_{1}+q_{2} y_{2}+\cdots+q_{n} y_{n}=\sum_{j=1}^{n} q_{j} y_{j} .$$

What do we know about the event "$X+Y$"? Since $X$ and $Y$ are independent events, we know that "$\mathrm{Z}+Y^{\prime \prime}$ has $m n$ possible outcomes: value $x_{i}+y_{j}$ occurs with probability $p_{i} q_{j}$, for all $1 \leq i \leq m$ and $1 \leq j \leq n$. So
$$\begin{aligned}
E(X+Y) & =p_{1} q_{1}\left(x_{1}+y_{1}\right)+p_{1} q_{2}\left(x_{1}+y_{2}\right)+\cdots+p_{1} q_{n}\left(x_{1}+y_{n}\right) \\
& +p_{2} q_{1}\left(x_{2}+y_{1}\right)+p_{2} q_{2}\left(x_{2}+y_{2}\right)+\cdots+p_{2} q_{n}\left(x_{2}+y_{n}\right) \\
& +\vdots \\
& +p_{m} q_{1}\left(x_{m}+y_{1}\right)+p_{m} q_{2}\left(x_{m}+y_{2}\right)+\cdots+p_{m} q_{n}\left(x_{m}+y_{n}\right) \\
& =\sum_{i=1}^{m} \sum_{j=1}^{n} p_{i} q_{j}\left(x_{i}+y_{j}\right)
\end{aligned}$$

Why is this equal to $E(X)+E(Y)$?

We can isolate the $x$ terms in each row. For example, in the first row of the above equation for $E(X+Y)$, we have
$$p_{1} q_{1} x_{1}+p_{1} q_{2} x_{1}+\cdots+p_{1} q_{n} x_{1}=p_{1} x_{1}\left(q_{1}+\cdots+q_{n}\right)=p_{1} x_{1}$$
since $q_{1}+\cdots+q_{n}=1$. Similarly, the $x$ terms in the second row sum to $p_{2} x_{2}$, and so on. Thus all the $x$ terms, summed over all rows, give
$$p_{1} x_{1}+p_{2} x_{2}+\cdots+p_{m} x_{m}=E(X)$$

We can also isolate the $y$ terms, but this time by column. For example, in the first column of the above equation for $E(X+Y)$, we have
$$p_{1} q_{1} y_{1}+p_{2} q_{1} y_{1}+\cdots+p_{m} q_{1} y_{1}=q_{1} y_{1}\left(p_{1}+\cdots+p_{m}\right)=q_{1} y_{1}$$
since $p_{1}+\cdots+p_{m}=1$. Similarly, the $y$ terms in the second column sum to $q_{2} y_{2}$, and so on. Thus all the $y$ terms, summed over all columns, give
$$q_{1} y_{1}+q_{2} y_{2}+\cdots+q_{n} y_{n}=E(Y)$$

This shows that $E(X+Y)=E(X)+E(Y)$.

> **Concept:** Don't worry if you didn't follow all of the details in the above proof-the algebra used is somewhat complicated. It's vastly more important that you understand the concept: we can sum expectations across separate events to get the expectation of the combined event.

In fact, the result $E(X+Y)=E(X)+E(Y)$ is still true even if $X$ and $Y$ are dependent events, as we saw as example of in Problem 6.3. It is a lot more difficult to prove, however: the algebra is a lot messier, and we'd need to introduce notation that we haven't yet developed. So we're not going to try to prove this here, but you can accept it as true from now on.

This is not limited to just 2 events: we can sum any number of events in the same fashion. To summarize:

> **Important:** If $X_{1}, X_{2}, \ldots, X_{k}$ are several events (independent or not), then
> $$E\left(X_{1}+X_{2}+\cdots+X_{k}\right)=E\left(X_{1}\right)+E\left(X_{2}\right)+\cdots+E\left(X_{k}\right) .$$

### Exercises

6.2.1 I flip 20 coins. I then discard the coins that come up heads, and re-flip those that come up tails. What is the expected number of coins that again come up tails?

6.2.2
(a) If I roll one green die and two blue dice, what is the expected value of the sum of the values of the blue dice minus the value of the green die?
(b) If I roll 37 green dice and 38 blue dice, what is the expected value of the sum of the values of the blue dice minus the value of the sum of the green dice?

6.2.3 Kai picks a number and Jae picks a number. Kai picks $w$ with probability $p$ and $x$ with probability $1-p$. Jae picks $y$ with probability $q$ and $z$ with probability $1-q$.
(a) What is the expected value of Kai's number?
(b) What is the expected value of Jae's number?
(c) Find an algebraic expression for the expected value of the sum of Kai's and Jae's numbers by finding the probabilities of each of the 4 cases and then computing the expected value manually. Is your expression equal to the sum of the expressions you found in (a) and (b)?

6.2.4 Henry flips 10 coins and lays them on the desk. He then chooses one of the coins at random, and if it is tails, he flips it to heads. What is the expected number of heads showing? (Source: Mandelbrot) Hints: 37

6.2.5★ What is the expected number of turns of a randomly-chosen 9-step path from point $A$ to point $B$ in the grid at right? (A turn is any point where the path changes direction; for example, the path shown at right has 3 turns, one at each of the marked points.) Hints: 150

## 6.3 Summing Expectations Constructively

### Problems

**Problem 6.5:** I flip a coin 10 times.
(a) What is the probability that the $1^{\text {st }}$ and $2^{\text {nd }}$ flips come up heads?
(b) What is the probability that the $2^{\text {nd }}$ and $3^{\text {rd }}$ flips come up heads?
(c) What is the expected number of pairs of consecutive tosses that come up heads? (For example, the sequence THHTHHHTHH has 4 pairs of consecutive HH's.)

**Problem 6.6:** I have 12 addressed letters to mail, and 12 corresponding pre-addressed envelopes. For some wacky reason, I decide to put the letters into the envelopes at random, one letter per envelope. What is the expected number of letters that get placed into their proper envelopes?

**Problem 6.7:** An equilateral triangle is tiled with $n^{2}$ smaller congruent equilateral triangles such that there are $n$ smaller triangles along each of the sides of the original triangle. (The case $n=11$ is shown at right.) For each of the small equilateral triangles, we randomly choose a vertex $V$ of the triangle and draw an arc with that vertex as center connecting the midpoints of the two sides of the small triangle with $V$ as an endpoint. Find the expected value of the number of full circles formed in terms of $n$. (Source: USAMTS)

**Problem 6.8:** There are 650 special points inside a circle of radius 16. You have a flat washer in the shape of an annulus (the region between two concentric circles), which has an inside radius of 2 and an outside radius of 3. Our goal is to show that it is always possible to place the washer so that it covers up at least 10 of the special points.
(a) Suppose we can show that the expected number of points covered by a randomly-placed washer is at least 9. Explain why this would prove our result that it is possible to choose a placement of the washer that covers at least 10 points.
(b) Let $G$ be one of the special points. Determine the probability that $G$ is covered by a randomly-placed washer.
(c) Compute the expected number of points covered by a randomly-placed washer, and finish the problem.
(Source: PSS)

Just as we can often count items by constructing them and keeping track of the number of choices along the way, we can also often compute expectations using a similar constructive method. As we saw in Problem 6.4, we have a very powerful tool: we can sum expectations, even across dependent events.

This first problem of this section shows the power of this idea.

**Problem 6.5:** I flip a coin 10 times. What is the expected number of pairs of consecutive tosses that come up heads? (For example, the sequence THHTHHHTHH has 4 pairs of consecutive HH's.)

*Solution for Problem 6.5:* There are several tactics that we might think about. For instance, we might try to count the number of sequences with 1 pair of heads, with 2 pairs of heads, and so on, but this quickly devolves into a really messy PIE calculation. (If you don't believe this, try it and see.)

We might also try a straightforward constructive counting argument, but the problem with this approach is that the probabilities of the existence of pairs of heads in consecutive locations are not independent. For example, if the first two flips are HH, then there's a $\frac{1}{2}$ chance of a second pair of heads in the next slot (in other words, of the first three flips being HHH), but if the first two flips are TT, then there's 0 chance of a pair of heads in the next slot (since the first three flips will be either TTH or TTT). This makes it hard to construct the sequences without a lot of messy casework.

Fortunately, we don't have to do that!
Any particular pair of consecutive flips is HH with probability $\frac{1}{4}$. Therefore, each pair of consecutive flips contributes $\frac{1}{4}$ to the overall expected value. Since there are 9 possible pairs of consecutive flips that could be HH, the expected number of pairs of consecutive flips of heads is $9\left(\frac{1}{4}\right)=\frac{9}{4}$.

If you don't quite buy this explanation, there's another way to think about it. We know that there are $2^{10}=1024$ possible sequences of ten coin flips (and they're all equally likely). We also know that $2^{8}=256$ of them begin with HH (since we have 2 choices for each of the remaining 8 flips). Similarly, for any particular choice of consecutive flips, we know that 256 of the sequences have HH in that position (for example, there are 256 sequences of the form ???HH?????, where ? can be anything), since we have 2 choices for each of the other 8 positions.

Therefore, when we sum the number of pairs of consecutive heads over all 1024 sequences, we find that 256 of the sequences contribute a pair of heads in the first position, 256 of the sequences contribute a pair of heads in the second position, and so on for each of the 9 possible positions. Therefore, there are $9(256)$ total consecutive pairs of heads among the 1024 sequences, and hence the expected value for the number of consecutive pairs of heads in any sequence is $\frac{9(256)}{1024}=9\left(\frac{256}{1024}\right)=9\left(\frac{1}{4}\right)=\frac{9}{4}$.

**Problem 6.6:** I have 12 addressed letters to mail, and 12 corresponding pre-addressed envelopes. For some wacky reason, I decide to put the letters into the envelopes at random, one letter per envelope. What is the expected number of letters that get placed into their proper envelopes?

*Solution for Problem 6.6:* Once again, we could try to count the number of outcomes with 0 correct letters, 1 correct letter, etc., but this would become a messy PIE calculation. We can instead sum the expected value constructively.

Each envelope individually has a $\frac{1}{12}$ chance of receiving the correct letter (since it is equally likely to receive any of the 12 letters). Therefore, each envelope contributes $\frac{1}{12}$ to the total expected number of letters in their correct envelopes. Since there are 12 envelopes, and each contributes $\frac{1}{12}$, the expected number of letters in their proper envelopes is $12\left(\frac{1}{12}\right)=1$.

Again, if you don't feel completely comfortable with this argument, note that for each envelope, 11! of the 12! possible arrangements will have that particular envelope correctly filled. Therefore, when we sum over all 12! arrangements, we get a total of $12(11!)$ envelopes correctly filled, and hence the expected number of such envelopes is $12(11!) / 12!=12!/ 12!=1$.

> **Sidenote:** It is natural to ask, in connection with Problem 6.6, what is the probability that none of the envelopes receives its correct letter? This is an example of a permutation called a derangement. We looked at derangements in Challenge Problem 3.41 when we were studying PIE. As we saw then, we can count the number of such permutations using PIE, by counting the number of arrangements in which at least 1 letter gets placed into its proper envelope. However, a nicer solution is to use recursion, which we will discuss in Chapter 10.

**Problem 6.7:** An equilateral triangle is tiled with $n^{2}$ smaller congruent equilateral triangles such that there are $n$ smaller triangles along each of the sides of the original triangle. (The case $n=11$ is shown at right.) For each of the small equilateral triangles, we randomly choose a vertex $V$ of the triangle and draw an arc with that vertex as center connecting the midpoints of the two sides of the small triangle with $V$ as an endpoint. Find the expected value of the number of full circles formed in terms of $n$.
(Source: USAMTS)

*Solution for Problem 6.7:* We can see that at any interior point inside the big triangle, we'll get a circle if all 6 of the little triangles surrounding that point line up exactly correctly, as in the picture at right. Each little triangle lines up with probability $\frac{1}{3}$, so the probability of getting a full circle at any particular point is $\left(\frac{1}{3}\right)^{6}=\frac{1}{729}$.

Now we have to determine how many interior points there are. We can see that there is 1 interior point near the top (at the bottom of the $2^{\text {nd }}$ row of triangles), then 2 interior points in the next row, and so on, down to $n-2$ points in the bottom interior row. Therefore there are
$$1+\cdots+(n-2)=\frac{(n-2)(n-1)}{2}$$
interior points. Since each of these points contributes $\frac{1}{729}$ to the expected number of circles, we get a final answer of
$$\frac{(n-2)(n-1)}{1458} .$$

One very powerful application of expected value is in geometric optimization problems, as in the next example.

**Problem 6.8:** There are 650 special points inside a circle of radius 16. You have a flat washer in the shape of an annulus (the region between two concentric circles), which has an inside radius of 2 and an outside radius of 3. Show that it is always possible to place the washer so that it covers up at least 10 of the special points. (Source: PSS)

*Solution for Problem 6.8:* This is an existence problem. We wish to show that there exists some position at which we can place the washer so that it covers at least 10 points. But why is this related to expected value?

Suppose that we could compute the expected number of points covered by a randomly-placed washer, and that this value was greater than 9. What could we conclude? If the average washer covers more than 9 points, then there must exist some washer that covers 10 or more points. Because, if every washer covered 9 or fewer, how could the average possibly be greater than 9?

So our goal is to show that the expected value of the number of points covered by a washer placed at random is greater than 9. If we can show this, then we can conclude that there must be some place where we can put the washer to cover 10 or more points. Note that this is essentially a geometric version of the Pigeonhole Principle.

Calculating this expected value, however, doesn't appear to be so simple. For starters, there are infinitely many possible places to put the washer! Evaluating each possible position of the washer will literally take forever, since there are an infinite number of places we can put it.

However, there are only 650 points in the circle we have to consider. Therefore, we can take an element-by-element approach, similar to what we did in Problem 6.5. Recall in that problem, we noted that $\frac{1}{4}$ of the total sequences of flips had a pair of consecutive heads in any particular position, and we could sum this over each possible position to get a total expected value of $\frac{9}{4}$ consecutive pairs of heads. We'll do the same thing here: we'll calculate, for each possible special point, the portion of the washer placements in which that special point is covered.

> **Extra!** One of the common denominators I have found is that expectations rise above that which is expected. - George W. Bush

Let $P$ be one of our special points. $P$ is covered by the washer if and only if the center of the washer is at least 2 units away from the point, but no more than 3 units away. This region (the region between 2 and 3 units away from $P$) we will call our "success" region, and it is the region between the heavy dashed circles in the diagram to the right.

For example, in the picture at right, a washer is shown with center $W$ inside the "success" region, so the washer covers our point $P$. Any washer whose center is in the "success" region will cover point $P$, and conversely, any washer that covers point $P$ will have its center in the "success" region.

Therefore, the area of the region in which the center of the washer must be in order to cover $P$ is just the area of the "success" region. The region is
the difference between a circle of radius 3 and a circle of radius 2, so its area is $3^{2} \pi-2^{2} \pi=5 \pi$.

Now we consider the overall region where the center of the washer might be. We must be careful to include those cases in which the center of the washer is just outside our initial circle, but still covering special points near the circumference of the circle, as shown at left. To take into account the possibility of a washer centered outside the circle covering special points inside the circle (an example of which is shown at left), we note that the "possible" region, in which the center of our washer can be placed and still have the washer cover special points, is a circle with radius 19, not 16.

Now, we can evaluate the probability that a washer placed at random covers a given special point. Out of the $19^{2} \pi=361 \pi$ area in which we can place the center of our washer, there is a $5 \pi$ area in which it can be placed to cover $P$. Therefore, the probability $P$ is covered by a randomly placed washer is $(5 \pi) /(361 \pi)=5 / 361$.

However, there's nothing special about the $P$ we examined. For each of the 650 special points, the probability that a randomly placed washer covers that point is $5 / 361$. Therefore, each special point contributes 5/361 to the expected value of the number of special points covered by a randomly placed washer. So, the total expected value of the number of special points covered by a randomly placed washer is
$$650 \cdot \frac{5}{361} \approx 9.003 .$$

Since the expected value of the number of special points covered by a randomly placed washer that overlaps some portion of our circle is greater than 9, there must be some placement of the washer that covers at least 10 special points.

### Exercises

6.3.1 There are 20 houses along the shore of a lake. Each is painted one of four colors at random. I laugh if the previous house is the same color. (This includes comparing the first house I see to mine, and comparing each house to the previous house I passed when I finish my journey.) I don't laugh at any other time during my walk. What is the expected value of the number of times that I laugh during my walk?

6.3.2 George has six ropes. He chooses two of the twelve loose ends at random (possibly from the same rope), and ties them together, leaving ten loose ends. He again chooses two loose ends at random and joins them, and so on, until there are no loose ends. Find, with proof, the expected value of the number of loops George ends up with. (Source: USAMTS)

6.3.3 One fair 6-sided die is rolled; let $a$ denote the number that comes up. We then roll $a$ dice; let the sum of the resulting $a$ numbers be $b$. Finally, we roll $b$ dice, and let $c$ be the sum of the resulting numbers. Find the expected value of $c$. (Source: HMMT)

6.3.4★ 51 points are inside a square of side length 1. Prove that we can cover some three of them by a circle with radius $\frac{1}{7}$. Hints: 67, 123

6.3.5★ For any subset $S \subseteq\{1,2, \ldots, 15\}$, call a number $n$ an anchor for $S$ if $n$ and $n+\#(S)$ are both members of $S$, where \#($S$) denotes the number of members of $S$. Find the average number of anchors over all possible subsets $S \subseteq\{1,2, \ldots, 15\}$. (Source: HMMT) Hints: 235

## 6.4★ A Coat With Many Patches (Reprise)

### Problems

**Problem 6.9:** Recall Problem 3.24:
I have a coat with area 5. The coat has 5 patches on it. Each patch has area at least 2.5. Prove that 2 patches exist with common area of at least 1. (Source: PSS)

Our goal is to prove it directly using expected value, without using PIE.
(a) Define a function $f$ such that $f(p)$ is the number of patches containing point $p$. If $p$ is chosen at random, compute a lower bound for $E(f(p))$.
(b) Show that $\binom{k}{2} \geq 2k-3$ for any integer $k$ such that $0 \leq k \leq 5$.
(c) Use parts (a) and (b) to show that $E\left(\binom{f(p)}{2}\right) \geq 2$.
(d) Use part (c) to show that some pair of patches must have common area at least 1.

Let's revisit the coat-and-patches problem from Chapter 3. You may recall that when we considered this problem earlier, we solved it using a series of PIE computations. Now let's find a completely different solution, using expected value.

**Problem 6.9:** Recall Problem 3.24:
I have a coat with area 5. The coat has 5 patches on it. Each patch has area at least 2.5.
Prove that 2 patches exist with common area of at least 1. (Source: PSS)
Prove it directly using expected value, without using PIE.

*Solution for Problem 6.9:* We will use a very clever expected value argument (due to Ravi Bopanna).
Here's the general strategy: we know that there are $\binom{5}{2}=10$ pairs of patches. If the result is not true-that is, if every pair of patches has an overlap with an area of less than 1-then the 10 pairs together overlap with an area less than 10. This would mean that a randomly chosen point on the coat (of area 5) would be covered by fewer than $10 / 5=2$ pairs of patches.

So, working the other way, if we can show that a randomly-chosen point on the coat is covered (on average) by at least 2 pairs of patches, then one of the pairs of patches must have overlapping area of at least 1.

Let's try to make this argument a bit more formal. Define a function $f$ where, for any point $p$ on the coat, $f(p)$ is the number of patches containing point $p$. In particular, note that $f(p)$ is a nonnegative integer between 0 and 5 (inclusive) for all points $p$.

The quantity that we're interested in, though, is the number of pairs of patches containing $p$. If $p$ is covered by $f(p)$ patches, then it is covered by $\binom{f(p)}{2}$ pairs of patches. So our goal is to show that
$$E\left(\binom{f(p)}{2}\right) \geq 2 .$$

We don't know anything immediately about $\binom{f(p)}{2}$, but we do have information about $f(p)$. Because the sum of the areas of the patches is at least 12.5, and the area of the coat is 5, we know that
$$E(f(p)) \geq \frac{12.5}{5}=2.5 .$$

Since we're dealing with integer values in this problem, let's double this expression and write it as $E(2f(p)) \geq 5$.

We need to relate $\binom{f(p)}{2}$ to $f(p)$. Since we know that $f(p)$ can only take on the values $0,1,2,3,4,5$, let's just make a chart:

\begin{tabular}{c||c|c|c|c|c|c}
$f(p)$ & 0 & 1 & 2 & 3 & 4 & 5 \\
\hline $2 f(p)$ & 0 & 2 & 4 & 6 & 8 & 10 \\
\hline$\binom{f(p)}{2}$ & 0 & 0 & 1 & 3 & 6 & 10
\end{tabular}

We notice that for our middle two values of $f(p)$, we have
$$\binom{f(p)}{2}=2 f(p)-3,$$
and furthermore, for all possible values of $f(p)$ we have
$$\binom{f(p)}{2} \geq 2 f(p)-3 .$$

Now we can compute our bound for $E\left(\binom{f(p)}{2}\right)$:
$$E\left(\binom{f(p)}{2}\right) \geq E(2 f(p)-3)=2 E(f(p))-3 \geq 2(2.5)-3=2 .$$

Therefore, the expected value of the number of pairs of patches that contain a randomly chosen point is at least 2, and as described at the beginning of our solution, this means that some pair of patches must overlap with an area of at least 1.

## 6.5 Summary

- To compute the expected value of a complicated event, think about breaking up the event into easier-to-manage components. If the value of an event is the sum of values of several intermediate components, then we can compute the expected value of each component and sum them to get the expected value of the overall event.
- More precisely, if $X_{1}, X_{2}, \ldots, X_{n}$ are events, then
$$E\left(X_{1}+X_{2}+\cdots+X_{n}\right)=E\left(X_{1}\right)+E\left(X_{2}\right)+\cdots+E\left(X_{n}\right)$$
- This works even if the events are not independent: the expected value of a sum of events is always the sum of the expected values of the individual events.
- Expected value can also be used in geometric optimization problems.

## Review Problems

**Problem 6.10:** I have $m n$ identical game pieces. Each one is a square with side length 2 inches. Each piece has a quarter circle drawn on it with its center at one of the corners and with radius 1. If I put the game pieces in an $m \times n$ grid, what is the expected value of the number of full circles I form?

**Problem 6.11:** A 10-digit binary number with four 1's is chosen at random. What is its expected value?

**Problem 6.12:** Five balls numbered 1 through 5 are in a bin. You draw them out one at a time, without replacement. Every time the number on the drawn ball matches the number of the draw, you win a dollar. For example, if you draw ball \#2 on the second draw, you win a dollar for that draw. What is the expected amount of your winnings?

**Problem 6.13:** The Happy Animals Kennel has 18 cages in a row. It will allocate 6 to dogs and 12 to cats. Let $A$ be the number of times in the row of cages that a dog cage and a cat cage are adjacent. For example, in the arrangement $c d c d d d c d c c c c c c d c c c$, we have $A=8$. Given that the kennel will choose an arrangement at random from among all the possible arrangements, find the expected value of $A$.

**Problem 6.14:** Select numbers $a$ and $b$ between 0 and 1 independently and at random, and let $c$ be their sum. Let $A, B$, and $C$ be the results when $a, b$, and $c$, respectively, are rounded to the nearest integer. (Assume that $\frac{1}{2}$ is rounded up to 1, and similarly that $n+\frac{1}{2}$ is rounded up to $n+1$ for all nonnegative integers $n$.)
(a) What is the probability that $A+B=C$?
(b) Find $E(C-(A+B))$.
(c) Suppose $a_{1}, a_{2}, \ldots, a_{100}$ are chosen randomly between 0 and 1, and let $c=a_{1}+a_{2}+\cdots+a_{100}$. As before, let $A_{i}$ be the result when $a_{i}$ is rounded to the nearest integer (for all $1 \leq i \leq 100$), and let $C$ be the result when $c$ is rounded to the nearest integer. Find $E\left(C-\left(A_{1}+A_{2}+\cdots+A_{100}\right)\right)$.
(Source: AMC)

**Problem 6.15:** Suppose that in the country of Aopslandia:
- $20 \%$ of families have no children
- $20 \%$ of families have exactly 1 child
- $30 \%$ of families have exactly 2 children
- $20 \%$ of families have exactly 3 children
- $10 \%$ of families have exactly 4 children
- no families have more than 4 children

A child is chosen at random. What is the expected number of siblings of the child?

## Challenge Problems

**Problem 6.16:** Fifteen freshmen are sitting in a circle around a table, but the course assistant (who remains standing) has made only six copies of today's handout. No freshman should get more than one handout, and any freshman who does not get one should be able to read a neighbor's. If the freshmen are distinguishable but the handouts are not, how many ways are there to distribute the six handouts subject to the above conditions? (Source: HMMT) Hints: $345,301,87$

**Problem 6.17:** Show that we can color the elements of the set $S=\{1,2, \ldots, 2007\}$ with 4 colors such that any subset of $S$ with 10 elements, whose elements form an arithmetic sequence, is not all one color. (Source: MO) Hints: 33, 185

**Problem 6.18:** For any positive integer $n$, let $p_{n}(k)$ be the number of permutations of the set $\{1,2, \ldots, n\}$ that have exactly $k$ fixed points. (A fixed point of a permutation is an element $i$ such that $i$ is in the $i^{\text {th }}$ position of the permutation. For example, the permutation $(3,2,5,4,1)$ of $\{1,2,3,4,5\}$ has two fixed points: the 2 (in the $2^{\text {nd }}$ spot) and the 4 (in the $4^{\text {th }}$ spot).) Prove that $\sum_{k=0}^{n} k p_{n}(k)=n!$. (Source: IMO) Hints: 3

**Problem 6.19★:** There are several circles inside a square with side length 1. The sum of the circumferences of the circles is 10. Prove that there exists a line that intersects at least 4 of the circles. Hints: 43, 177

**Problem 6.20★:** A standard 52-card deck is shuffled, and cards are turned over one-at-a-time starting with the top card. What is the expected number of cards that will be turned over before we see the first Ace? (Recall that there are 4 Aces in the deck). Hints: 325, 52

**Problem 6.21★:** In a competition, there are $a$ contestants and $b$ judges, where $b \geq 3$ is an odd integer. Each judge rates each contestant as either "pass" or "fail." Suppose that $k$ is a number such that, for any two judges their ratings coincide for at most $k$ contestants. Prove that $\frac{k}{a} \geq \frac{b-1}{2 b}$. (Source: IMO) Hints: 202
