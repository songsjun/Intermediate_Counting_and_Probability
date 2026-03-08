# Chapter 1: Review of Counting & Probability Basics

*A bad review is like baking a cake with all the best ingredients and having someone sit on it. - Danielle Steele*

## 1.1 Introduction

Before beginning with new material, we'll spend this chapter making sure that you have a good grasp of the basics of counting and probability. This chapter is basically a one-chapter review of the contents of Introduction to Counting \& Probability. If a lot of the material in this chapter is unfamiliar to you, then you should probably start with the Introduction book, before tackling this book.

The chapter will consist of some problems selected from Introduction to Counting \& Probability together with their solutions.

> **Important:** You should feel confident that you are able to solve most or all of the problems in this chapter before continuing on to the rest of the book.

It is important that basic counting and probability computations of the type that we do in this chapter are as natural and familiar to you as arithmetic and basic algebra are. As a child, you wouldn't try to learn how to multiply three-digit numbers together without having absolutely mastered multiplication of 1-digit numbers. In the same way, you shouldn't plunge into the more advanced counting techniques in this book without having the basics mastered.

Also, there is one brief section at the end of this chapter (namely, Section 1.6) that includes new material that is not in the Introduction book. This section discusses summation notation, an example of which is the left side of the equation below:
$$\sum_{i=1}^{n} i=\frac{n(n+1)}{2} .$$

If you are not familiar with this notation, please make sure that you read this section before continuing on with the book.

## 1.2 Basic Counting Techniques

### Problems

**Problem 1.1:** My city is running a lottery. In the lottery, 25 balls numbered 1 through 25 are placed in a bin. Four balls are drawn one at a time and their numbers are recorded. The winning combination consists of the four selected numbers in the order they are selected. How many winning combinations are there, if:
(a) each ball is discarded after it is removed?
(b) each ball is replaced in the bin after it is removed and before the next ball is drawn?

**Problem 1.2:** On the island of Mumble, the Mumblian alphabet has only 5 letters, and every word in the Mumblian language has no more than 3 letters in it. How many words are possible? (A word can use a letter more than once, but 0 letters does not count as a word.)

**Problem 1.3:** The Smith family has 4 sons and 3 daughters. In how many ways can they be seated in a row of 7 chairs, such that at least 2 boys are next to each other?

**Problem 1.4:** How many 3-digit numbers have exactly one zero?

**Problem 1.5:** Our math club has 20 members and 3 officers: President, Vice President, and Treasurer. However, one member, Ali, hates another member, Brenda. In how many ways can we fill the offices if Ali refuses to serve as an officer if Brenda is also an officer?

**Problem 1.6:** How many possible distinct arrangements are there of the letters in the word BALL?

**Problem 1.7:** In how many different ways can 6 people be seated at a round table? Two seating arrangements are considered the same if, for each person, the person to his or her left is the same in both arrangements.

**Problem 1.8:** Consider a club that has $n$ people. What is the number of ways to form an $r$-person committee from the total of $n$ people?

**Problem 1.9:** Each block on the grid shown at right is 1 unit by 1 unit. Suppose we wish to walk from $A$ to $B$ via a 7 unit path, but we have to stay on the grid-no cutting across blocks. How many different paths can we take?

**Problem 1.10:** In how many ways can a dog breeder separate his 10 puppies into a group of 4 and a group of 6 if he has to keep Biter and Nipper, two of the puppies, in separate groups?

### Solutions

**Problem 1.1:** My city is running a lottery. In the lottery, 25 balls numbered 1 through 25 are placed in a bin. Four balls are drawn one at a time and their numbers are recorded. The winning combination consists of the four selected numbers in the order they are selected. How many winning combinations are there, if:
(a) each ball is discarded after it is removed?
(b) each ball is replaced in the bin after it is removed and before the next ball is drawn?

*Solution for Problem 1.1:* (a) We have 25 choices for the first ball. After the first ball is drawn and discarded, there are 24 balls left in the bin, so there are 24 choices for the second ball. Similarly, there are 23 choices for the third ball and 22 choices for the fourth ball. Hence the number of winning combinations is $25 \times 24 \times 23 \times 22=303,600$.
(b) We have 25 choices for each of the four balls, since when each ball is drawn, all 25 balls are in the bin. Hence there are $25 \times 25 \times 25 \times 25=25^{4}=390,625$ winning combinations.

> **Concept:** In an event with multiple stages, we multiply the number of choices at each stage to get the total number of choices.

> **Concept:** It is important to distinguish selecting without replacement from selecting with replacement. When choosing $k$ items, in order, from a group of $n$, with replacement, we have $n^{k}$ choices. When choosing $k$ items, in order, from a group of $n$, without replacement, we have
> $$n(n-1)(n-2) \cdots(n-k+1)$$
> choices. Selecting $k$ items from a group of $n$ items, without replacement, where order matters, is called a permutation. The number of permutations of $k$ items from a group of $n$ items is sometimes denoted $P(n, k)$ or ${ }_{n} P_{k}$.

**Problem 1.2:** On the island of Mumble, the Mumblian alphabet has only 5 letters, and every word in the Mumblian language has no more than 3 letters in it. How many words are possible? (A word can use a letter more than once, but 0 letters does not count as a word.)

*Solution for Problem 1.2:* For this problem, it makes sense to divide the words into cases, based on the number of letters in each word.

Case 1: 1-letter words
There are 5 1-letter words (each of the 5 letters is itself a 1-letter word).

Case 2: 2-letter words
To form a 2-letter word, we have 5 choices for our first letter, and 5 choices for our second letter. Thus there are $5 \times 5=25$ 2-letter words possible.

Case 3: 3-letter words
To form a 3-letter word, we have 5 choices for our first letter, 5 choices for our second letter, and 5 choices for our third letter. Thus there are $5 \times 5 \times 5=125$ 3-letter words possible.

