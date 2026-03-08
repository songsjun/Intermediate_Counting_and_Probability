# Chapter 5: The Pigeonhole Principle

*Discourse is fleeting, but junk mail is forever. - Joe Bob Briggs*

## 5.1 Introduction

Once again, we have a simple concept with a fancy name: the Pigeonhole Principle. It actually has a fancier name, the Dirichlet Principle, after the German mathematician Johann Peter Gustav Lejeune Dirichlet, and an even fancier name, the Dirichlet Box Principle, but it is usually referred to (in the United States) as the Pigeonhole Principle.

Imagine a mailroom with a bunch of small mailboxes (sometimes called pigeonholes). If we have, say, 100 mailboxes in the room, and 101 letters arrived today, then we know that at least 2 of the letters must go in the same pigeonhole. More generally, if there are more letters than pigeonholes, then some pigeonhole must get more than one letter. That's really all there is to it!

Although the Pigeonhole Principle may seem "obvious," it is extremely useful in solving a wide variety of counting problems.

## 5.2 It's Just Common Sense!

### Problems

**Problem 5.1:** Suppose that I have 5 balls and 4 boxes. Prove that, no matter how I place the balls into boxes, at least one box must contain more than 1 ball.

The Pigeonhole Principle couldn't be more simple. It merely states that if we have more objects than slots to place them in, then at least one slot must contain more than one object.

Here's a basic example:

**Problem 5.1:** Suppose that I have 5 balls and 4 boxes. Prove that, no matter how I place the balls into boxes, at least one box must contain more than 1 ball.

*Solution for Problem 5.1:* We can prove this very easily by contradiction. Suppose that the 4 boxes have $2 \cdot b, c$, and $d$ balls in them, respectively. If each box has no more than 1 ball, then $a \leq 1, b \leq 1, c \leq 1$, and $z \leq 1$. Therefore, $a+b+c+d \leq 1+1+1+1=4$. But we know that $a+b+c+d=5$, so $5 \leq 4$. Obviously this is a contradiction, so not all of the boxes can have at most one ball.

We can generalize this simple example:

> **Important:** The Pigeonhole Principle: If I place $k$ balls into $n$ boxes, where $k>n$, then at least one box must contain more than 1 ball.

The proof is essentially the same as in the specific example from Problem 5.1-we will leave it as an evercise.

Don't let all this detail obscure the fact that the Pigeonhole Principle is just common sense.

> **Concept:** The Pigeonhole Principle is just common sense. If you have more items than boxes to place them in, then at least one of the boxes must contain more than one item.

### Exercises

5.2.1 Prove the general statement of the Pigeonhole Principle: If I place $n$ balls into $k$ boxes, with $n>k$, then at least one box must contain more than 1 ball.

5.2.2 Prove that if I flip 3 coins, I must get at least two heads or at least two tails.

5.2.3 How many cards do we have to draw out of a standard 52-card deck in order to guarantee that we draw at least one pair (two cards of matching rank)?

## 5.3 Basic Pigeonhole Problems

### Problems

**Problem 5.2:** I have a drawer with a large number of white, brown, and black socks. How many socks do I have to pull out of the drawer in order to ensure that I get a matching pair?

> **Extra!** I have reached an age where if someone tells me to wear socks, I don't have to. - Albert Einstein

**Problem 5.3:** We wish to prove that given any 6 integers, there are 2 of them whose difference divisible by 5.
(a) Since we want to prove that at least 2 of 6 items share a property, how many "boxes" will we need in order to apply the Pigeonhole Principle?
(b) Given that we are considering divisibility by 5, what would be a natural choice for our boxes?
(c) Finish the problem.

**Problem 5.4:** Given a unit square and 5 points in the square, we wish to prove that there must exist a pair of these points that are at most $\sqrt{2} / 2$ distance apart.
(a) We have 5 points and we wish to show that a pair of them have some property. How many "boxes" will we need to apply the Pigeonhole Principle?
(b) How can we choose our boxes?
(c) How does our choice of boxes in (b) force two points in the same box to be at most $\sqrt{2} / 2$ distance apart?

