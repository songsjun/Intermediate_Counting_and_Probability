# Chapter 7: Distributions

*I resolved to stop accumulating and begin the infinitely more serious and difficult task of wise distribution. - Andrew Carnegie*

## 7.1 Introduction

If you read Introduction to Counting & Probability, then you're already a bit familiar with a distribution. Basically, whenever we have to assign (or "distribute") indistinguishable items among distinguishable people or objects, we have a distribution problem.

In this chapter, we'll start by looking at the basic problem: distributing indistinguishable objects to distinguishable recipients, such that each recipient receives at least one object. This problem is well understood, and its solution is fairly easy, although it requires a slight bit of cleverness.

However, it turns out the solutions to many more complicated distribution problems can be put into 1-1 correspondence with the solutions of our basic distribution problem. In other problems, we can find a different 1-1 correspondence to relate a distribution to a different problem that we know how to solve. In the most difficult sort of distribution problem, we'll have to think "outside the box" and come up with a more clever solution.

An important lesson to learn about solving distribution problems is not to rely on a formula to solve them. Instead, reason out the answer each time you're presented with a distribution. This will not only minimize the possibility of incorrectly solving basic problems, but also increase your success at solving more difficult distribution problems. Also, many seemingly-difficult counting problems are really distribution problems in disguise. Once you have a better understanding of how to solve distribution problems, you will be able to use this knowledge to solve an even wider variety of counting problems.

> **Extra!** Of all things, good sense is the most fairly distributed: everyone thinks he is so well supplied with it that even those who are the hardest to satisfy in every other respect never desire more of it than they already have. - Rene Descartes

## 7.2 Basic Distributions

### Problems

**Problem 7.1:** A working crew of 4 people just finished work on your yard. You pay the crew $\$ 200$, using ten $\$ 20$ bills. In how many ways can the four crew members divide the 10 bills among themselves if each member must get at least one bill? Assume the crew members are distinct, but the \$20 bills are not.

**Problem 7.2:** In how many ways can I pass out 11 identical lollipops to 6 kids, if each kid must receive at least one lollipop?

**Problem 7.3:** In how many ways can we distribute $n$ indistinguishable items into $k$ distinguishable boxes, if each box must contain at least one item?

**Problem 7.4:** How many quadruples $(a, b, c, d)$ of positive integers are solutions to $a+b+c+d=17$?

The basic idea of a distribution is simple. We have a bunch of indistinguishable objects that we want to distribute into distinguishable piles. We don't care which specific objects end up in each pile, just how many of them end up in each pile.

Here's a basic example:

**Problem 7.1:** A working crew of 4 people just finished work on your yard. You pay the crew $\$ 200$, using ten $\$ 20$ bills. In how many ways can the four crew members divide the 10 bills among themselves if each member must get at least one bill? Assume the crew members are distinct, but the $\$ 20$ bills are not.

*Solution for Problem 7.1:* This is a distribution problem because we don't care which specific $\$ 20$ bills go to which people; we only care about how many $\$ 20$ bills each person gets. The bills are indistinguishable, but the people are distinguishable.