To get the total number of words in the language, we add the number of words from each of our cases. (We need to make sure that the cases are exclusive, meaning they don't overlap. But that's clear in this solution, since, for example, a word can't be both a 2-letter word and a 3-letter word at the same time.)

Therefore, there are $5+25+125=155$ words possible on Mumble.

> **Concept:** Casework is the general technique of breaking up the possibilities into two or more categories. We can then add the possibilities of the various cases to get the total number of possibilities.

> **Concept:** When using casework, it is important that the cases be exclusive, meaning that they don't overlap. Otherwise, you'll end up counting some outcomes multiple times. (Although, later in this book, we'll see some techniques for dealing with overlapping cases.)

**Problem 1.3:** The Smith family has 4 sons and 3 daughters. In how many ways can they be seated in a row of 7 chairs, such that at least 2 boys are next to each other?

*Solution for Problem 1.3:* It will be fairly difficult to try to count this directly with casework, since there are lots of possible cases (for example, two possibilities are BBBBGGG and BGGBBGB, where B is a boy and $G$ is a girl). But there is only one way to assign genders to the seating so that no two boys are next to each other, and that is BGBGBGB. So we use complementary counting: we count the items that we don't want.

If we seat the children as BGBGBGB, then there are 4 ! orderings for the 4 boys, and 3 ! orderings for the 3 girls, giving a total of $4!\times 3!=144$ seatings for the 7 children.

These are the seatings that we don't want, so to count the seatings that we do want, we need to subtract these seatings from the total number of seatings without any restrictions. Since there are 7 kids, there are 7 ! ways to seat them.

Therefore, the answer is $7!-(4!\times 3!)=5040-144=4896$.

Often, complicated casework means that you should think about trying complementary counting: that is, counting what we don't want and subtracting this count from the number of possibilities (without restriction). If it's hard to count all the cases that we want, then it may be relatively easy to count what we don't want.

> **Concept:** When a problem asks "How many are not?", we might think instead to count "How many are?" When a problem asks "How many have at least one?", we might think instead to count "How many have none?"

**Problem 1.4:** How many 3-digit numbers have exactly one zero?

*Solution for Problem 1.4:* We could do this by casework.

Case 1: 3-digit numbers with 0 as the middle digit
There are 9 choices for the first digit and 9 choices for the last digit, for a total of $9 \times 9=81$ numbers in this case.

Case 2: 3-digit numbers with 0 as the final digit
There are 9 choices for the first digit and 9 choices for the middle digit, for a total of $9 \times 9=81$ numbers in this case.

Therefore, there are $81+81=162$ such numbers.

On the other hand, we can also solve the problem directly, by thinking about the steps necessary to construct such a 3-digit number, and counting the number of choices that we have at each step.

When doing such a construction, we usually want to start by dealing with the most severe restriction in the construction. In this problem, the restriction is that the number must have exactly one zero.

So when attempting to construct such a 3-digit number, our first choice should be: where do we put the 0 ? We have 2 choices-the zero can go in the middle (tens) digit or in the rightmost (units) digit. Note that a number cannot begin with a 0 , so we can't put the zero in the leftmost (hundreds) digit.

Now that we've placed the zero, we need to choose the other two digits. Each of the other two digits can be any digit from 1 through 9 (but cannot be 0 ). So we have 9 choices for each of the other two digits.

Therefore, there are $2 \times 9 \times 9=162$ such 3-digit numbers.

> **Concept:** This general idea-thinking about how to construct the items that we wish to count, and then keeping track of the choices that we have to make during the construction-is known as constructive counting.

> **Concept:** Deal with the restriction first. Considering the restriction first usually helps when solving constructive counting problems.

**Problem 1.5:** Our math club has 20 members and 3 officers: President, Vice President, and Treasurer. However, one member, Ali, hates another member, Brenda. In how many ways can we fill the offices if Ali refuses to serve as an officer if Brenda is also an officer?

*Solution for Problem 1.5:* The best way to approach this problem is to use complementary counting.
We know that there are $20 \times 19 \times 18$ ways to choose the 3 officers if we ignore the restriction about Ali and Brenda. So now we want to count the number of outcomes that we don't want: both Ali and Brenda serving as officers.

To count the outcomes we don't want, we will use constructive counting. We need to pick an office for Ali, then pick an office for Brenda, then put someone in the last office.

We have 3 choices for an office for Ali, either President, VP, or Treasurer.
Once we pick an office for Ali , we have 2 offices left from which to choose an office for Brenda.
Once we have both Ali and Brenda installed in offices, we have 18 members left in the club to pick from for the remaining vacant office.

So there are $3 \times 2 \times 18$ ways to pick officers such that Ali and Brenda are both in an office. Remember that these are the cases that we want to exclude, so to finish the problem we subtract these cases from the total number of cases. Hence the answer is:
$$(20 \times 19 \times 18)-(3 \times 2 \times 18)=((20 \times 19)-6) \times 18=374 \times 18=6732 .$$

> **Concept:** Many problems will require you to use more than one counting method. In the previous problem, we used both complementary counting and constructive counting.

**Problem 1.6:** How many possible distinct arrangements are there of the letters in the word BALL?

*Solution for Problem 1.6:* First, note that the answer is not simply 4!:

> **Bogus Solution:** We have 4 ways to pick the first letter, 3 ways to pick the second, and so on, for a total of 4 ! possibilities.

This method overcounts. The reason for this is that two of our letters are the same.
Let's pretend that the two L's are different, and call them $\mathrm{L}_{1}$ and $\mathrm{L}_{2}$. So our word BALL is now really $\mathrm{BAL}_{1} \mathrm{~L}_{2}$. In making the expected 4 ! arrangements, we make both $\mathrm{BAL}_{1} \mathrm{~L}_{2}$ and $\mathrm{BAL}_{2} \mathrm{~L}_{1}$. But when we remove the numbers, we have BALL and BALL, which are the same.

With 4 !, we've overcounted, and we need to correct for this.
Every possible arrangement of BALL is counted twice among our arrangements of $B A L_{1} L_{2}$. For example, $L L A B$ is counted as both $L_{1} L_{2} A B$ and $L_{2} L_{1} A B$, $L A B L$ is counted as both $L_{1} A B L_{2}$ and $L_{2} A B L_{1}$, and so on for every possible arrangement of BALL. We can see this in Figure 1.1:

\begin{table}
\begin{tabular}{ll}
$\mathrm{BAL}_{1} \mathrm{~L}_{2}, \mathrm{BAL}_{2} \mathrm{~L}_{1} \Rightarrow$ BALL & $\mathrm{BL}_{2} \mathrm{AL}_{1}, \mathrm{BL}_{1} \mathrm{AL}_{2} \Rightarrow$ BLAL \\
$\mathrm{BL}_{1} \mathrm{~L}_{2} \mathrm{~A}, \mathrm{BL}_{2} \mathrm{~L}_{1} \mathrm{~A} \Rightarrow$ BLLA & $\mathrm{ABL}_{1} \mathrm{~L}_{2}, \mathrm{ABL}_{2} \mathrm{~L}_{1} \Rightarrow$ ABLL \\
$\mathrm{L}_{1} \mathrm{BAL}_{2}, \mathrm{~L}_{2} \mathrm{BAL}_{1} \Rightarrow$ LBAL & $\mathrm{L}_{1} \mathrm{BL}_{2} \mathrm{~A}, \mathrm{~L}_{2} \mathrm{BL}_{1} \mathrm{~A} \Rightarrow$ LBLA \\
$\mathrm{AL}_{1} \mathrm{BL}_{2}, \mathrm{AL}_{2} \mathrm{BL}_{1} \Rightarrow$ ALBL & $\mathrm{L}_{1} \mathrm{ABL}_{2}, \mathrm{~L}_{2} \mathrm{ABL}_{1} \Rightarrow$ LABL \\
$\mathrm{L}_{1} \mathrm{~L}_{2} \mathrm{BA}, \mathrm{L}_{2} \mathrm{~L}_{1} \mathrm{BA} \Rightarrow$ LLBA & $\mathrm{AL}_{1} \mathrm{~L}_{2} \mathrm{~B}, \mathrm{AL}_{2} \mathrm{~L}_{1} \mathrm{~B} \Rightarrow$ ALLB \\
$\mathrm{L}_{1} \mathrm{AL}_{2} \mathrm{~B}, \mathrm{~L}_{2} \mathrm{AL}_{1} \mathrm{~B} \Rightarrow$ LALB & $\mathrm{L}_{1} \mathrm{~L}_{2} \mathrm{AB}, \mathrm{L}_{2} \mathrm{~L}_{1} \mathrm{AB}$ \\
\hline LLAB
\end{tabular}
\captionsetup{labelformat=empty}
\caption{Figure 1.1: BALL's with different L's}
\end{table}

Thus, the number of arrangements of $B A L_{1} L_{2}$ is exactly twice the number of arrangements of BALL. So to get the number of arrangements of BALL, we have to divide the number of arrangements of $\mathrm{BAL}_{1} \mathrm{~L}_{2}$ by 2 .

Therefore, the number of arrangements of BALL is $4!/ 2=12$.

> **Concept:** Often we can count outcomes by strategically overcounting the number of outcomes, and then correcting for the overcounting. One common use of this is in counting permutations with repeated items.

**Problem 1.7:** In how many different ways can 6 people be seated at a round table? Two seating arrangements are considered the same if, for each person, the person to his or her left is the same in both arrangements.

*Solution for Problem 1.7:* If the 6 people were sitting in a row, rather than around a table, there would be 6 ! arrangements. But this is clearly an overcounting, since several different row arrangements correspond to the same round table arrangement. For example, suppose we take a row of 6 people and sit them at the round table by putting the first person in the "top" seat and proceeding counterclockwise. Six row arrangements and their corresponding circular arrangements are shown in Figure 1.2 below.

Figure 1.2: Row and Circular Seatings

All six arrangements of the people $A$ through $F$ shown in the diagram correspond to the same arrangement of the people seated around a round table.

The reason for this is that our problem has symmetry: each arrangement can be rotated 6 ways (one of them being no rotation) to make other arrangements. Hence, when we put our 6 ! arrangements of ABCDEF in a circle, we count each circular arrangement 6 times, once for each rotation.

Therefore, we must divide our initial overcount of $6!$ by 6 , to account for the fact that there are 6 row arrangements corresponding to each circular arrangement. So our answer is that there are $6!/ 6=5!=120$ ways to arrange the 6 people around the table.

> **Concept:** Counting outcomes with symmetry usually means some sort of strategic overcounting.

**Problem 1.8:** Consider a club that has $n$ people. What is the number of ways to form an $r$-person committee from the total of $n$ people?

*Solution for Problem 1.8:* We start by counting the number of ways to choose $r$ people if order matters. There are $n$ choices for the first person, $n-1$ choices for the second person, $n-2$ choices for the third person, and so on, up to $n-r+1$ choices for the $r^{\text {th }}$ person.

So there are
$$n \times(n-1) \times(n-2) \times \cdots \times(n-r+1)$$
ways to choose $r$ people from a total of $n$ people if order matters. (Recall that this is the quantity that is often denoted by $P(n, r)$.)

But we know that there are $r$ ! ways to order $r$ people. Therefore, each unordered committee of $r$ people will correspond to $r$ ! ordered choices of $r$ people. So we need to divide our count in equation (1.1) by $r$ ! to correct for the overcounting.

Therefore our answer is
$$\binom{n}{r}=\frac{n \times(n-1) \times(n-2) \times \cdots \times(n-r+1)}{r!}=\frac{n!}{r!(n-r)!} .$$

> **Concept:** If we don't care about the order when choosing $r$ items from a set of $n$ items-for example, when choosing a committee-we have a combination. The number of ways to choose $r$ items from a set of $n$ items, without regard to order, is $\binom{n}{r}$, pronounced " $n$ choose $r$." (Note: some sources denote this as $C(n, r)$ or as ${ }_{n} C_{r}$.)

> **Important:** The formula for combinations is:
> $$\binom{n}{r}=\frac{n!}{r!(n-r)!}=\frac{n(n-1)(n-2) \cdots(n-r+1)}{r!} .$$
>
> The first formula is more typically used in algebraic proofs involving combinations, whereas the latter formula is the one that we most often use to actually compute combinations. For example:
> $$\binom{11}{3}=\frac{11 \times 10 \times 9}{3 \times 2 \times 1}=165$$

**Problem 1.9:** Each block on the grid shown below is 1 unit by 1 unit. Suppose we wish to walk from $A$ to $B$ via a 7 unit path, but we have to stay on the grid-no cutting across blocks. How many different paths can we take?

*Solution for Problem 1.9:* We know that we must take a 7 unit path. If we look at the grid a little more carefully, we can see that our path must consist 4 steps to the right and 3 steps up, and we can take those steps in any order. So in order to specify a path, we must choose 3 of our 7 steps to be "up" (and the other 4 steps will thus be "right"). Hence the number of paths is
$$\binom{7}{3}=\frac{7 \times 6 \times 5}{3 \times 2 \times 1}=35 .$$

If you are not convinced, we can describe a path by writing " r " for a right step and " u " for an up step. For every arrangement of $4 \mathrm{r}^{\prime}$ s and 3 u's, we get a path from $A$ to $B$, as shown in Figure 1.3.

Figure 1.3: Example path from $A$ to $B$

Therefore, to count the number of paths from $A$ to $B$, we need only to count the number of arrangements of "rrrruuu." The number of arrangements is
$$\frac{7!}{4!3!}=\binom{7}{3}=35 .$$

Remember how we get the above expression: there are 7 ! arrangements of " $r_{1} r_{2} r_{3} r_{4} u_{1} u_{2} u_{3}$," where we think of each $r$ and each $u$ as different. However, we want to count the number of arrangements of "rrrruuu," where the r's and u's are all the same, so we must divide by the 4 ! possible arrangements of the $r$ 's and the 3 ! possible arrangements of the $u$ 's.

> **Concept:** Counting paths on a grid is one application of combinations.

**Problem 1.10:** In how many ways can a dog breeder separate his 10 puppies into a group of 4 and a group of 6 if he has to keep Biter and Nipper, two of the puppies, in separate groups?

*Solution for Problem 1.10:* Let's first do the problem by complementary counting.
If we have no restrictions on the groups, then we simply need to choose 4 of the 10 dogs to be in the smaller group, and the rest of the dogs will make up the larger group. There are $\binom{10}{4}$ ways to do this.

But we can't have Biter and Nipper in the same group. So we have to subtract the number of ways that we can form the two groups with Biter and Nipper in the same group. This calls for a little bit of casework.

Case 1: Biter and Nipper are both in the smaller group.
If they are both in the smaller group, then we have to choose 2 more dogs from the 8 remaining to complete the smaller group, and we can do this in $\binom{8}{2}$ ways.

Don't mistakenly count the possibilities in Case 1 as $\binom{8}{2}\binom{8}{6}$, by reasoning that we must choose 2 out of 8 dogs for the smaller group, and 6 out of 8 dogs for the larger group. These choices are not independent! Once we pick the 2 dogs for the smaller group, then we have no choice but to put the remaining 6 dogs into the larger group.

Case 2: Biter and Nipper are both in the larger group.
If they are both in the larger group, then we have to choose 4 dogs from the 8 remaining to compose the smaller group, and we can do this in $\binom{8}{4}$ ways.

So to get the number of ways to form groups such that Biter and Nipper are both in the same group, we add the counts from our two cases, to get $\binom{8}{2}+\binom{8}{4}$.

But remember that these are the cases that we don't want, so to solve the problem, we subtract this count from the number of ways to form the two groups without restrictions. Thus, our answer is
$$\binom{10}{4}-\left(\binom{8}{2}+\binom{8}{4}\right)=210-(28+70)=112 .$$

The other way that we could solve this problem is by direct casework. There are two cases of possible groupings.

Case 1: Biter is in the smaller group, Nipper is in the larger group.
To complete the smaller group, we need to choose 3 more dogs from the 8 remaining dogs. We can do this in $\binom{8}{3}$ ways.

Case 2: Nipper is in the smaller group, Biter is in the larger group. Again, to complete the smaller group, we need to choose 3 more dogs from the 8 remaining. We can do this in $\binom{8}{3}$ ways.

To count the total number of groupings, we add the counts from our two cases, to get $\binom{8}{3}+\binom{8}{3}= 56+56=112$ as our final answer.

> **Concept:** Many counting problems can be solved in more than one way. If it's easy to do, solving problems in more than one way is both good practice and a good way to check your answer.

## 1.3 Basic Probability Techniques

### Problems

**Problem 1.11:** What is the probability that when a fair 6-sided die is rolled, a prime number faces up?

**Problem 1.12:** A standard deck of cards has 52 cards divided into 4 suits, each of which has 13 cards. Two of the suits ( $\diamond$ and $\diamond$, called "hearts" and "diamonds") are red, the other two ( $\star$ and $\star$, called "spades" and "clubs") are black. The cards in the deck are placed in random order (usually by a process called "shuffling"). What is the probability that the first two cards are both red?

**Problem 1.13:** We have a standard deck of 52 cards, with 4 cards in each of 13 ranks. We call a 5-card poker hand a full house if the hand has 3 cards of one rank and 2 cards of another rank (such as 33355 or AAAKK). What is the probability that five cards chosen at random form a full house?

**Problem 1.14:** $A$ bag has 3 red and $k$ white marbles, where $k$ is an (unknown) positive integer. Two of the marbles are chosen at random from the bag. Given that the probability that the two marbles are the same color is $\frac{1}{2}$, find $k$.

**Problem 1.15:** Mary and James each sit in a row of 7 chairs. They choose their seats at random. What is the probability that they don't sit next to each other?

**Problem 1.16:** The Grunters play the Screamers 4 times. The Grunters are the much better team, and are $75 \%$ likely to win any given game. What is the probability that the Grunters will win all 4 games?

**Problem 1.17:** A bag has 4 red and 6 blue marbles. A marble is selected and not replaced, then a second is selected. What is the probability that both are the same color?

**Problem 1.18:** Point $C$ is chosen at random atop a 5 foot by 5 foot square table. A circular disk with a radius of 1 foot is placed on the table with its center directly on point $C$. What is the probability that the entire disk is on top of the table (in other words, none of the disk hangs over an edge of the table)?

### Solutions

**Problem 1.11:** What is the probability that when a fair 6 -sided die is rolled, a prime number faces up?

*Solution for Problem 1.11:* There are 6 equally likely outcomes. Three of those outcomes are successful: Therefore, the probability is $\frac{3}{6}=\frac{1}{2}$.

> **Concept:** If all outcomes are equally likely, then the probability of success is
> $$P(\text { success })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }} .$$