**Problem 5.5:** A group of 25 people are at a party. Over the course of the party, some of the attendees shake hands with each other. Prove that, at the end of the party, there exist two guests that have shaken hands with the same number of people.

Remember, the general idea of the Pigeonhole Principle is that we have more balls than boxes, so some box must contain more than one ball. Often the main difficulty is trying to decide what the "balls" and the "boxes" are.

**Problem 5.2:** I have a drawer with a large number of white, brown, and black socks. How many socks do I have to pull out of the drawer in order to ensure that I get a matching pair?

*Solution for Problem 5.2:* Since we want two socks of the same color, it makes sense to think of "colors" as our "boxes" for this problem. For example, we can imagine having 3 boxes labeled "White," "Brown," and "Black," and as we pull socks out of the drawer, we put them into the appropriate box.

Since we have 3 colors-white, brown, and black-we need 4 "balls," or socks, to put into these boxes in order to ensure that one box has at least two. For example, if we only pull out 3 socks, we might pull out one of each color (as shown above), and thus would have 1 sock in each box. If we pull out a $4^{\text {th }}$ sock, it will have to go into one of the boxes, and then that box will have 2 socks (a matching pair). Therefore, we need to pull 4 socks out of the drawer.

**Problem 5.3:** Prove that given any 6 integers, there are 2 of them whose difference is divisible by 5.

*Solution for Problem 5.3:* Suppose $x$ and $y$ are integers whose difference is divisible by 5. This means that
$$\frac{x-y}{5}=\frac{x}{5}-\frac{y}{5}$$
is an integer. This only happens when $x$ and $y$ have the same remainder upon division by 5. More formal ways to write this are:
$$5 \mid(x-y) \quad \text { or } \quad x \equiv y \quad(\bmod 5) .$$

Now our course of action is more clear. Our "boxes" for this problem are remainders when dividing by 5. Since we have 6 integers, we may conclude, by the Pigeonhole Principle, that at least two of them must have the same remainder upon division by 5 (since there are only 5 possible remainders: $0,1,2$, 3. or 4). The difference of these two integers will be divisible by 5.

**Problem 5.4:** Given a unit square and 5 points in the square, show that there must exist a pair of these points that are at most $\sqrt{2} / 2$ distance apart.

*Solution for Problem 5.4:* We're looking for a pair of points out of 5 that satisfy a certain condition, so this suggests the Pigeonhole Principle, in which the points are placed into 4 boxes, guaranteeing that at least awo of the points are in the same box. We also want the condition that "two points are in the same box" to imply that "two points are at most $\sqrt{2} / 2$ distance apart." Furthermore, we think of what distance $\sqrt{2} / 2$ represents, and one common distance that should come to mind is the diagonal of a square of side ength $\frac{1}{2}$. We have all the pieces-it remains to assemble them into a solution.

Divide the unit square into four smaller squares of side length $\frac{1}{2}$ as shown in the diagram to the right. By the Pigeonhole Principle, given any 5 points, at least two of them must be in the same small square. These two points then can be apart by at most the diagonal of a strall square, which is $\sqrt{2} / 2$.

> **Concept:** Whenever we have to show that "a pair" of objects or "at least 2" objects share some property, that's our cue to think about the Pigeonhole Principle.

**Problem 5.5:** A group of 25 people are at a party. Over the course of the party, some of the attendees shake hands with each other. Prove that, at the end of the party, there exist two guests that have shaken hands with the same number of people.

*Solution for Problem 5.5:* Since we want to prove that two guests have shaken hands with the same nu-mber of people, it makes sense to think of "\# of handshakes" as our boxes. Since there are 25 people at the party, each person could shake hands with $0,1,2, \ldots, 23$, or 24 of the other people.

Uh-oh. There are 25 numbers in the list $0,1, \ldots, 23,24$, and there are 25 people. We need more people than numbers in order to apply the Pigeonhole Principle. Are we doomed?

No, we're not doomed, because we can't simultaneously have someone who shook no hands (and thus would be in the 0 box) and someone who shook everybody's hand (and thus would be in the 24 200x). So there are really only 24 boxes, and we can apply the Pigeonhole Principle to prove that there must be two people who have shaken the same number of hands.