It is possible to solve this problem through a lengthy casework process. This is somewhat tedious, but leads to the interesting Hockey Stick identity. (See Chapter 13 of Introduction to Counting & Probability if you'd like to see this method.) Here, we will show only the faster, more clever solution.

Imagine that we arrange the ten $\$ 20$ bills in a row, where each "\$" denotes a bill:
$\$ \$ \$ \$ \$ \$ \$ \$ \$ \$$
We don't care which specific bills each person receives, since the bills are indistinguishable. We only care how many bills each person receives. So we can assume that the first person takes some number of bills from the left side of the row, then the next person takes some bills from those remaining at the left side of the row, and so on. For example, if person \#1 gets $\$ 80$, person \#2 gets $\$ 40$, person \#3 gets \$60, and person \#4 gets \$20, we can think of that as:

Better yet, we can place "dividers" between the \$'s to separate them into groups:
$$\$ \$ \$ \$|\$ \$| \$ \$ \$ \mid \$$$

In order to divide the $10 \$$ 's into 4 groups, we need to insert 3 dividers. Since a divider can be placed between any pair of \$'s and there are 9 consecutive pairs, we have 9 "slots" to choose from in which to insert the dividers. Note that we can place at most one divider into any slot, since we need to guarantee that each person receives a positive number of bills.

To use our more formal language, there is a 1-1 correspondence between
{\# of ways to distribute 10 \$'s among 4 people} $\leftrightarrow$ {\# of ways to insert 3 dividers into 9 slots}.
The right side of the above correspondence is easy to count: we can place 3 dividers into 9 slots in $\binom{9}{3}=84$ ways, since we simply have to choose 3 of the 9 slots in which to place dividers. So there are 84 ways to distribute the money.

Let's see another example before going to the general case.

**Problem 7.2:** In how many ways can I pass out 11 identical lollipops to 6 kids, if each kid must receive at least one lollipop?

*Solution for Problem 7.2:* We can arrange the 11 lollipops in a row (we will use **x** to represent a lollipop):
$\mathbf{x} \mathbf{x} \boldsymbol{x} \mathbf{x} \boldsymbol{x} \mathbf{x} \boldsymbol{x} \boldsymbol{x} \boldsymbol{x} \boldsymbol{x}$
To divide this into 6 groups, we need to insert 5 dividers. The first kid then gets the leftmost group, the next kid gets the next group, and so on. For example, to give 2 lollipops to each of the first two kids, 1 to each of the next three, and 4 to the last kid, we insert dividers as:
$\mathbf{x x} \boldsymbol{|} \mathbf{x x} \boldsymbol{| x} \boldsymbol{| x} \boldsymbol{| x} \boldsymbol{| x x x} \boldsymbol{x}$
There are 10 slots into which we can insert the dividers, and we must choose 5 of them. Therefore there are $\left(\frac{10}{5}\right)=252$ ways to give out the lollipops.

Having seen a couple of examples, we should have an idea how to handle the general problem.

**Problem 7.3:** In how many ways can we distribute $n$ indistinguishable items into $k$ distinguishable boxes, if each box must contain at least one item?

*Solution for Problem 7.3:* We use the same general idea that we used in the two previous examples. Imagine arranging the $n$ items in a line. In order to divide them into $k$ groups, we need to insert $k-1$ dividers. There are $n-1$ slots between items into which the dividers can be inserted, and we need to choose $k-1$ of these slots.

Formally, we have a 1-1 correspondence:
$$\left\{\begin{array}{l}
\text { Ways to distribute } n \text { indistinguishable items } \\
\text { into } k \text { distinguishable boxes, with each box } \\
\text { getting at least } 1 \text { item }
\end{array}\right\} \leftrightarrow\left\{\begin{array}{l}
\text { Ways to insert } k-1 \text { dividers into } n-1 \\
\text { slots }
\end{array}\right\} .$$

Since there are $\binom{n-1}{k-1}$ ways to choose $k-1$ of the $n-1$ slots to receive dividers, we conclude using the 1-1 correspondence described above that there are $\binom{n-1}{k-1}$ ways to distribute the items.

We can summarize our results as follows:

> **Concept:** As we often say, don't memorize the above formula! Instead, understand the concept that leads to the formula. That is, when presented with a distribution problem, your thought process should be to think of dividers and slots, not to try to recall the above formula from memory.

Distributions often turn up in counting the number of solutions to certain Diophantine equations. (A Diophantine equation is an equation in which we are looking for integer solutions.) Let's see an example.

**Problem 7.4:** How many quadruples $(a, b, c, d)$ of positive integers are solutions to $a+b+c+d=17$?

*Solution for Problem 7.4:* This is exactly the same as distributing 17 indistinguishable items into 4 distinguishable boxes, with the condition that each box must get at least one item. The "items" are copies of the number 1, and the "boxes" are $a, b, c$, and $d$. For example, setting $a=6$ means that we are placing six of the "1" "items" into the "box" labeled "$a$." The fact that we are looking for positive integer solutions means that each "box" must receive at least one 1.

More formally, we have the correspondences
$$\begin{aligned}
\{\text { Positive integer solutions to } a+b+c+d=17\} & \leftrightarrow\left\{\begin{array}{l}
\text { Ways to distribute } 17 \text { 1's into four variables, } \\
\text { such that each variable receives at least one } 1
\end{array}\right\} \\
& \leftrightarrow\{\text { Ways to insert } 3 \text { dividers into } 16 \text { slots }\}
\end{aligned}$$

Therefore there are $\binom{16}{3}=560$ solutions.

### Exercises

7.2.1 In how many ways can 10 kindergarten children eat 30 cookies, if each child must eat at least one cookie?

7.2.2 Suppose the head of my 4-person work crew insists that she get at least 3 of the $10 \$ 20$ bills that will be distributed to the crew. Each of the other members will get at least one. In how many ways can the bills be distributed?

7.2.3 Find the number of positive integer solutions to the equation $a+b+c=100$.

7.2.4 In how many ways can 8 licorice sticks and 10 chocolate bars be distributed to 5 kids, if:
(a) each kid must receive at least one piece of candy of each type?
(b) each kid must receive at least one piece of candy, but no kid can receive both types of candy? Hints: 171

## 7.3 Distributions With Extra Conditions

### Problems

**Problem 7.5:** How many solutions does the equation $v+w+x+y+z=21$ have, where $v, w, x, y, z$ are all nonnegative integers?
(a) Why is the answer not $\binom{20}{4}$, using the formula that we learned in the previous section?
(b) How can we change this problem to look like a problem that we considered in the previous section?
(c) What is the answer to this problem?

**Problem 7.6:** In how many ways can we distribute $n$ indistinguishable balls into $k$ distinguishable boxes, if some box(es) may remain empty?

**Problem 7.7:** In how many ways can I distribute 20 candy canes to 7 children, if each child must receive at least one, and two of the children are twins who insist on receiving the same amount?
(a) What are the possibilities for the amounts of candy that I can give to the twins?
(b) For each possible amount in (a), in how many ways can I distribute the rest of the candy to the other 5 children?
(c) Use your answers to (b) to finish the problem.

**Problem 7.8:** In how many ways can I give out 15 pieces of candy to 4 kids, with each kid getting at least one piece, if the oldest kid insists on receiving more pieces than any other kid?
(a) Explain why this solution does not work: The number of ways to distribute 15 candies to 4 kids is $\binom{14}{3}=364$. But only $\frac{1}{4}$ of these have the oldest kid with the most candy (by symmetry), so the number of distributions satisfying the condition of the problem is $364 / 4=91$.
(b) What are the possible amounts of candy that we could give to the oldest kid?
(c) For each possible amount in (b), in how many ways can we distribute the rest of the candy to the other kids?
(d) Finish the problem.

**Problem 7.9:** How many solutions does $a+b+c+d=27$ have in nonnegative integers, if $a$ must be even and $d$ must be a power of 3?

In the last section, we discussed the basic distribution problem of counting the number of ways to distribute $n$ indistinguishable items into $k$ distinguishable boxes, such that each box has at least one item. However, many distribution problems will have different conditions on the types of allowable distributions. The most common of these is eliminating the condition that every box must contain at least one item. Let's see an example of this:

**Problem 7.5:** How many solutions does the equation $v+w+x+y+z=21$ have, where $v, w, x, y, z$ are all nonnegative integers?

*Solution for Problem 7.5:* We can't use our straightforward "dividers and slots" approach here, because we have to allow for the fact that some of the variables might be 0. But can we convert it to one of our earlier distributions?

> **Concept:** When faced with a problem that you don't initially know how to do, try to convert it into a problem that you do know how to do.

What if we force the variables to be positive?
Let $v^{\prime}=v+1, w^{\prime}=w+1$, and so on. If $v, w, \ldots$ are nonnegative, then $v^{\prime}, w^{\prime}, \ldots$ are positive, and vice versa. Then
$$v^{\prime}+w^{\prime}+x^{\prime}+y^{\prime}+z^{\prime}=(v+1)+(w+1)+(x+1)+(y+1)+(z+1)=(v+w+x+y+z)+5=26 .$$

Aha-now we want to count the positive solutions to $v^{\prime}+w^{\prime}+x^{\prime}+y^{\prime}+z^{\prime}=26$. We know how to do that:
As usual, we could write this as a correspondence:
$\{$ Nonnegative solutions to $v+w+x+y+z=21\} \leftrightarrow\left\{\right.$ Positive solutions to $v^{\prime}+w^{\prime}+x^{\prime}+y^{\prime}+z^{\prime}=26$
$\leftrightarrow$ \{Ways to insert 4 dividers into 25 slots\}
So there are $\binom{25}{4}=12650$ solutions.

We can use our insight from Problem 7.5 to solve the general form of this distribution problem.

**Problem 7.6:** In how many ways can we distribute $n$ indistinguishable balls into $k$ distinguishable boxes, if some box(es) may remain empty?

*Solution for Problem 7.6:* Here's the general idea:
1. Add $k$ balls to our group of balls, so that we have $n+k$ balls total.
2. Distribute the $n+k$ balls into the $k$ boxes, leaving no box empty.
3. Remove 1 ball from each box.

Clearly this operation is reversible, so this establishes 1-1 correspondences:
$$\begin{aligned}
\left\{\begin{array}{l}
\text { Distributions of } n \text { balls to } k \text { boxes, } \\
\text { with some box(es) possibly empty }
\end{array}\right\} & \leftrightarrow\left\{\begin{array}{l}
\text { Distributions of } n+k \text { balls to } k \text { boxes, } \\
\text { with no boxes empty }
\end{array}\right\} \\
& \leftrightarrow\{\text { Insertion of } k-1 \text { dividers into } n+k-1 \text { slots }\} .
\end{aligned}$$

Therefore we can do this distribution in $\binom{n+k-1}{k-1}$ ways.

> **Important:** The number of ways to distribute $n$ indistinguishable balls in $k$ distinguishable boxes, where some box(es) may remain empty, is
> $$\binom{n+k-1}{k-1} .$$

> **Concept:** You know what I'm going to say (I hope): don't memorize this formula. Understand where it comes from.

We've now handled the two most common distributions: those with no restrictions at all, and those in which no box can be left empty. But many distribution problems tack on more exotic conditions. Let's do a couple of examples.

**Problem 7.7:** In how many ways can I distribute 20 candy canes to 7 children, if each child must receive at least one, and two of the children are twins who insist on receiving the same amount?

*Solution for Problem 7.7:* Unfortunately, there's no "slick" way of solving this problem. We're going to have to get our hands dirty with some casework.

The twins can each receive between 1 and 7 pieces of candy (if they receive more than 7 each, then there's not enough candy left for the other 5 kids). This leaves the rest of the candy to be distributed to the other 5 kids, which we know how to count.

Here's a chart showing the cases:

\begin{tabular}{|l|l|l|}
\hline \# of candies given to each of the twins & \# of candies remaining to be given to the other 5 kids & \# of ways to distribute remaining candy \\
\hline 1 & 18 & $\binom{17}{4}$ \\
\hline 2 & 16 & $\binom{15}{4}$ \\
\hline 3 & 14 & $\binom{13}{4}$ \\
\hline 4 & 12 & $\binom{11}{4}$ \\
\hline 5 & 10 & $\binom{9}{4}$ \\
\hline 6 & 8 & $\binom{7}{4}$ \\
\hline 7 & 6 & $\binom{5}{4}$ \\
\hline
\end{tabular}

So the number of possible distributions is
$$\binom{17}{4}+\binom{15}{4}+\binom{13}{4}+\binom{11}{4}+\binom{9}{4}+\binom{7}{4}+\binom{5}{4}=2380+1365+715+330+126+35+5=4956 .$$

There doesn't seem to be any good way to simplify this answer to a nicer expression, so there probably wasn't a simpler method that we could have used.

> **Concept:** If you get a "nice" answer, then there's often a relatively simple combinatorial explanation for the simpler answer, and a relatively simple method of obtaining it. However, if you get an "ugly" answer, then there's probably not a simple method for getting it.

**Problem 7.8:** In how many ways can I give out 15 pieces of candy to 4 kids, with each kid getting at least one piece, if the oldest kid insists on receiving more pieces than any other kid?

*Solution for Problem 7.8:* It might be tempting to use this quick "shortcut":

> **Bogus Solution:** The number of ways to distribute 15 candies to 4 kids is $\binom{14}{3}=364$. But only $\frac{1}{4}$ of these have the oldest kid with the most candy (by symmetry), so the number of distributions satisfying the condition of the problem is $364 / 4=91$.

This doesn't work since not every distribution will have a unique kid with the most candy-there might be a tie. For example, if I gave 5 to each of the first two kids, 3 to the third kid, and 2 to the last kid, then there's no kid with more pieces than any other kid. This isn't allowed: the oldest kid must have more pieces than any other kid. If we could somehow compute the number of distributions that have a unique kid with the most candy, then it would be valid to take $\frac{1}{4}$ of that number to get our answer. Unfortunately, there's no easy way to compute that.

So instead, once again, we appeal to casework. This time, our cases will be determined by the number of candies that we give to the oldest (greedy) kid.

We can give the oldest kid any amount of candies between 5 and 12 inclusive. If we give him more than 12, then we don't have enough candy left so that each of the other 3 kids gets at least one piece. On the other hand, if we give him 4 or fewer, then there are at least 11 pieces left, so by the Pigeonhole Principle at least one of the other 3 kids must receive at least 4 pieces, which is not allowed.

If we give the oldest kid between 7 and 12 pieces (inclusive), then we can distribute the rest of the candy to the other 3 kids however we want, since there's no way to give one of these kids as many as the oldest. (Remember that each kid must get at least 1 piece.) So these cases give
$$\binom{2}{2}+\binom{3}{2}+\cdots+\binom{7}{2}=1+3+6+10+15+21=56$$
possible distributions.

> **Sidenote:** Note that, in the line above, we could have used the Hockey Stick identity:
> $$\binom{2}{2}+\binom{3}{2}+\cdots+\binom{7}{2}=\binom{8}{3}=56 .$$
> (If you're not familiar with the Hockey Stick identity, we'll see it in greater detail in Chapter 12.) As we just mentioned at the end of the last problem, a simple answer like $\binom{8}{3}$ often means a simple explanation. Can you find a simple combinatorial explanation to why, if we give the oldest kid between 7 and 12 pieces (inclusive), the number of ways to distribute the candy is just $\binom{8}{3}$?

If we give the oldest kid 6 pieces, then there are 9 pieces left. Normally, this would result in $\binom{8}{2}=28$ distributions, but we cannot distribute the candies in groups of $6,2,1$ or $7,1,1$ in any order, since that would give some kid at least as many candies as the oldest kid has. So we must exclude these $3!+\binom{3}{1}=9$ distributions (since they can be in any order), and hence this case contributes $28-9=19$ distributions.

If we give the oldest kid 5 pieces, then there are 10 pieces left. If none of the three remaining kids can have more than 4 pieces, then each kid must have at least 2 pieces (check this for yourself). The only way to do this is to distribute the candies in groups of $4,4,2$ or in groups of $4,3,3$. Each of these groups can be arranged in 3 ways (for each group, we merely have to choose which kid gets the different number of pieces), so there are $3 \times 2=6$ valid distributions in this case. As a check, we can list them (since there are only 6 of them):
$$5,4,4,2, \quad 5,4,2,4, \quad 5,2,4,4, \quad 5,4,3,3, \quad 5,3,4,3, \quad 5,3,3,4 .$$

Therefore, the number of distributions is $56+19+6=81$.

**Problem 7.9:** How many solutions does $a+b+c+d=27$ have in nonnegative integers, if $a$ must be even and $d$ must be a power of 3?

*Solution for Problem 7.9:* Once again, there's no nice way to do this except by getting into casework. We generally want to start by looking at the most restrictive condition first, which in this case is the condition that $d$ must be a power of 3.

> **Concept:** When dealing with restrictions, it usually is best to deal with the most restrictive condition first.

This means that $d$ must be $27,9,3$, or 1. We can now make a chart.

\begin{tabular}{c|c|c|c}
$d$ & Possible values for $a$ & \# of choices for $b, c$ & Number of solutions \\
\hline 27 & 0 & 1 & 1 \\
9 & $0,2, \ldots, 18$ & $19,17, \ldots, 1$ & 100 \\
3 & $0,2, \ldots, 24$ & $25,23, \ldots, 1$ & 169 \\
1 & $0,2, \ldots, 26$ & $27,25, \ldots, 1$ & 196
\end{tabular}

So there are $1+100+169+196=466$ solutions satisfying the conditions.

### Exercises

7.3.1 Find the number of nonnegative integer solutions to the equation $u+v+w+x+y=22$.

7.3.2
(a) Pat wants to buy four donuts from an ample supply of three types of donuts: glazed, chocolate, and powdered. How many different selections are possible?
(b) Pat is to select six cookies from a tray containing only chocolate chip, oatmeal, and peanut butter cookies. There are at least six of each of these three kinds of cookies on the tray. How many different assortments of six cookies can be selected?
(Source: AMC)

7.3.3 Compute the number of distinct ways in which 77 one-dollar bills can be distributed to 7 people so that no person receives less than $\$ 10$. (Source: ARML)

7.3.4 Find the number of integer solutions to the equation $x+y+z=10$ if $x, y$, and $z$ are all less than 20.

7.3.5★ Find the number of positive integer solutions to $w+x+y+z<25$. Hints: 39, 12

7.3.6★ Andrew has 10 candy bars, 10 packages of jelly beans, 10 lollipops, and 10 packs of chewing gum, and Andrew has two sisters. In how many ways can Andrew distribute the candies between his sisters, so that each sister gets 20 items total? Hints: 256

## 7.4 More Complicated Distribution Problems

### Problems

**Problem 7.10:** A triomino game piece has three numbers on it from 1 to 9. Two pieces are considered different if they have different numbers; in other words, the order of the numbers on the piece doesn't matter. For example, the two triominos shown below are considered the same. A piece may have a number repeated, or have the same number in all three positions. How many distinct triomino pieces are there?

**Problem 7.11:** How many cubic polynomials $f(x)$ with positive integer coefficients are there such that $f(1)=9$?

**Problem 7.12:** How many 15-digit base 4 numbers are there with eight 0's that appear in 3 groups? (For example, 230001330210000 is one such number; the 3 groups are 000, 0, and 0000.)

**Problem 7.13:** How many arrangements of the word PROBABILISTIC have no two I's appearing consecutively?

In most cases, a distributions problem is not going to come with a huge flashing sign that says "DISTRIBUTION!" in big neon letters. You are often going to have to look carefully to see that a more complicated problem involves distributions.

**Problem 7.10:** A triomino game piece has three numbers on it from 1 to 9. Two pieces are considered different if they have different numbers; in other words, the order of the numbers on the piece doesn't matter. For example, the two triominos shown below are considered the same. A piece may have a number repeated, or have the same number in all three positions. How many distinct triomino pieces are there?

*Solution for Problem 7.10:* We could solve this pretty easily using casework-let's do so for practice, before seeing the solution using distributions.

**Case 1:** Triominos with all three numbers the same. There are 9 of these.

**Case 2:** Triominos with two of one number and a third different number. There are 9 choices for the number that appears twice, then 8 choices for the different third number, so there are 72 of these.

**Case 3:** Triominos with three different numbers. There are $\binom{9}{3}=84$ of these.

So there are $9+72+84=165$ possible triominos.

But we can also solve this problem using distribution theory. If we let $a_{1}, a_{2}, \ldots$ represent the number of 1's, 2's, ... on a triomino, then there is a 1-1 correspondence between triominos and nonnegative integer solutions to
$$a_{1}+a_{2}+\cdots+a_{9}=3 .$$

These also know that these solutions are in 1-1 correspondence to positive integer solutions of
$$b_{1}+b_{2}+\cdots+b_{9}=12,$$
where $b_{i}=a_{i}+1$. And we know that these solutions are in 1-1 correspondence with the number of ways to insert 8 dividers into 11 slots. So the answer is $\binom{11}{8}=\binom{11}{3}=165$.

> **Concept:** Solving a problem via two different methods is a good way to check your answer.

The main advantage of the distribution solution to Problem 7.10 is that it scales upward easily. For example, if you were asked to count the number of hexominos (hexagons with six numbers from 1 through 9 on them), the casework would be really messy, but the distribution-based solution would be quick. (You can see for yourself in the Exercises.)

Distributions can sometimes show up in unusual places, as we see in the next problem.

**Problem 7.11:** How many cubic polynomials $f(x)$ with positive integer coefficients are there such that $f(1)=9$?

*Solution for Problem 7.11:* We can write a such a cubic polynomial as $f(x)=a x^{3}+b x^{2}+c x+d$. Plugging in $x=1$ gives us $9=a+b+c+d$. So it's just a distribution problem! More formally, we have a 1-1 correspondence:
$$\begin{aligned}
\left\{\begin{array}{l}
\text { Polynomials } f(x)=a x^{3}+b x^{2}+c x+d \text { with } \\
\text { positive integer coefficients such that } f(1)=9
\end{array}\right\} & \leftrightarrow\{\text { Positive integer solutions to } 9=a+b+c+d\} \\
& \leftrightarrow\{\text { Ways to insert } 3 \text { dividers into } 8 \text { slots }\}
\end{aligned}$$

Thus there are $\binom{8}{3}=56$ such cubic polynomials.

**Problem 7.12:** How many 15-digit base 4 numbers are there with eight 0's that appear in 3 groups? (For example, 230001330210000 is one such number; the 3 groups are 000, 0, and 0000.)

*Solution for Problem 7.12:* We think about this problem constructively: how would we build such a number? There are basically three steps:
- Decide how to break up the 0's into 3 groups;
- Decide where to place the groups of 0's within the 15-digit number;
- Choose the remaining non-0 digits.

We can count the number of choices for each step, then multiply (since the steps are independent) to get the total number of such numbers.

First, we break up the 0's into 3 groups. If the sizes of the groups are $a, b, c$, then we must have $a, b, c$ all positive and $a+b+c=8$, the total number of 0's. This is a basic distribution problem: it's the same as inserting 2 dividers into 7 possible slots, so there are $\binom{7}{2}=21$ ways that we can break up the 0's into 3 groups.

Second, we have to place these groups into the 15-digit number. If 8 of the digits are 0, then the other 7 digits are non-0. We can think of the 3 groups of 0's as dividers that divide the non-0 digits apart. The slightly tricky thing to be aware of is that we cannot place a group of 0's at the beginning, but we can place it at the end. So there are 7 possible slots for our 3 groups (6 in the middle and 1 at the right end), hence there are $\binom{7}{3}=35$ ways that we can insert the digits.

Finally, there are 7 non-0 digits, and each can be 1, 2, or 3. So there are $3^{7}=2187$ choices for the non-0 digits.

Combining our counts, we see that there are $(21)(35)(2187)=1,607,445$ such numbers.

**Problem 7.13:** How many arrangements of the word PROBABILISTIC have no two I's appearing consecutively?

*Solution for Problem 7.13:* There are 3 I's and 10 other letters. We can think of placing the 3 I's into slots between 2 other letters, or at the beginning or the end of the word. Therefore, there are 11 possible positions for the I's, and 3 of them to place, so there are $\binom{11}{3}=165$ allowed positions for the I's. Then the remaining 10 letters can be arranged in $10!/ 2$ ways (don't forget to divide by 2 since there are two B's!). Hence, the total number of allowed arrangements is $165(10!) / 2=15(11!) / 2$.

For practice, let's also compute this using complementary counting and PIE, to check our work. There are $13!/ 3!2$ ! arrangements of the letters without any restrictions. There are $12!/ 2$ ! arrangements with at least two I's together. There are $11!/ 2$ ! arrangements with all three I's together. So, by PIE, the total number of allowed arrangements is
$$\frac{13!}{3!2!}-\frac{12!}{2!}+\frac{11!}{2!}=11!\left(13-6+\frac{1}{2}\right)=11!\left(\frac{15}{2}\right),$$
which (of course) matches our distribution-based answer.

### Exercises

7.4.1 Calculate the number of possible hexominos: 6-sided game pieces with 6 numbers from 1 through 9 (inclusive), where a number may be repeated and where we don't care about the position of the numbers, just how many of each number are on each piece.

7.4.2 ARMLovian, the language of the fair nation of ARMLovia, consists only of words using the letters A, R, M, and L. The words can be broken up into syllables that consist of exactly one vowel, possibly surrounded by a single consonant on either or both sides. For example, LAMAR, AA, RA, MAMMAL, AMAL, LALA, MARLA, RALLAR, and AAALAAAAAMA are ARMLovian words, but MELMRLM, MAMMMAL, MMMMM, L, ARM, ALARM, LLAMA, and MALL are not. Compute the number of 7-letter ARMLovian words. (Source: ARML) Hints: 271

7.4.3 A gardener plants 3 maple trees, 4 oak trees, and 5 birch trees in a row. He plants them in random order, each arrangement being equally likely. Find the probability that no two birch trees are next to each other. (Source: AIME) Hints: 194

7.4.4★ How many degree 6 polynomials $f(x)$ with positive integer coefficients are there such that $f(1)=30$ and $f(-1)=12$? Hints: 32, 36

7.4.5★ The Aopslandia lottery consists of randomly drawing 6 balls (without regard to order) from a bin of 44 balls numbered 1 through 44. A group of citizens is concerned that the lottery may be rigged, because they have noticed that, historically, over $50 \%$ of the drawings have resulted in at least one pair of consecutively numbered balls being drawn. Should these citizens be concerned? Hints: 210, 15

> **Extra!** The speed of communications is wondrous to behold. It is also true that speed can multiply the distribution of information that we know to be untrue. - Edward R. Murrow

## 7.5 Summary

- Distributions are problems involving placing indistinguishable items into distinguishable boxes.
- If each box must contain a positive number of items, we can think of arranging the items in a row, and placing dividers between the items to divide them into the requisite number of boxes. Thinking of the problem in this way, we see that if there are $n$ items to divide into $k$ boxes, then we must place $k-1$ dividers among $n-1$ slots, and thus there are $\binom{n-1}{k-1}$ possible distributions.
- If some of the boxes may be empty, then add 1 extra item to each box, and take advantage of the 1-1 correspondences:
$$\begin{aligned}
\left\{\begin{array}{l}
\text { Distributions of } n \text { items to } k \text { boxes, } \\
\text { with some box(es) possibly empty }
\end{array}\right\} & \leftrightarrow\left\{\begin{array}{l}
\text { Distributions of } n+k \text { items to } k \text { boxes, } \\
\text { with no boxes empty }
\end{array}\right\} \\
& \leftrightarrow\{\text { Insertion of } k-1 \text { dividers into } n+k-1 \text { slots }\} .
\end{aligned}$$
- Don't memorize the formulas. Understand where they come from. That is to say: when presented with a distribution problem, your thought process should be to think of dividers and slots, not to try to recall a formula from memory.
- Distribution problems with extra conditions may require casework or some other clever manipulation to convert it to a distribution problem that we know how to do.
- Many problems are distribution problems in disguise.

Here are some general problem-solving concepts that we saw in this chapter:

> **Concept:** When faced with a problem that you don't initially know how to do, try to convert it into a problem that you do know how to do.

> **Concept:** If you get a "nice" answer, then there's often a relatively simple combinatorial explanation for the simpler answer, and a relatively simple method of obtaining it. However, if you get an "ugly" answer, then there's probably not a simple method for getting it.

> **Concept:** When dealing with restrictions, it usually is best to deal with the most restrictive condition first.

> **Concept:** Solving a problem via two different methods is a good way to check your answer.

## Review Problems

**Problem 7.14:** Determine how many triples $(x, y, z)$ satisfy each of the following:
(a) $x+y+z=10$ and $x, y, z$ are positive integers.
(b) $x+y+z=10$ and $x, y, z$ are nonnegative integers.
(c) $x+y+z=10$ and $x, y, z$ are integers no less than -2.
(d) $x+y+z=10$ and $x, y, z$ are positive even integers.

**Problem 7.15:** Find the number of quintuples $\left(x_{1}, x_{2}, x_{3}, x_{4}, x_{5}\right)$ of positive odd integers that satisfy
$$x_{1}+x_{2}+x_{3}+x_{4}+x_{5}=2003 .$$

**Problem 7.16:** I have 8 identical pieces of candy and 4 identical cookies to distribute to 3 children (2 boys and a girl). In how many ways can I do this, if:
(a) each child must receive at least 1 of each type of item?
(b) each child must receive exactly 4 items?
(c) the girl must receive more pieces of candy than either of the boys, and the boys must receive an equal number of cookies?

**Problem 7.17:** How many solutions are there in positive integers to the equation $w+x+y+z=30$ if no variable takes on a value greater than 16?

**Problem 7.18:** In how many ways can the integers from 1 to 36, inclusive, be ordered such that no two multiples of 6 are adjacent?

**Problem 7.19:** How many terms are in the expansion of $(x+y+z)^{100}$? (For example, $(x+y+z)^{2}=x^{2}+y^{2}+z^{2}+ 2 x y+2 x z+2 y z$ has 6 terms.)

**Problem 7.20:** In how many ways can three teachers and eight students sit in the front row of 11 chairs at the auditorium if there must be at least 2 students between each pair of teachers? (Source: AMC)

## Challenge Problems

**Problem 7.21:** 20 chairs are set in a row. 5 people randomly sit in the chairs (no more than one person to a chair, of course!). What is the probability that nobody is sitting next to anybody else? (Source: Mandelbrot) Hints: 6

**Problem 7.22:** In how many ways can a word be formed with 8 A's and 5 B's if every A is next to another A and every B is next to another B? Hints: 121

**Problem 7.23:** Amy flipped a coin 20 times, and got the sequence THHTTTHTTHHTHTTTTTHH. She noticed that 3 times a heads followed a heads, 7 times a tails followed a tails, 4 times a tails followed a heads, and 5 times a heads followed a tails. How many such sequences are possible? Hints: 326, 261

**Problem 7.24★:** A bin has 10 red balls and 8 blue balls. We randomly draw out 6 balls, one at a time, without replacement. What is the probability that, at some point, we choose two consecutive balls that are red? Hints: 305

**Problem 7.25★:** In a certain lottery, 7 balls are drawn at random from $n$ balls numbered 1 through $n$. If the probability that no pair of consecutive numbers is drawn equals the probability of drawing exactly one pair of consecutive numbers, find $n$. (Source: Mandelbrot) Hints: 61