**Problem 1.12:** A standard deck of cards has 52 cards divided into 4 suits, each of which has 13 cards. Two of the suits ( ▷ and ◇, called "hearts" and "diamonds") are red, the other two ( * and *, called "spades" and "clubs") are black. The cards in the deck are placed in random order (usually by a process called "shuffling"). What is the probability that the first two cards are both red?

*Solution for Problem 1.12:*

Method 1: For the total number of possibilities, there are 52 ways to pick the first card, then 51 ways to pick the second card, for a total of $52 \times 51$ possibilities.

For the number of successful possibilities, there are 26 ways to pick a red card first (since there are 26 total red cards), then there are 25 ways to pick a second red card (since there are 25 red cards remaining after we've chosen the first card). Thus, there are a total of $26 \times 25$ successful possibilities.

Therefore, the probability is
$$P(\text { first two cards are red })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }}=\frac{26 \times 25}{52 \times 51}=\frac{25}{102} .$$

Method 2: For the total number of possibilities, there are $\binom{52}{2}=1326$ ways to pick two cards (without regard to order).

For the number of successful possibilities, there are $\binom{26}{2}=325$ ways to pick two red cards (without regard to order).

Therefore, the probability is
$$P(\text { first two cards are red })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }}=\frac{325}{1326}=\frac{25}{102} .$$