> **Concept:** Sometimes, before applying the Pigeonhole Principle, we have to do a little work to reduce the number of boxes.

### Exercises

5.3.1 Prove that given any 11 integers, there will be at least two with the same units digit.

5.3.2
(a) What is the maximum number of rooks that can be placed on an $8 \times 8$ chessboard such that each row and column contains no more than 1 rook?
(b) ★ What is the maximum number of bishops that can be placed on an $8 \times 8$ chessboard such that each diagonal contains no more than 1 bishop? Hints: 265

5.3.3 Prove that among any 8 positive integers that sum to 20, there must be a group of them that sums to 4.

5.3.4 What is the size of the largest subset $S$ of $\{1,2,3, \ldots, 50\}$ such that no pair of distinct elements of $S$ has a sum divisible by 7? (Source: AMC)

5.3.5 Prove the general version of Problem 5.3: given any positive integer $n$, and any set of $n+1$ integers, there are 2 of them whose difference is divisible by $n$.

5.3.6 A subset $B$ of the set of integers from 1 to 100, inclusive, has the property that no two elements of $B$ sum to 125. What is the maximum possible number of elements in $B$? (Source: AMC) Hints: 115, 274

## 5.4 More Advanced Pigeonhole Problems

### Problems

**Problem 5.6:** Suppose that I place 25 balls into 6 boxes. Prove that one of the boxes must contain at least 5 balls.

**Problem 5.7:** Suppose that I place $n$ items into $k$ boxes. What is the largest number $m$ such that I can be guaranteed that one of the boxes contains at least $m$ items?

**Problem 5.8:** There are 20 children in a small mountain town. Any two of them have a common grandfather, and each child has two distinct grandfathers.
(a) How many grandfathers can there be in the town?
(b) Prove that there are 14 children who have a common grandfather.
(Source: ToT)

**Problem 5.9:** Given any set of ten distinct 2-digit numbers, prove that there exist two disjoint subsets (of the 10 numbers) with the same sum. (Source: IMO)

**Problem 5.10:** Aimee plays at least one game of chess a day for eight weeks, but she plays no more than 11 games in any 7-day period. Show that there is some period of consecutive days in which she plays exactly 23 games.

As we've seen, the Pigeonhole Principle can be used to show that more than 1 item share some quality. But what if we want to show that more than $k$ items share some quality, where $k>1$ is a positive integer? Fortunately, given the right conditions, we can do that too.

Here's a basic example:

**Problem 5.6:** Suppose that I place 25 balls into 6 boxes. Prove that one of the boxes must contain at least 5 balls.

*Solution for Problem 5.6:* As with the basic Pigeonhole Principle, we can think about this just using common sense. If we place 4 balls into each of the 6 boxes, that accounts for 24 balls; any other distribution of the first 24 balls will result in 5 balls in at least one box. But we still have one ball left over, so whichever box we place it in will have 5 balls.

Although this is good common-sense reasoning, it is not a formal proof, so let's formally prove the statement. Suppose that the boxes are numbered from 1 to 6, and that there are $a_{1}, a_{2}, \ldots, a_{6}$ balls in the respective boxes. Since there are 25 total balls, we must have
$$a_{1}+a_{2}+\cdots+a_{6}=25 .$$

If every box contains at most 4 balls, then $a_{1} \leq 4, a_{2} \leq 4, \ldots, a_{6} \leq 4$. Therefore
$$25=a_{1}+a_{2}+a_{3}+a_{4}+a_{5}+a_{6} \leq 4+4+4+4+4+4=24$$
giving $25 \leq 24$, a contradiction. So some box must contain at least 5 balls.

This is an example of a more general version of the Pigeonhole Principle. It basically says that some box is guaranteed to have at least a certain number of balls. Exactly how many balls are guaranteed in general? We'll work that out in the next problem.

**Problem 5.7:** Suppose that I place $n$ items into $k$ boxes. What is the largest number $m$ such that I can be guaranteed that one of the boxes contains at least $m$ items?

*Solution for Problem 5.7:* We want to take our reasoning from Problem 5.6 and apply it to the general case. So what's wrong with the following argument?