Method 3: The probability that the first card is red is $\frac{26}{52}=\frac{1}{2}$. If the first card is red, then the probability that the second card is red is $\frac{25}{51}$. Therefore:
$$P(\text { first two cards are red })=P(\text { first card red }) \times P(\text { second card red })=\frac{1}{2} \times \frac{25}{51}=\frac{25}{102} .$$

> **Concept:** There are often many ways to approach the counting within probability problems. However you choose to approach a problem, make sure that you are consistent! For example, if you count possible outcomes without regard to order, don't count successful outcomes with regard to order. In other words, don't compare apples and oranges!

**Problem 1.13:** We have a standard deck of 52 cards, with 4 cards in each of 13 ranks. We call a 5-card poker hand a full house if the hand has 3 cards of one rank and 2 cards of another rank (such as 33355 or AAAKK). What is the probability that five cards chosen at random form a full house?

*Solution for Problem 1.13:* The total number of outcomes is just the number of ways to choose 5 cards from a set of 52 , which is $\binom{52}{5}=2,598,960$. Notice that in this count, we don't care about the order in which the cards are chosen. (Remember-apples and oranges!)

To count the number of successful outcomes, we turn to constructive counting, thinking about how we'd construct a full house.

To form a full house, we have to choose:
(a) A rank for the 3 cards. This can be done in 13 ways.
(b) 3 of the 4 cards of that rank. This can be done in $\binom{4}{3}=4$ ways.
(c) A rank for the other 2 cards. This can be done in 12 ways (since we can't choose the rank that we chose in (a)).
(d) 2 of the 4 cards of that rank. This can be done in $\binom{4}{2}=6$ ways.

Again, note that in each of the steps in our constructive count, we don't care about the order in which the cards are chosen.

So there are $13 \times 4 \times 12 \times 6=3,744$ full houses. Thus, the probability is
$$\frac{3,744}{2,598,960}=\frac{6}{4165} .$$

> **Concept:** You will often have to use your toolbox of counting techniques (in this case, constructive counting) to solve probability problems.

**Problem 1.14:** A bag has 3 red and $k$ white marbles, where $k$ is an (unknown) positive integer. Two of the marbles are chosen at random from the bag. Given that the probability that the two marbles are the same color is $\frac{1}{2}$, find $k$.

*Solution for Problem 1.14:* Here we compute the probability in terms of $k$ that the two marbles are the same color, and then set that probability equal to $\frac{1}{2}$.

To calculate the probability, we simply use our usual method of counting both the total number of outcomes and the number of successful outcomes. There are $k+3$ total marbles in the bag, so the number of ways to choose 2 of them, without regard to order, is $\binom{k+3}{2}$.

One type of successful outcome is to choose two red marbles. This can be done in $\binom{3}{2}=3$ ways. The other successful outcome is to choose two white marbles. This can be done in $\binom{k}{2}$ ways. Since these two cases are mutually exclusive, we can add our counts. So
$$P(\text { both marbles are the same color })=\frac{3+\binom{k}{2}}{\binom{k+3}{2}} .$$

We set this equal to the given probability of $\frac{1}{2}$, and then solve for $k$. Our equation is
$$\frac{3+\binom{k}{2}}{\binom{k+3}{2}}=\frac{1}{2} .$$

In order to solve this, we'll need to first write out the combinations:
$$\frac{3+\frac{k(k-1)}{2}}{\frac{(k+3)(k+2)}{2}}=\frac{1}{2} \text {. }$$

We can get rid of the 2's in the denominators by multiplying the numerator and denominator of the left side by 2 :
$$\frac{6+k(k-1)}{(k+3)(k+2)}=\frac{1}{2},$$
and then we cross-multiply to get rid of the fractions:
$$12+2 k(k-1)=(k+3)(k+2) .$$

Multiplying out, we get
$$2 k^{2}-2 k+12=k^{2}+5 k+6,$$
so $k^{2}-7 k+6=0$. This factors as $(k-6)(k-1)=0$, so either $k=6$ or $k=1$. Both solutions work.

> **Concept:** Many probability problems will require some algebraic manipulation in order to solve them. Don't be afraid to use algebra (in particular, to use variables) if you need to!

**Problem 1.15:** Mary and James each sit in a row of 7 chairs. They choose their seats at random. What is the probability that they don't sit next to each other?

*Solution for Problem 1.15:* There are $\binom{7}{2}=21$ ways in which Mary and James can choose 2 chairs, if we don't worry about the order in which they sit.

Although we can use casework to count the number of ways they can choose chairs that are not next to each other, it is easier to use complementary counting. If we number the chairs \#1, \#2, . . , \#7 in order, then there are 6 ways Mary and James can choose chairs next to each other: they can sit in the first two chairs, or chairs \#2 and \#3, or chairs \#3 and \#4, etc., up to chairs \#6 and \#7. Therefore
$$P(\text { they sit next to each other })=\frac{6}{21}=\frac{2}{7^{\prime}}$$
and therefore
$$P(\text { they don't sit next to each other })=1-\frac{2}{7}=\frac{5}{7} .$$

> **Concept:** Just as with counting, sometimes it's easier to calculate the probability of an event not occurring than it is to calculate the probability of the event occurring.

**Problem 1.16:** The Grunters play the Screamers 4 times. The Grunters are the much better team, and are $75 \%$ likely to win any given game. What is the probability that the Grunters will win all 4 games?

*Solution for Problem 1.16:* The following solution is incorrect:

> **Bogus Solution:** Since each game has 2 possible outcomes, there are $2^{4}=16$ possible outcomes for the series. Only 1 of these outcomes is what we want, namely the Grunters winning all 4 games. Therefore the probability is $\frac{1}{16}$.

One clue that this is an incorrect solution is that we never used the " $75 \%$ " information that was presented in the problem. The reason this solution is incorrect is that the outcomes described in the bogus solution are not all equally likely! We can only use this counting approach to probability when we have equally likely outcomes.

So instead, we'll use multiplication of probabilities of independent events. (The games are independent, because the outcome of each game does not depend on what happened in the earlier games.) Each of the 4 games is independent of the others, and in each game, the Grunters have probability $\frac{3}{4}$ of winning. Therefore, to get the probability that the Grunters will win all 4 games, we multiply the probabilities that the Grunters win each individual game. This gives:
$$\begin{aligned}
P(\text { Grunters win all } 4 \text { games }) & =P(\text { Grunters win Game } 1) \times \cdots \times P(\text { Grunters win Game } 4) \\
& =\frac{3}{4} \times \frac{3}{4} \times \frac{3}{4} \times \frac{3}{4} \\
& =\left(\frac{3}{4}\right)^{4}=\frac{81}{256} .
\end{aligned}$$

Using the same logic, we can show that $P($ Screamers win all 4 games $)=\left(\frac{1}{4}\right)^{4}=\frac{1}{256}$.

> **Concept:** When computing probability by counting outcomes and using
> $$P(\text { success })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }},$$
> this approach will work only if the outcomes are equally likely.

> **Concept:** In an event that is made up of multiple, independent, sequential subevents, we multiply the probabilities of the sub-events to get the probability of the overall event.

**Problem 1.17:** A bag has 4 red and 6 blue marbles. A marble is selected and not replaced, then a second is selected. What is the probability that both are the same color?

*Solution for Problem 1.17:* We could solve this problem by counting the outcomes, but let's instead solve it by multiplying probabilities.

The probability that both marbles are red is given by:
$$P(\text { both red })=P(\text { first red }) \times P(\text { second red after first red is drawn }) .$$

The probability that the first marble is red is $\frac{4}{10}$. After drawing a red marble, there are 3 red marbles and 9 marbles total left in the bag, so the probability that the second marble is also red is $\frac{3}{9}$. Therefore
$$P(\text { both red })=\frac{4}{10} \times \frac{3}{9}=\frac{2}{15} .$$

Similarly, the probability that both marbles are blue is given by:
$$P(\text { both blue })=P(\text { first blue }) \times P(\text { second blue after first blue is drawn }) .$$

The probability that the first marble is blue is $\frac{6}{10}$. After drawing a blue marble, there are 5 blue marbles and 9 marbles total left in the bag, so the probability that the second marble is also blue is $\frac{5}{9}$. Therefore
$$P(\text { both blue })=\frac{6}{10} \times \frac{5}{9}=\frac{1}{3} .$$

Since drawing two red marbles and drawing two blue marbles are exclusive events, we add the individual probabilities to get the probability of one or the other occurring. Therefore:
$$P(\text { both same color })=P(\text { both red })+P(\text { both blue })=\frac{2}{15}+\frac{1}{3}=\frac{7}{15} .$$

> **Concept:** When multiplying probabilities of dependent events, be sure to take the prior events into account when computing the probabilities of later events.

**Problem 1.18:** Point $C$ is chosen at random atop a 5 foot by 5 foot square table. A circular disk with a radius of 1 foot is placed on the table with its center directly on point $C$. What is the probability that the entire disk is on top of the table (in other words, none of the disk hangs over an edge of the table)?

*Solution for Problem 1.18:* The "total outcomes" region is easy: it's just the surface of the table, so it's a square region with side length 5 .

The "successful outcomes" region is trickier. We can draw a diagram as in Figure 1.4.

Figure 1.4: Table and some disks

We can see that the disk will be entirely on the table if and only if $C$ is at least 1 foot away from each edge of the table. Therefore, $C$ must be within a central square region of side length 3 , as shown in Figure 1.4.

So, now we can compute the probability:
$$P(\text { success })=\frac{P(\text { Area of successful outcomes region })}{P(\text { Area of possible outcomes region })}=\frac{3 \times 3}{5 \times 5}=\frac{9}{25} .$$

> **Concept:** In geometry problems, or in other problems in which the possible outcomes are continuous (as opposed to discrete, meaning that they can be counted), we need to use geometry to compute the probability:
> $$P(\text { success })=\frac{P(\text { Size of successful outcomes region })}{P(\text { Size of possible outcomes region })} .$$

> **Extra!** Twice and thrice over, as they say, good is it to repeat and review what is good. - Plato

## 1.4 Expected Value

### Problems

**Problem 1.19:** Suppose you have a weighted coin in which heads comes up with probability $\frac{3}{4}$ and tails with probability $\frac{1}{4}$. If you flip heads, you win $\$ 2$, but if you flip tails, you lose $\$ 1$. What is the expected value of a coin flip?

**Problem 1.20:** In an urn, I have 20 marbles: 2 red, 3 yellow, 4 blue, 5 green, and 6 black. I select one marble at random from the urn, and I win money based on the following chart:

\begin{tabular}{|r||c|c|c|c|c|}
\hline Color & Red & Yellow & Blue & Green & Black \\
\hline Amount won & $\$ 10$ & $\$ 5$ & $\$ 2$ & $\$ 1$ & $\$ 0$ \\
\hline
\end{tabular}

What is the expected value of my winnings?

**Problem 1.21:** Suppose I have a bag with 12 slips of paper in it. Some of the slips have a 2 on them, and the rest have a 7 on them. If the expected value of the number shown on a slip randomly drawn from the bag is 3.25 , then how many slips have a 2 ?

### Solutions

Recall that expected value is the notion of a "weighted average," where the possible outcomes of an event are weighted by their respective probabilities. We can state this more precisely:

> **Concept:** Suppose that we have an event with a list of possible values of the outcomes: $x_{1}, x_{2}, \ldots, x_{n}$. Value $x_{1}$ occurs with probability $p_{1}$, value $x_{2}$ occurs with probability $p_{2}$, and so on. Note that
> $$p_{1}+p_{2}+\cdots+p_{n}=1,$$
> since the probabilities must total to 1 . Then the expected value of the outcome is defined as the sum of the probabilities of the outcomes times the value of the outcomes:
> $$E=p_{1} x_{1}+p_{2} x_{2}+\cdots+p_{n} x_{n} .$$

**Problem 1.19:** Suppose you have a weighted coin in which heads comes up with probability $\frac{3}{4}$ and tails with probability $\frac{1}{4}$. If you flip heads, you win $\$ 2$, but if you flip tails, you lose $\$ 1$. What is the expected value of a coin flip?

*Solution for Problem 1.19:* We multiply the outcomes by their respective probabilities, and add them up:
$$E=\frac{3}{4}(+\$ 2)+\frac{1}{4}(-\$ 1)=\$ 1.50-\$ 0.25=\$ 1.25 .$$

> **Concept:** Another way to think of the expected value in Problem 1.19 is to imagine flipping the coin 1000 times. Based on the probabilities, we would expect to flip heads 750 times and to flip tails 250 times. We would then win $\$ 1500$ from our heads but lose $\$ 250$ from our tails, for a net profit of $\$ 1250$. Since this occurs over the course of 1000 flips , our average profit per flip is
> $$\frac{\$ 1250}{1000}=\$ 1.25 .$$

**Problem 1.20:** In an urn, I have 20 marbles: 2 red, 3 yellow, 4 blue, 5 green, and 6 black. I select one marble at random from the urn, and I win money based on the following chart:

\begin{tabular}{|r||c|c|c|c|c|}
\hline Color & Red & Yellow & Blue & Green & Black \\
\hline Amount won & $\$ 10$ & $\$ 5$ & $\$ 2$ & $\$ 1$ & $\$ 0$ \\
\hline
\end{tabular}

What is the expected value of my winnings?

*Solution for Problem 1.20:* I draw a red marble with probability $\frac{2}{20}$, a yellow marble with probability $\frac{3}{20}$, and so on. Therefore, the expected value is
$$\frac{2}{20}(\$ 10)+\frac{3}{20}(\$ 5)+\frac{4}{20}(\$ 2)+\frac{5}{20}(\$ 1)+\frac{6}{20}(\$ 0)=\frac{\$ 48}{20}=\$ 2.40 .$$

> **Concept:** One common use of the expected value in a problem like Problem 1.20 is to determine a fair price to play the game. The fair price to play is the expected winnings, which is $\$ 2.40$. In the long run, if I were charging people the fair price to play the game, I would expect to break even, neither making nor losing money. If I were running this game at a carnival, I could charge carnival-goers $\$ 2.50$ to play the game, and I would expect to make a 10-cent profit, on average, from each person that plays.

**Problem 1.21:** Suppose I have a bag with 12 slips of paper in it. Some of the slips have a 2 on them, and the rest have a 7 on them. If the expected value of the number shown on a slip randomly drawn from the bag is 3.25 , then how many slips have a 2 ?

*Solution for Problem 1.21:* We let $x$ denote the number of slips with a 2 written on them. (This is the usual tactic of letting a variable denote what we're trying to solve for in the problem.) Then there are $12-x$ slips with a 7 on them.

The probability of drawing a 2 is $\frac{x}{12}$ and the probability of drawing a 7 is $\frac{12-x}{12}$, so the expected value of the number drawn is
$$E=\frac{x}{12}(2)+\frac{12-x}{12}(7)=\frac{84-5 x}{12} .$$

But we are given that $E=3.25$, so we have the equation
$$3.25=\frac{84-5 x}{12}$$

This simplifies to $39=84-5 x$, which means that $x=9$. Thus 9 of the 12 slips have a 2 written on them.

> **Concept:** We said this before about probability, and it's true here too: don't be afraid to use algebra in solving expected value problems.

## 1.5 Pascal's Triangle and the Binomial Theorem

### Problems

**Problem 1.22:** Suppose that we consider Pascal's Triangle to be a grid of dots (in other words, everywhere there's a number, we're just going to place a dot). We can count the number of paths from the top dot to any of the lower dots, where each step of the path is from a dot to one of the two dots immediately below it.

For example, the above diagram shows a path to the circled dot. How many paths are there from the top dot to the circled dot in the above picture?

**Problem 1.23:** Prove that
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r} .$$

**Problem 1.24:** Expand $(x+y)^{n}$.

**Problem 1.25:** What is the coefficient of the term of $\left(x+2 y^{2}\right)^{6}$ with a $y^{8}$ in it?

**Problem 1.26:** Prove that for any $n$,
$$\binom{n}{0}+\binom{n}{1}+\cdots+\binom{n}{n}=2^{n} .$$

> **Extra!** All men's miseries derive from not being able to sit in a quiet room alone. - Blaise Pascal

### Solutions

**Problem 1.22:** Suppose that we consider Pascal's Triangle to be a grid of dots (in other words, everywhere there's a number, we're just going to place a dot). We can count the number of paths from the top dot to any of the lower dots, where each step of the path is from a dot to one of the two dots immediately below it.

For example, the above diagram shows a path to the circled dot. How many paths are there from the top dot to the circled dot in the above picture?

*Solution for Problem 1.22:* We must take a total of 4 steps, since the circled dot is 4 rows below the top dot. Of those 4 steps, 3 of the steps must be down and to the right, and the other step is down and to the left. We can take the 4 steps in any order, so long as 3 are to the right and 1 is to the left. Therefore, the number of paths to the circled dot is the same as the number of ways to arrange 3 steps to the right and 1 step to the left. We must choose 3 of the 4 steps to be to the right, and we know that we can do this is $\binom{4}{3}$ ways. So there are $\binom{4}{3}$ paths from the top of the triangle to the circled dot.

> **Important:** More generally, the number of paths to the $r^{\text {th }}$ dot of Row $n$ (where the top dot is considered to be Row 0) is $\binom{n}{r}$.

While knowing the numbers is important, it's not nearly as important as knowing what the numbers mean-and what they mean is combinations!

**Problem 1.23:** Prove that
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r} .$$

*Solution for Problem 1.23:*

Proof by block-walking on Pascal's Triangle: Let's look at a piece somewhere in the middle of Pascal's Triangle:

We know that each entry is the sum of the two entries immediately above it, since every path to $\binom{n}{r}$ must pass through one or the other of the points immediately above (but not both). Therefore, we conclude that
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r} .$$

Proof by algebra: We start by writing out the algebraic definition of the combinations:
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\frac{(n-1)!}{(r-1)!((n-1)-(r-1))!}+\frac{(n-1)!}{r!(n-1-r)!} .$$

We now can now simplify the denominators, and put both fractions over a common denominator:
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\frac{(n-1)!}{(r-1)!(n-r)!}+\frac{(n-1)!}{r!(n-1-r)!}=\frac{r(n-1)!}{r!(n-r)!}+\frac{(n-r)(n-1)!}{r!(n-r)!} .$$

Now we add the fractions and factor the numerator:
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\frac{r(n-1)!+(n-r)(n-1)!}{r!(n-r)!}=\frac{n(n-1)!}{r!(n-r)!}=\frac{n!}{r!(n-r)!}=\binom{n}{r} .$$

Proof by committee-forming: Given a club with $n$ members, we know that we can form an $r$-person committee in $\binom{n}{r}$ ways. This is just our basic definition of combinations.