> **Bogus Solution:** We can put $\frac{n-1}{k}$ balls into each of the $k$ boxes. This accounts for $k\left(\frac{n-1}{k}\right)=n-1$ of the balls. There is 1 ball left over, which must go in some box, and thus some box must contain at least $\frac{n-1}{k}+1$ balls.

Seems reasonable, and it works with $n=25$ and $k=6$ as in Problem 5.6. So why is this not quite correct?

The problem is that $\frac{n-1}{k}$ might not be an integer. The best we can do in our initial step is to put $\left\lfloor\frac{n-1}{k}\right\rfloor$ balls in each box, where $\lfloor x\rfloor$ is the "floor" function, meaning the greatest integer less than or equal to $x$. Then our leftover ball(s) ensure that at least one box will have $\left\lfloor\frac{n-1}{k}\right\rfloor+1$ balls.

This is the best that we can do, as follows: Suppose that $n \geq k$, and write $n-1=q k+r$, where $q$ is a positive integer and $0 \leq r<k$ is the remainder of $(n-1) / k$. Then we can place $\left\lfloor\frac{n-1}{k}\right\rfloor+1$ balls in the first $r+1$ boxes and $\left\lfloor\frac{n-1}{k}\right\rfloor$ balls in the remaining $k-(r+1)$ boxes. Noting that $\left\lfloor\frac{n-1}{k}\right\rfloor=q$, we see that this account for all $n$ balls:
$$\begin{aligned}
(r+1)(q+1)+(k-(r+1)) q & =(r+1+k-(r+1)) q+(r+1) \\
& =k q+r+1 \\
& =(n-1)+1=n .
\end{aligned}$$

Finally, if $n<k$, then there's nothing to prove: we can only guarantee at least 1 box in some box.

> **Important:** The generalized Pigeonhole Principle: If we place $n$ balls into $k$ boxes, then at least one box must contain at least $\left\lfloor\frac{n-1}{k}\right\rfloor+1$ balls.

> **Concept:** Don't memorize this formula! It's better to use your common sense when applying the Pigeonhole Principle than to memorize a somewhat obscure formula.

**Problem 5.8:** There are 20 children in a small mountain town. Any two of them have a common grandfather, and each child has two distinct grandfathers. Prove that there are 14 children who have a common grandfather. (Source: ToT)

*Solution for Problem 5.8:* Since we're trying to prove that a group of things all share some property in common-specifically, that 14 children have a common grandfather-this problem is a good candidate for the Pigeonhole Principle. But how can we use it? It seems clear that the children are our "balls" and the grandfathers are our "boxes," but we only have 20 children. How are we going to be able to get 14 of them in the same "box"?

The first thing to observe is that we actually have 40 "balls," since each child has two distinct grandfathers. In other words, each child is going to be placed into two boxes, one per grandfather. So we need to be able to use Pigeonhole in a way such that placing 40 balls into the boxes will result in at least 14 balls in one box.

Now we look at the numbers. We might notice that if we only had 39 balls, we could get exactly 13 balls in each of 3 boxes. We could also look at our formula from above: placing 40 balls into $k$ boxes guarantee that at least one box contains
$$\left\lfloor\frac{39}{k}\right\rfloor+1$$
balls; if we want this to equal 14, we need $\left\lfloor\frac{39}{k}\right\rfloor=13$, which suggests $k=3$. So if there were only 3 grandfathers in the entire town, then there'd be 3 "boxes" (grandfathers) for 40 "balls" (grandchildren), and hence one of the boxes would have 14 balls, and we'd be done.

So we're left to try to prove the (perhaps surprising) claim that there are only 3 (or fewer) grandfathers. Let's see how we might do this. Suppose the $1^{\text {st }}$ kid has grandfathers $A$ and $B$. The $2^{\text {nd }}$ kid has to have a grandfather in common with the $1^{\text {st }}$ kid, so suppose it's $A$ that they have in common (it doesn't matter; the argument works the same if we supposed it was $B$). So the $2^{\text {nd }}$ kid has grandfathers $A$ and C. Now there are two possibilities.

One possibility is that every kid might have grandfather $A$. If this is the case, then there might be more than 3 grandfathers in the town (every kid might have a unique $2^{\text {nd }}$ grandfather), but that's no arorry, because in this case, the problem becomes trivial: not only are there 14 kids with a common grandfather, but in fact all 20 kids have a common grandfather!