Imagine that one of the club members is named Bob. If Bob is on the committee, then we must choose $r-1$ remaining committee members from the $n-1$ remaining club members. So there are $\binom{n-1}{r-1}$ committees with Bob on them.

However, if Bob is not on the committee, then we must choose all $r$ committee members from the $n-1$ remaining club members. So there are $\binom{n-1}{r}$ committees with Bob not on them.

The two situations above are exclusive cases, so to get the total number of committees, we add the number of committees with Bob and the number of committees without Bob. Thus, the number of $r$-person committees is $\binom{n-1}{r-1}+\binom{n-1}{r}$. But we already know that the number of $r$-person committees is $\binom{n}{r}$, so equating these two counts, we again get
$$\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r} .$$

> **Important:** Pascal's identity:
> $$\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r} .$$

> **Concept:** Many combinatorial identities can be proved in one or more of the following ways:
> - By a committee-forming argument
> - By a block-walking argument
> - By algebra

**Problem 1.24:** Expand $(x+y)^{n}$.

*Solution for Problem 1.24:* Let's look at how this works for $(x+y)^{2}$ :
$$\begin{aligned}
(x+y)^{2} & =(x+y)(x+y) \\
& =x x+x y+y x+y y \\
& =x^{2}+2 x y+y^{2}
\end{aligned}$$

On the second line above, we get four terms: each term corresponds to choosing $x$ or $y$ from the first term, then choosing $x$ or $y$ from the second term, and multiplying them together. After simplification, we get our usual result on the third line above.

Just to make sure that it's clear what's happening, let's also look at how this works for $(x+y)^{3}$ :
$$\begin{aligned}
(x+y)^{3} & =(x+y)(x+y)(x+y) \\
& =x x x+x x y+x y x+x y y+y x x+y x y+y y x+y y y \\
& =x^{3}+3 x^{2} y+3 x y^{2}+y^{3} .
\end{aligned}$$

As before, in the second line above, each term is a product of $x$ or $y$ from the first term, times $x$ or $y$ from the second term, times $x$ or $y$ from the third term. We take these products for every possible choice of $x$ or $y$ from each term, and then add them up. When we simplify, we get our usual expression for $(x+y)^{3}$.

Now we can see where the coefficients come from. For example, the coefficient of the $x^{2} y$ term in $(x+y)^{3}$ is 3 . That's because there are 3 ways to choose two $x^{\prime}$ s and one $y$ : $x x y, x y x$, and $y x x$. Alternatively, we can think of this as the number of ways to arrange two $x^{\prime}$ s and one $y$ to make a three-letter "word". And we know how to count this: it's
$$\frac{3!}{2!1!}=\binom{3}{1} .$$