The other possibility is that there's some kid who doesn't have $A$ as a grandfather. But since this kid must have a grandfather in common with each of the first two kids, we know that this new kid must have $B$ and $C$ as her grandfathers. At this point, we have kids with the following sets of grandfathers:
$$(A \text { and } B) \quad(A \text { and } C) \quad(B \text { and } C)$$

Since every other kid must have a grandfather in common with all 3 of these children, we see that $\{A, B, C\}$ are the only possible grandfathers. If there were a $4^{\text {th }}$ grandfather called $D$, and some child had grandfather $D$, then that child's other grandfather would have to be in common with all 3 of the kids listed above, but those 3 kids don't have a grandfather in common. Therefore, there are only 3 grandfathers, and we can use the Pigeonhole Principle as described earlier to complete the proof.

Here's a summary of our solution:
One possibility is that all the children have a grandfather in common, in which case the problem becomes trivial. If they don't all have a grandfather in common, then we showed that there are only 3 grandfathers in the entire town. But this means that we have 40 children "balls" to place into 3 grandfather "boxes," since each child has 2 grandfathers, and hence, by the Pigeonhole Principle, one of the grandfathers must have at least 14 grandchildren.

We'll finish this section with a couple of harder applications of the Pigeonhole Principle.

**Problem 5.9:** Given any set of ten distinct 2-digit numbers, prove that there exist two disjoint subsets (of the 10 numbers) with the same sum. (Source: IMO)

*Solution for Problem 5.9:* The fact that we're trying to prove the existence of two of something with the same property (in this case, two subsets with the same sum) is our tipoff that we may want to consider using the Pigeonhole Principle. So subsets are going to be our "balls" and sums are going to be our "boxes". In order to apply the Pigeonhole Principle, we need to count how many of each of these there are.

A set with 10 elements has $2^{10}=1024$ subsets, since each of the 10 elements can either be in or not in any particular subset. However, we can exclude the empty set (since it has sum 0) and the subset consisting of the entire set (since there cannot be another subset disjoint to this). Therefore we reall have only $1024-2=1022$ subsets to consider.

Now we count the number of possible sums. The smallest possible sum is 10, coming from the subset $\{10\}$, and the largest possible sum is
$$91+92+\cdots+99=9(95)=855$$
coming from the subset $\{91,92, \ldots, 99\}$. Therefore, there are $855-10+1=846$ possible sums of subsets consisting of between 1 and 9 elements of the set.

Since $1022>846$, we are guaranteed (by the Pigeonhole Principle) that at least 2 different subsets have the same sum. But how do we know that these subsets are disjoint?

We don't know that they're disjoint, but it's not a problem! Simply remove any elements that the two subsets have in common. Since we're removing the same elements, and the subsets originally had the same sum, they will still have the same sum after we remove the (same) elements from each.

Note that 10 elements is the minimum value for which this argument works. If we had started with only 9 elements, then we would have $2^{9}-2=510$ subsets, but the sums could range from 10 to $92+\cdots+99=8(95.5)=764$, so there would be $764-10+1=755$ possible sums. Hence, since $510<755$, we couldn't apply the Pigeonhole Principle. (This doesn't mean that the result is not true for 9 elements, it just means that our proof wouldn't work.)

**Problem 5.10:** Aimee plays at least one game of chess a day for eight weeks, but she plays no more than 11 games in any 7-day period. Show that there is some period of consecutive days in which she plays exactly 23 games.

*Solution for Problem 5.10:* It's not immediately clear how to apply the Pigeonhole Principle to this problem. For one thing, we want to show that there's a period in which Aimee plays exactly 23 games, but the Pigeonhole Principle, as we typically use it, only guarantees at least some amount of something. Is there another way that we can think about this problem so that it is equivalent to showing that there are at least 2 of something?