We can also think of this as the number of ways to choose one "slot" for the $y$ in our 3-letter word.

Now let's go back to the general case of $(x+y)^{n}$. Every term in the product results from choosing an $x$ or $y$ from each of the $n$ different $(x+y)$ terms in the product. So if, for example, we choose $k y^{\prime}$ s, the other $n-k$ choices will be $x^{\prime} \mathrm{s}$, and we'll get an $x^{n-k} y^{k}$ term in the product. But $k y^{\prime}$ s can be chosen from $n$ terms in $\binom{n}{k}$ ways. Therefore, the coefficient of $x^{n-k} y^{k}$ is $\binom{n}{k}$.

> **Important:** The Binomial Theorem: for any positive integer $n$, the coefficient of the $x^{n-k} y^{k}$ term of $(x+y)^{n}$ is $\binom{n}{k}$. In other words,
> $$(x+y)^{n}=\binom{n}{0} x^{n}+\binom{n}{1} x^{n-1} y+\cdots+\binom{n}{k} x^{n-k} y^{k}+\cdots+\binom{n}{n} y^{n} .$$

**Problem 1.25:** What is the coefficient of the term of $\left(x+2 y^{2}\right)^{6}$ with a $y^{8}$ in it?

*Solution for Problem 1.25:* How do we get a term in the expansion of $\left(x+2 y^{2}\right)^{6}$ with a $y^{8}$ in it? The term with a $y^{8}$ in it is the term that has a $\left(2 y^{2}\right)^{4}$ in it. We know that when expanding $\left(x+2 y^{2}\right)^{6}$, we have to choose 4 copies of $2 y^{2}$ from the six ( $x+2 y^{2}$ ) terms in order to get a term with $y^{8}$ in it. This can be done in $\binom{6}{4}$ ways. We then take an $x$ from each of the remaining two $\left(x+2 y^{2}\right)$ terms that didn't contribute a $2 y^{2}$. Therefore, the relevant term in the expansion of $\left(x+2 y^{2}\right)^{6}$ is $\binom{6}{4} x^{2}\left(2 y^{2}\right)^{4}=240 x^{2} y^{8}$. The answer is 240 .

> **Concept:** When dealing with the Binomial Theorem, as with most theorems or formulas, it is important to not merely memorize the formula, but to understand it well enough to be able to use it flexibly.

**Problem 1.26:** Prove that for any $n$,
$$\binom{n}{0}+\binom{n}{1}+\cdots+\binom{n}{n}=2^{n} .$$

*Solution for Problem 1.26:* The sum of combinations should definitely remind us of the Binomial Theorem:
$$(x+y)^{n}=\binom{n}{0} x^{n}+\binom{n}{1} x^{n-1} y+\cdots+\binom{n}{n} y^{n} .$$

Plug in $x=1$ and $y=1$ into the Binomial Theorem. This makes all the $x^{\prime}$ s and $y$ s go away!
After we plug in $x=1$ and $y=1$, we're left with:
$$(1+1)^{n}=2^{n}=\binom{n}{0}+\binom{n}{1}+\cdots+\binom{n}{n} .$$

That's what we wanted to prove, so we're done!

> **Concept:** Often we can solve a problem by taking a general expression (which is stated in terms of variables) and plugging in some nice values for the variables to make them go away.

## 1.6 Summation Notation

You've probably already seen expressions like
$$1+2+\cdots+n=\frac{n(n+1)}{2}$$
or
$$a+a r+a r^{2}+\cdots=\frac{a}{1-r}$$

These expressions use "..." to denote missing terms in a sum. Although writing sums like this may be intuitively clear, it is not very mathematically precise. For some expressions, the pattern of the missing terms might not be sufficiently well-defined. For example, if we were to write
$$1+3+\cdots+81$$
are we summing the first 41 positive odd integers, or are we summing the first 5 positive powers of 3 ? Also, in an expression like
$$1+2+\cdots+n$$
we run into a bit of ambiguity if $n \leq 2$ : what are the "missing" terms?

To avoid many of these difficulties, we have a convenient notation that we use to write sums, called summation notation. We use the symbol $\sum$, the capital Greek letter sigma, which stands for "sum." For example, we would write
$$1+2+\cdots+n=\sum_{k=1}^{n} k$$

The symbol $\sum_{k=1}^{n}$ means to take the sum where the different terms are given by plugging in $k=1, k=2$, and so on up through $k=n$. The letter $k$ is not important, and can be any letter not in the sum's terms. The variable $k$ is sometimes called a dummy variable.

To take another simple example,
$$\sum_{i=5}^{11} i^{2}=5^{2}+6^{2}+7^{2}+8^{2}+9^{2}+10^{2}+11^{2}=25+36+49+64+81+100+121=476 .$$

Often we will use summation notation to write identities more concisely. For instance, we can write the Binomial Theorem as
$$(x+y)^{n}=\sum_{k=0}^{n}\binom{n}{k} x^{n-k} y^{k}$$

If the sum is infinite, then we can use the symbol $\infty$ to indicate this. For example, if $|r|<1$, then
$$\sum_{j=0}^{\infty} a r^{j}=\frac{a}{1-r}$$

We will discuss more subtle aspects of summation notation throughout the book as we need them.

## 1.7 Summary

This chapter is a review of the concepts and techniques that you should know before proceeding further with this book. The rest of the book will assume that you know and are comfortable with these techniques. If many of the solutions to the problems in this chapter did not come easily to you, you may want to review more introductory-level material before continuing on with this book.

The book Introduction to Counting \& Probability covers all of the topics in this chapter (except for summation notation), and does so in much greater detail than we did here.