Suppose that we keep a running total of the number of games that Aimee plays through the first $i$ days, where $0 \leq i \leq 56$. Specifically, let $g_{i}$ be the total number of games that she plays starting at Day 1 and going through Day $i$; note that $g_{0}=0$ since she plays 0 games in the first 0 days. The statement that we want to prove-that Aimee played exactly 23 games during some period-is equivalent to showing that there must exist integers $0 \leq i<j \leq 56$ such that $g_{j}-g_{i}=23$. This should remind you a bit of Problem 5.3, so we'll try to use a similar approach.

Consider the remainders when each $g_{i}$ is divided by 23. The possible values of these remainders are the first 23 nonnegative integers: $\{0,1, \ldots, 22\}$. Eight weeks is 56 days, thus by the Pigeonhole Principle, there must be some remainder $r$ which occurs on three different days. Again by the Pigeonhole Principle, two of these days must be at most 4 weeks apart: if there were more than 4 weeks between the first and second days and the second and third days, then there would be more than 8 weeks between the first and third, which is too long. So we know that there exist integers $0 \leq i \leq j \leq 56$, with $j-i \leq 28$, such that $g_{j}-g_{i}$ is a multiple of 23. But we need to show that it is exactly 23.

There's still information in the problem statement that we haven't used!

> **Concept:** When you seem to be stuck on a problem, think if there is any information in the problem statement that you haven't yet used.

We also have the information that Aimee plays at most 11 games in any 7-day period. This means that in 4 weeks she will have played at most 44 games. Thus $0<g_{j}-g_{i} \leq 44$. But $g_{j}-g_{i}$ is also a multiple of 23. The only multiple of 23 greater than 0 and less than or equal to 44 is 23. Thus $g_{j}-g_{i}=23$, and we conclude that starting with Day $i+1$ and ending with Day $j$, Aimee played exactly 23 games.

### Exercises

5.4.1 Show that, in a 13-card bridge hand, there must be at least 4 cards of the same suit.

5.4.2 Prove that, for any set of 17 positive integers, there is some subset of 5 of them whose sum is a multiple of 5. Hints: 106

5.4.3 Every triangle with vertices among 11 given points (no 3 of which are collinear) is assigned one of four colors: amber, burgundy, chartreuse, or dark green. What is the largest number $N$ for which we can be sure that at least $N$ of the triangles are assigned the same color? (Source: Mandelbrot)

5.4.4 A pen-pal club has 12 members. In August, each member of the club sends a letter to 6 of the other members, chosen at random.
(a) Prove that some pair of members of the club will send each other letters. Hints: 226
(b) In September, each member of the club sends a letter to only 5 of the other members. Does the conclusion from part (a) still hold? Why or why not? Hints: 17

5.4.5★ Somewhere in the universe, $n$ students are taking a 10-question math competition. Their collective performance is called laughable if, for some pair of questions, there exist 57 students such that either all of them answered both questions correctly or none of them answered both questions correctly. Compute the smallest $n$ such that the performance must be laughable, no matter how the students performed on the competition. (Source: HMMT) Hints: 137, 53, 126

## 5.5 Summary

> Formally, the Pigeonhole Principle states that if we place $n$ balls into $k$ boxes, where $n>k$, then at least one box must contain more than 1 ball.

> Informally, the Pigeonhole Principle is just common sense. If you have more items than boxes to place them in, then at least one of the boxes must contain more than one item.

> More generally, if we have $n$ items to be placed in $k$ boxes, then at least one box must contain at least $\left\lfloor\frac{n-1}{k}\right\rfloor+1$ balls.

Don't memorize a "formula" for the Pigeonhole Formula (like the one above). Instead, use your common sense when applying it.

- Whenever we have to show that "a pair" of objects or "at least 2" objects share some property that's our cue to think about the Pigeonhole Principle. More generally, it can often be used the show "at least $n$" objects share some property, or in problems that ask you to find the maximum number of objects satisfying some property.
- Sometimes, before applying the Pigeonhole Principle, we have to do a little work to reduce the number of boxes.
- Usually, the tricky part of applying the Pigeonhole Principle to a problem is identifying what are the "boxes" and the "balls."

## Review Problems

**Problem 5.11:** My sock drawer has lots of socks of four different colors (white, black, brown, and blue). How many socks do I have to pull out to ensure:
(a) at least one matching pair?
(b) at least two matching pairs?

**Problem 5.12:** The Aopslandia Grand Championship lacrosse tournament has 38 teams and lasts for several weeks. Each team will play each other team exactly once over the course of the tournament. Prove that, at any point in the tournament, there must be two teams who have completed the same number of games.

**Problem 5.13:** Prove that for any set of five positive integers, there are three of them whose sum is divisible by 3.

**Problem 5.14:** 10 students took a 35-question history test. The test was very hard: each question was solved by exactly 1 student. If we know that at least one student got exactly 1 question right, at least one student got exactly 2 questions right, and at least one student got exactly 3 questions right, show that there must be a student that got at least 5 questions right.

**Problem 5.15:** The farmer's market down the street from my house has 7 different kinds of apples: Golden Delicious, Fuji, Granny Smith, Gala, McIntosh, Cortland, and Braeburn. I want to bake a pie, for which I need 5 apples of the same type (because a pie with more than one type of apple, well, that would be disgusting).
(a) If I randomly select apples, how many do I need to buy to guarantee that I will be able to bake my pie?
(b) If I want to bake 3 pies, now how many randomly-selected apples do I have to buy?

**Problem 5.16:** Prove that for any set of 11 positive integers, there is some nonempty subset of them whose sum is divisible by 11.

**Problem 5.17:** A group of 15 friends has $\$ 100$ among them, and each person in the group has an integer number of dollars. Prove that two of them must have the same amount.

**Problem 5.18:** Show that if 16 people are seated in a row of 20 chairs, then some group of 4 consecutive chairs must be occupied.

**Problem 5.19:** What is the maximum number of kings that we can place on an $8 \times 8$ chessboard, such that no two kings are adjacent (including diagonally)?

## Challenge Problems

**Problem 5.20:** A certain (small!) college has 20 students and offers 6 courses. Each student can enroll in any or all of the 6 courses, or none at all (which is a real waste of tuition). Prove or disprove: there must exist 5 students and 2 courses, such that either all 5 students are in both courses, or all 5 students are in neither course. (Source: Putnam) Hints: 244

**Problem 5.21:** Sam's band has 6 members, but only 4 of them play together in a concert. Additionally, no 3 members can play together in more than one performance. How many concerts can Sam's band give, at most? (Source: Mandelbrot) Hints: 258

**Problem 5.22:** Prove that for every prime $p$ except 2 and 5, there is a power of $p$ that ends with the digits 0001. Hints: 273

**Problem 5.23:** Let $r$ by any real number, and $n \geq 1$ be a positive integer. Show that at least one of $r, 2 r, \ldots,(n-1) r$ differs from an integer by at most $\frac{1}{n}$. Hints: 278

**Problem 5.24:** Every point in the plane is colored either red, green, or blue. Prove that there exists a rectangle in the plane such that all four of its vertices are the same color. Hints: 319, 289

**Problem 5.25★:** In a $6 \times 6$ grid, what is the largest number of squares that can be colored such that no four of the colored squares form the corners of a rectangle with vertical and horizontal sides? For example, the coloring pattern shown at right is not allowed, since the four marked squares form the corners of such a rectangle. (Source: Mandelbrot)
Hints: 293, 227

**Problem 5.26★:** Let $X=\left\{x_{1}, x_{2}, \ldots, x_{m}\right\}$ be a set of $m$ positive integers, all less than or equal to $n$, and let $Y=\left\{y_{1}, y_{2}, \ldots, y_{n}\right\}$ be a set of $n$ positive integers, all less than or equal to $m$. Prove that there is a nonempty subset of $X$ and a nonempty subset of $Y$ with the same sum. (Source: Putnam) Hints: 130, 170, 175

**Problem 5.27★:** 40 teams play a tournament in which every team plays every other team exactly once. No ties occur, and each team has a $50 \%$ chance of winning any game it plays. Find the probability that no two teams win the same number of games. (Source: AIME) Hints: 260

**Problem 5.28★:** An international society has its members from six different countries. The list of members has 1578 names, numbered $1,2, \ldots, 1978$. Prove that there is at least one member whose number is the sum of the numbers of two (not necessarily distinct) members from his own country. (Source: IMO) Hints: $80,162,108$
