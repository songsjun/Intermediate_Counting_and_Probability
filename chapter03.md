# Chapter 3: A Piece of PIE

*If you want to make an apple pie from scratch, you must first create the universe. - Carl Sagan*

## 3.1 Introduction

In this chapter we'll have some PIE.
PIE is the abbreviation for the Principle of Inclusion and Exclusion. Despite the fancy name, PIE is actually pretty simple. In fact, for the first few problems, PIE is really just an extension of your common sense, but as we'll see later in this chapter, PIE can be a powerful tool for solving a wide variety of counting problems.

PIE is essentially a special application of one of our most fundamental counting techniques: strategic overcounting. In a typical PIE computation, we will repeatedly overcount and undercount until, at the end of the process, we arrive at exactly the correct count. It may seem a bit confusing, but trust us, it's not as complicated as it sounds. It does, however, require some thought to use PIE correctly; in particular, memorizing a "formula" for PIE is a really bad idea.

## 3.2 PIE With 2 Properties

Problems

**Problem 3.1:** If 20 girls are on my school's soccer team, 25 girls are on my school's hockey team, and 11 girls play both sports, then how many girls play soccer or hockey?

**Problem 3.2:** If $A$ and $B$ are sets, write an expression for the number of elements in $A \cup B$ in terms of the number of elements in $A, B$, and $A \cap B$.

**Problem 3.3:** At my school, the only foreign languages offered are Spanish and French, and there are 40 students enrolled in at least one of the classes. If 28 students are in the Spanish class and 23 students are in the French class, then how many students are taking both languages?

**Problem 3.4:**
(a) How many 6-digit numbers start with an even digit?
(b) How many 6-digit numbers end with an even digit?
(c) How many 6-digit numbers start and end with an even digit?
(d) How many 6-digit numbers start or end with an even digit?

Suppose that we have two sets $A$ and $B$. We'd like to count the number of elements in their union $A \cup B$, which is to say, we want to count the elements that are in $A$ or $B$.

What's wrong with the following argument?

> **Bogus Solution:** The number of elements in $A \cup B$ is the number of elements in $A$
> plus the number of elements in $B$. Or, as an equation,
> $$\#(A \cup B)=\#(A)+\#(B) .$$

This argument doesn't take into account the fact that some elements might be in both sets. To take a simple example, suppose that $A=\{1,2,3\}$ and $B=\{3,4,5\}$. Then $A \cup B=\{1,2,3,4,5\}$, and we see that
$$\#(A \cup B)=5 \text { but } \#(A)+\#(B)=3+3=6 .$$

Let's see a basic example of this phenomenon in a problem setting.

**Problem 3.1:** If 20 girls are on my school's soccer team, 25 girls are on my school's hockey team, and 11 girls play both sports, then how many girls play soccer or hockey?

*Solution for Problem 3.1:* A bogus solution to this would be:

> **Bogus Solution:** There are 20 girls on the soccer team and 25 girls on the hockey
> team, so there are $20+25=45$ girls on either team.

This doesn't work since there are 11 girls on both teams. If we simply count $20+25$, we've counted these 11 girls twice, once on the soccer team and once on the hockey team.

Therefore, we must subtract these girls from our count, since we've counted them twice and we only want to count them once.

So the number of girls playing soccer or hockey is $20+25-11=34$.
We can also see this by using a Venn Diagram.

In order to fill in the numbers, we work from the inside out, as this is usually the best way to proceed with Venn diagrams. So, we start by placing the 11 girls who are on both teams into the center of the diagram.

Then we can place $20-11=9$ girls in the "soccer only" part of the diagram, and $25-11=14$ girls in the "hockey only" part of the diagram.

We can now see that there are $9+11+14=34$ girls on the two teams.

Here's the general idea of this basic version of PIE:
We want to count the number of elements in the union of two sets $A$ and $B$. For example, in Problem 3.1, set $A$ is "girls on the soccer team" and set $B$ is "girls on the hockey team." However, if sets $A$ and $B$ overlap, we cannot merely sum the elements in each set, since elements in both sets would get counted twice. In order to count the elements in $A \cup B$, we need to include the elements of $A$ and the elements of $B$, and then exclude the elements in both. This is why we call this method the Principle of Inclusion and Exclusion.

Let's see the general statement of PIE for counting the number of elements in the union of two sets:

**Problem 3.2:** If $A$ and $B$ are sets, write an expression for the number of elements in $A \cup B$ in terms of the number of elements in $A, B$, and $A \cap B$.

*Solution for Problem 3.2:* We can write PIE for 2 sets as a formula:

> **Important:** $\quad \#(A \cup B)=\#(A)+\#(B)-\#(A \cap B)$

Going back to our first example, Problem 3.1, we can write this in words as
$$\begin{aligned}
\text { Number of girls playing soccer or hockey }= & \text { Number of girls playing soccer } \\
& + \text { Number of girls playing hockey } \\
& - \text { Number of girls playing both soccer and hockey. }
\end{aligned}$$

**Problem 3.3:** At my school, the only foreign languages offered are Spanish and French, and there are 40 students enrolled in at least one of the classes. If 28 students are in the Spanish class and 23 students are in the French class, then how many students are taking both languages?

*Solution for Problem 3.3:* This problem is slightly different from Problem 3.1. Here, we're told not only the sizes of the two sets, but also the size of their union; we want to find the size of their intersection.

Let $x$ be the number of students in both language classes. (Note that we're using the very common problem solving technique of letting a variable denote what we want to find.) Then PIE tells us that
$$40=28+23-x$$
which we can solve to get $x=11$.
As a quick check, we can draw the Venn Diagram for this problem, with all of the numbers filled in:

It is easy to verify from the diagram that there are 28 students in Spanish, 23 students in French, and 40 students total, and thus there are 11 students in both languages.

Problems 3.1 and 3.3 were pretty transparent-it was clear that we needed to count the elements in two overlapping sets, and that PIE was the tool to use. Most PIE problems are not quite so simply stated. Here's an example:

**Problem 3.4:** How many 6-digit numbers start or end with an even digit?

*Solution for Problem 3.4:* The word "or" suggests that we are counting elements in two sets. In this problem, we want to count the 6-digit numbers that are in the union of those that start with an even digit and those that end with an even digit.

> **Concept:** If we want to count things that satisfy some property or some other property, and the two properties overlap, then we probably want to use PIE.

Thus, our strategy is going to be
\#(6-digit numbers that start or end with an even digit) =
\#(6-digit numbers that start with an even digit)
+ \#(6-digit numbers that end with an even digit)
- \#(6-digit numbers that start and end with an even digit)

Each of these terms is fairly easy to count.
6-digit numbers that start with an even digit: There are 4 choices for the first digit ( $2,4,6$, or 8 ), and 10 choices for each remaining digit, so there are $4 \times 10^{5}=400,000$ of these numbers.

6-digit numbers that end with an even digit: There are 9 choices for the first digit (since it can't be 0 ), 10 choices for each of the four middle digits, and 5 choices for the last digit ( $2,4,6,8$, or 0 ), so there are $9 \times 10^{4} \times 5=450,000$ of these numbers.

6-digit numbers that start and end with an even digit: There are 4 choices for the first digit, 10 choices for each of the four middle digits, and 5 choices for the last digit, so there are $4 \times 10^{4} \times 5=200,000$ of these numbers.

Therefore, the number of 6-digit numbers that start or end with an even digit is
$$400,000+450,000-200,000=650,000 .$$

We also could have counted these numbers using complementary counting. We know there are 900,000 6-digit numbers (since there are 9 choices for the first digit and 10 choices for each of the other 5 digits). We also know that there are 250,000 6-digit numbers for which both the first and last digits are odd (since there are 5 choices for the first and last digits, and 10 choices for each of the 4 middle digits). Therefore, there are $900,000-250,000=650,000$ 6-digit numbers for which the first and last digits are not both odd, meaning that at least one of them is even.

> **Concept:** When faced with counting things that are "at least" something or "one or more" of something, our two main tools are PIE and complementary counting.

### Exercises

**3.2.1** There are 47 dogs at the pound. All of them are big or very hairy. 30 are big. 42 are very hairy. How many of the dogs are big, very hairy dogs?

**3.2.2** How many 10-digit binary numbers start with 2 ones or end with 2 ones (or both)?

**3.2.3** Suppose that $80 \%$ of U.S. households own a DVD player and that $70 \%$ of U.S. households own a computer. What is the range of possible percentages of U.S. households that own both? Hints: 25

**3.2.4** How many positive integers less than 100,000 are neither squares nor cubes? Hints: 62

**3.2.5** Of the 85 teachers at my school, 25 have no children, 50 have a son, and 45 have a daughter. How many have a son and a daughter?

**3.2.6** How many 9-digit numbers have the property that the product of their first and last digits is even?

**3.2.7** $\star$ A school with 100 students offers French and Spanish as its language courses. Twice as many students are in the French class as the Spanish class. Three times as many students are in both classes as are in neither class. The number of students in both classes is even, and fewer than 10 students are in neither class. How many students are taking Spanish? Hints: 309, 141

## 3.3 PIE With 3 Properties

Problems

**Problem 3.5:** Now my school offers 3 foreign languages: Spanish, French, and Chinese. There are 57 students enrolled in at least one of the classes. If 29 are in the Spanish class, 34 are in the French class, 33 are in the Chinese class, 15 are taking both French and Spanish, 16 are taking both French and Chinese, and 12 are taking both Spanish and Chinese, then how many students are taking all three languages?

**Problem 3.6:** If $A, B$, and $C$ are three sets, find an expression for the number of elements of $A \cup B \cup C$.

**Problem 3.7:** How many positive integers less than 1000 are divisible by neither 2, 3, nor 5?

We've seen how to use PIE to count the number of elements in the union of two sets. It seems reasonable to ask whether PIE can be used to count the number of elements in the union of a bunch of sets. We'll explore this general question in Section 3.5, but in this section we'll look at the example of counting elements that are in one or more of three different sets. Let's start with a concrete example.

**Problem 3.5:** Now my school offers 3 foreign languages: Spanish, French, and Chinese. There are 57 students enrolled in at least one of the classes. If 29 are in the Spanish class, 34 are in the French class, 33 are in the Chinese class, 15 are taking both French and Spanish, 16 are taking both French and Chinese, and 12 are taking both Spanish and Chinese, then how many students are taking all three languages?

*Solution for Problem 3.5:* Suppose that we try to count the number of students in at least one of the classes. We start with
$$(29 \text { Spanish })+(34 \text { French })+(33 \text { Chinese })=96 .$$

Clearly, though, this is way too big, since it overcounts those students who are in more than one class. Also, we already know that there should be 57 students total, because the problem told us so.

Our first attempt at correcting this is to subtract the number of students who are taking 2 classes: we know those students have been counted twice, so we need to subtract to make sure that they are only counted once. Now our count is.
$$(29+34+33)-(15+16+12)=96-43=53 .$$

But this is now too small, since we know that there are 57 students total. What's wrong here?
The problem is that we have not correctly accounted for those students who are taking all three classes. To see this, imagine that Vincent is taking all three languages. How many times do we count Vincent in our expression $29+34+33-15-16-12$ ?

We add Vincent once in each of the 29, 34, and 33 terms, since he is in all three classes. On the other hand, we subtract him once in the $-15,-16$, and -12 terms, since he is in all three pairs of classes. Therefore, in the expression $29+34+33-15-16-12$, we haven't counted Vincent at all!

Thus, our count $29+34+33-15-16-12=53$ doesn't count the students who are in all three classes. Since $57-53=4$, we are missing 4 students, therefore there are 4 students in all three classes.

We can use a Venn Diagram to check our answer. Using Figure 3.1, you can verify that there are $7+11+4+12=34$ students in the French class, and all of the other data given in the problem can be verified as well.

Figure 3.1: Completed Venn Diagram for Problem 3.5

We can use the logic of Problem 3.5 to come up with a general formula for the number of elements in the union of 3 sets.

**Problem 3.6:** If $A, B$, and $C$ are three sets, find an expression for the number of elements of $A \cup B \cup C$.

*Solution for Problem 3.6:* We start with just summing the elements in the three sets:
$$\#(A)+\#(B)+\#(C) .$$

However, this sum overcounts elements that appear in more than one set. We can try to correct for this by subtracting the number of elements in each pair of sets:
$$\#(A)+\#(B)+\#(C)-\#(A \cap B)-\#(A \cap C)-\#(B \cap C) .$$

If an element is in exactly two sets, it will now be counted exactly once. For example, if $x$ is in $A$ and $B$, then $x$ will be counted once in $\#(A)$ and once in $\#(B)$, but $x$ will also be subtracted once in $\#(A \cap B)$. So $x$ will be added twice and subtracted once, which means that $x$ will be counted one time overall.

Now we look at those elements in all three sets. These elements are added three times when we count the individual sets, but they are also subtracted three times when we subtract the pairs. So these elements have not yet been counted at all! We finish our count by adding them back in.

Our conclusion:

> **Important:** If $A, B, C$ are finite sets, then
> $$\#(A \cup B \cup C)=\#(A)+\#(B)+\#(C)-\#(A \cap B)-\#(A \cap C)-\#(B \cap C)+\#(A \cap B \cap C) .$$

Let's see an application of the 3-set PIE process.

**Problem 3.7:** How many positive integers less than 1000 are divisible by neither 2, 3, nor 5?

*Solution for Problem 3.7:* There seems to be no good direct way to count this, so we think about trying to count the opposite: how many positive integers less than 1000 are divisible by at least one of 2, 3, or 5?

The "at least" in this question should make us think about PIE. Our three sets are:
$A=$ "Positive integers less than 1000 that are divisible by 2"
$B=$ "Positive integers less than 1000 that are divisible by 3"
$C=$ "Positive integers less than 1000 that are divisible by 5"
Our goal is to compute $\#(A \cup B \cup C)$. This means PIE.
What's the easiest way to compute the number of positive integers less than 1000 that are divisible by $n$ ? We simply take the largest integer less than $1000 / n$.

So, using our notation above:
$$\begin{aligned}
\#(A) & =(\text { largest integer less than } 1000 / 2)=499, \\
\#(B) & =(\text { largest integer less than } 1000 / 3)=333, \\
\#(C) & =(\text { largest integer less than } 1000 / 5)=199 .
\end{aligned}$$

Now we can look at the intersections of pairs of the sets:
$$\begin{aligned}
A \cap B & =\text { "Positive integers less than } 1000 \text { that are divisible by } 2 \text { and } 3 \text { " } \\
& =\text { "Positive integers less than } 1000 \text { that are divisible by } 6 \text { " } \\
A \cap C & =\text { "Positive integers less than } 1000 \text { that are divisible by } 2 \text { and } 5 \text { " } \\
& =\text { "Positive integers less than } 1000 \text { that are divisible by } 10 \text { " } \\
C \cap B & =\text { "Positive integers less than } 1000 \text { that are divisible by } 3 \text { and } 5 \text { " } \\
& =\text { "Positive integers less than } 1000 \text { that are divisible by } 15 \text { " }
\end{aligned}$$

We can count these using the same reasoning as above:
$$\begin{array}{l}
\#(A \cap B)=(\text { largest integer less than } 1000 / 6)=166 \\
\#(A \cap C)=(\text { largest integer less than } 1000 / 10)=99 \\
\#(B \cap C)=(\text { largest integer less than } 1000 / 15)=66
\end{array}$$

Finally, we know that $A \cap B \cap C$ is the set of positive integers less than 1000 that are divisible by all of 2, 3, and 5. This is the set of positive integers less than 1000 that are divisible by 30, hence
$$\#(A \cap B \cap C)=(\text { largest integer less than } 1000 / 30)=33 .$$

Therefore, using PIE, we can compute:
$$\begin{aligned}
\#(A \cup B \cup C) & =\#(A)+\#(B)+\#(C)-\#(A \cap B)-\#(A \cap C)-\#(B \cap C)+\#(A \cap B \cap C) \\
& =499+333+199-166-99-66+33 \\
& =733
\end{aligned}$$

Remember, these are the integers less than 1000 that are divisible by at least one 2, 3, or 5. We want those that are not divisible by any of 2, 3, or 5, so we must subtract this answer from 999 (the total number of positive integers less than 1000) to get our final answer of $999-733=266$.

### Exercises

**3.3.1** Dogs in the GoodDog obedience school win a blue ribbon for learning how to sit, a green ribbon for learning how to roll over, and a white ribbon for learning how to stay. There are 100 dogs in the school. Suppose:
- 73 have blue ribbons, 39 have green ribbons, and 62 have white ribbons.
- 21 have a blue ribbon and a green ribbon; 28 have a green ribbon and a white ribbon; 41 have a blue ribbon and a white ribbon.
- 14 have all three ribbons.

How many dogs have not learned any tricks?

**3.3.2** How many 3-letter words (where a "word" is any string of 3 letters) have at least one A? (Solve using PIE.)

**3.3.3** Vernonia High School has 85 senior boys, each of whom plays on at least one of the school's three boys varsity sports teams: football, baseball, and lacrosse. It so happens that 74 are on the football team; 26 are on the baseball team; 17 are on both the football and lacrosse teams; 18 are on both the baseball and football teams; and 13 are on both the baseball and lacrosse teams. Compute the number of senior boys playing all three sports, given that twice this number are members of the lacrosse team. (Source: HMMT)

**3.3.4** Four coins are flipped one after the other. What's the probability of getting two consecutive tails?

**3.3.5** $\star$ A new class of 180 dogs has enrolled in the GoodDog school from Problem 3.3.1. We have the following facts:
- An equal number of dogs have each of the ribbons.
- An equal number of dogs have each pair of ribbons.
- 15 dogs have all three ribbons.
- All dogs have at least one ribbon.
- The number of dogs with exactly one ribbon equals twice the number of dogs with more than one ribbon.

How many dogs have blue ribbons? Hints: 102, 119

**3.3.6** $\star$ How many 6-digit numbers, written in decimal notation, have at least one 1, one 2, and one 3 among its digits? Hints: 96, 290

## 3.4 Counting Problems With PIE

Problems

**Problem 3.8:** How many positive integers less than 180 are relatively prime to 180?

**Problem 3.9:** The Sanders family has 3 boys and 3 girls. In how many ways can the 6 children be seated in a row of 6 chairs, so that the boys aren't all seated together and the girls aren't all seated together?

**Problem 3.10:** We form a 12-card deck by taking the Jacks, Queens, and Kings from a standard deck of cards (so that there are 4 cards of each rank). Arrange these 12 cards in a row at random. What is the probability that:
(a) no 4 cards of the same rank are all together?
(b) no 3 cards of the same suit are all together?

**Problem 3.11:** Two biologists, two chemists, and two physicists go out to dinner and sit at a round table with 6 equally spaced chairs. In how many ways can they sit so that no two scientists of the same type (for example, two biologists) are seated next to each other? (Two seatings that are merely rotations of each other are not considered distinguishably different.)
(a) First, solve the problem using casework: count the number of seatings in which the two biologists are sitting directly opposite from one another, and count the number of seatings in which the two biologists are sitting with one person between them.
(b) Now solve the problem using PIE, by counting the total number of seatings (without any restrictions), then subtracting the number of seatings with at least one pair of like scientists adjacent. (The "at least," as usual, is your signal to use PIE.)

**Problem 3.12:** How many 6-digit binary numbers (numbers with 0's and 1's as digits) have a string of three consecutive 1's appearing in them? (For example, 101110 and 111100 both have a string of three consecutive 1's, but 100110 doesn't).

In most cases, a counting problem won't come with the instruction "Use PIE to solve this problem." You'll have to figure out on your own that PIE is the right tool to use. In this section we'll work through a few problems that call for the use of PIE.

**Problem 3.8:** How many positive integers less than 180 are relatively prime to 180?

*Solution for Problem 3.8:* This problem should remind you of Problem 3.7.
We'll use a slight computational shortcut to make the calculations come out a little nicer than they did in Problem 3.7. Instead of determining the number of positive integers less than 180 that are relatively prime to 180, we'll instead determine the number of positive integers less than or equal to 180 that are relatively prime to 180. Since 180 isn't relatively prime to itself, this doesn't change our final answer.

We start by noting that $180=4 \times 5 \times 9=2^{2} \times 5 \times 3^{2}$. Therefore, a positive integer is relatively prime to 180 if and only if it is not divisible by 2, 3, or 5. As in Problem 3.7, there's no obvious way to count the relatively prime integers directly (though see the Sidenote after this solution for more information on this), but we can use PIE to count the complement of what we want, namely the positive integers less than or equal to 180 that are divisible by at least one of 2, 3, or 5.

Hence, in words, what we are counting is:
\# of integers less than or equal to 180 divisible by at least one of 2, 3, or $5=$
\# of integers less than or equal to 180 divisible by 2
+\# of integers less than or equal to 180 divisible by 3
+ \# of integers less than or equal to 180 divisible by 5
- \# of integers less than or equal to 180 divisible by 2 and 3
- \# of integers less than or equal to 180 divisible by 2 and 5
- \# of integers less than or equal to 180 divisible by 3 and 5
+\# of integers less than or equal to 180 divisible by 2, 3, and 5.

Thus, our calculation is
$$\frac{180}{2}+\frac{180}{3}+\frac{180}{5}-\frac{180}{6}-\frac{180}{10}-\frac{180}{15}+\frac{180}{30}=90+60+36-30-18-12+6=132 .$$

Since there are 180 total positive integers less than or equal to 180, and 132 of them are not relatively prime to 180, that leaves 180-132=48 that are relatively prime to 180.

> **Sidenote:** Given any positive integer $n$, there is a fairly easy formula for computing the number of positive integers less than or equal to $n$ that are relatively prime to $n$. If $p_{1}, p_{2}, \ldots, p_{k}$ are the distinct prime divisors of $n$, then
> $$\phi(n)=n\left(1-\frac{1}{p_{1}}\right)\left(1-\frac{1}{p_{2}}\right) \cdots\left(1-\frac{1}{p_{k}}\right)$$
> is the number of positive integers less than $n$ that are relatively prime to $n$. For example, as we already have computed in Problem 3.8,
> $$\phi(180)=180\left(1-\frac{1}{2}\right)\left(1-\frac{1}{3}\right)\left(1-\frac{1}{5}\right)=180 \cdot \frac{1}{2} \cdot \frac{2}{3} \cdot \frac{4}{5}=48 .$$
>
> This is known as the Euler phi function (or totient function), and has many important applications in number theory, the most well-known of which is Euler's Theorem, which states that
> $$a^{\phi(n)} \equiv 1 \quad(\bmod n)$$
> for all $a$ that are relatively prime to $n$. You can prove the formula for $\phi(n)$ using PIE: try it for yourself in the Challenge Problems.

**Problem 3.9:** The Sanders family has 3 boys and 3 girls. In how many ways can the 6 children be seated in a row of 6 chairs, so that the boys aren't all seated together and the girls aren't all seated together?

*Solution for Problem 3.9:* We can do this problem in two steps. First, we determine how many ways there are to assign the 6 chairs by gender: 3 to boys and 3 to girls. Second, we count the ways to place the boys and the girls into their assigned chairs.

It seems like messy casework to try to count directly the number of legal configurations for the boys and girls, so we think instead of counting the illegal configurations: those configurations where 3 boys or 3 girls are all consecutive.

> **Concept:** Messy casework often means that there is a simpler solution using complementary counting and PIE.

With no restriction, there are $\binom{6}{3}=20$ ways to assign the seats, since we must choose 3 of them for the boys to occupy (the girls will then occupy the other 3). Now we need to determine how many of these 20 configurations are illegal.

There are 4 configurations with the 3 boys together-we could list them as BBBGGG, GBBBGG, GGBBBG, and GGGBBB, or we could reason that there are 4 choices for where the middle boy sits: any of the seats except for the end seats.

Similarly there are 4 configurations with the 3 girls together.
But this does not mean that there are $4+4=8$ illegal configurations! We have double-counted the configurations where both the boys and the girls are together. There are two of these-BBBGGG and GGGBBB-so we must subtract 2 from our total.

Therefore there are 6 illegal configurations of boys and girls, and hence $20-6=14$ legal configurations.

Finally, in each of the 14 legal configurations, we know that there are $3!=6$ ways to assign the boys to their designated sets, and also $3!=6$ ways to assign the girls. Therefore, the number of possible seatings is $14 \times 6 \times 6=504$.

**Problem 3.10:** We form a 12-card deck by taking the Jacks, Queens, and Kings from a standard deck of cards (so that there are 4 cards of each rank). Arrange these 12 cards in a row at random. What is the probability that:
(a) no 4 cards of the same rank are all together?
(b) no 3 cards of the same suit are all together?

*Solution for Problem 3.10:* This problem is very similar to Problem 3.9, in that we are arranging things in a row, subject to a condition that certain groups cannot be together. So for both parts of this problem, we'll use a similar strategy to the one that we used in the solution to Problem 3.9: count the number of illegal configurations, then subtract this count from the total number of configurations to get the count of our successful configurations.

(a) Note that we don't have to worry about the suits at all. The suits are totally irrelevant to this part of the problem.

First we count the number of configurations of the Jacks, Queens, and Kings in the row, without worrying about the condition. We have four J's, four Q's, and four K's to arrange in a line of 12. Without any restriction, this can be done in $\binom{12}{4}\binom{8}{4}=34650$ ways (we choose 4 of the initial 12 spots for the J's, then 4 of the remaining 8 spots for the Q's, and the K's go in the 4 spots that are left over).

Now, we need to determine how many of these configurations are illegal. A configuration is illegal if at least one of the ranks (Jacks, Queens, or Kings) appear together as a group. As we've seen before, the "at least" is a signal to use PIE.

First, we'll count the configurations that have the 4 Jacks together. There are 9 choices for where to place the Jacks (the first Jack must be in any of positions 1 through 9), then there are $\binom{8}{4}$ ways to allocate the remaining spaces for the Queens and Kings. So there are $9 \times\binom{ 8}{4}=630$ configurations with all of the Jacks together.

Similarly, by symmetry, there are 630 configurations with all the Queens together, and 630 configurations with all the Kings together.

But we have overcounted-configurations such as JJJJKKQQQQKK are counted twice, once as a configuration with the Jacks together, and once as a configuration with the Queens together. So we have to subtract off configurations in which two ranks are grouped together.
We count configurations with both the Jacks and Queens together as follows: think of arranging a block of J's, a block of Q's, and four K's into 6 slots. There are 6 choices for where to place the block of J's, then 5 choices for where to place the block of Q's; the K's will go in the remaining empty slots. Therefore, there are $6 \times 5=30$ configurations with the J's and Q's together. Similarly, there are 30 configurations with the J's and K's together, and 30 configurations with the Q's and K's together.

Finally, we count configurations with all three ranks together: we have a block of J's, a block of Q's, and a block of K's. All we need to choose is in what order they appear. Therefore, there are $3!=6$ configurations with all three ranks together, which must be added back to our count.

Thus, there are a total of
$$3(630)-3(30)+6=1806$$
illegal configurations, and hence $34650-1806=32844$ legal configurations. Finally, our probability is $\frac{32844}{34650}=\frac{782}{825} \approx 94.8 \%$.

(b) Similarly to part (a), we don't have to worry about the ranks of the cards here. All we have to do is keep track of the suits.

We proceed in a manner similar to part (a). We start by noting that there are $\binom{12}{3}\binom{9}{3}\binom{6}{3}=369,600$ possible configurations: we choose 3 of the 12 spaces for the $\spadesuit$, then 3 of the 9 remaining spaces for the $\heartsuit$s, then 3 of the remaining 6 spaces for the $\diamondsuit$s, then the $\clubsuit$s go in the final 3 spaces.

To count the number of arrangements with all of the $\spadesuit$s together, we note that there are 10 choices for where the $\spadesuit$s go, then there are $\binom{9}{3}\binom{6}{3}$ ways to allocate the remaining suits. So there are $10\binom{9}{3}\binom{6}{3}=16800$ configurations with the 3 $\spadesuit$s together. By symmetry, there are also 16800 configurations for each of the other three suits being together.

Next, we look at configurations with pairs of suits together. For example, if we want all of the $\spadesuit$s together and all of the $\heartsuit$s together, there are $8 \times 7 \times\binom{ 6}{3}=1120$ configurations (thinking of the $\spadesuit$s as a block and the $\heartsuit$s as a block). There are this many configurations for each of the $\binom{4}{2}=6$ pairs of suits.

Next, we count configurations with 3 suits together. For example, if we want all of the $\heartsuit$s, $\spadesuit$s, and $\diamondsuit$s to be together, there are $6 \times 5 \times 4=120$ configurations. There are 120 configurations for each of the 4 choices of 3 suits to keep together.

So far, we have
$$4(16800)-6(1120)+4(120)=60960$$
configurations counted. Is this count correct? Is it too high? Too low?
We know, based on our previous work with PIE, that this accurately counts all configurations with 1, 2, or 3 suits together. But it doesn't correctly count the configurations with all 4 suits together. These configurations are counted 4 times in the first term, subtracted 6 times in the second term, then added back 4 times in the third term, for a net total of being counted twice. Therefore, we need to subtract them once to get them properly counted once overall.

There are $4!=24$ configurations with all four suits together (we merely have to choose in what order the four suits appear), so our complete count of configurations with at least one suit together is $60960-24=60936$.

This means that there are $369600-60936=308664$ configurations with no suit all together; hence, the probability of this occurring is
$$\frac{308664}{369600}=\frac{12861}{15400} \approx 83.5 \%$$

**Problem 3.11:** Two biologists, two chemists, and two physicists go out to dinner and sit at a round table with 6 equally spaced chairs. In how many ways can they sit so that no two scientists of the same type (for example, two biologists) are seated next to each other? (Two seatings that are merely rotations of each other are not considered distinguishably different.)

*Solution for Problem 3.11:* We can solve this problem using casework-let's do so, for practice.
We start by arbitrarily seating one of the biologists in any seat. Since we're dealing with a round table, this isn't really a "choice," since we can always rotate the table. Now there are two cases, depending on where we seat the other biologist.

Case 1: The other biologist sits directly opposite the first. Then to complete the seating, we must have one chemist and one physicist on either side of each biologist. We have 4 choices for where the first chemist sits (since there are 4 empty seats), then 2 choices for where the other chemist sits (since she cannot sit next to the first chemist). To finish, we have 2 choices for how to seat the two physicists. So there are a total of $4 \times 2 \times 2=16$ seatings in this case.

Case 2: The other biologist sits 2 seats away from the first. There are 2 choices here ( 2 seats to the left or 2 seats to the right). We then have 4 choices for the person to sit between the biologist. The other person of the same science must then sit directly opposite, so that the remaining two people are not next to each other. Finally, there are 2 choices for seating the remaining two people. So there are $4 \times 2 \times 2=16$ seatings in this case.

This gives a total of $16+16=32$ seatings.

Now let's look at the PIE solution. This is a basic PIE calculation-in words, what we want to compute is:
$$\begin{aligned}
\# \text { of seatings with no pair adjacent }= & \# \text { of seatings (with no restriction) } \\
& -\# \text { of seatings with } 1 \text { pair adjacent } \\
& +\# \text { of seatings with } 2 \text { pairs adjacent } \\
& -\# \text { of seatings with all } 3 \text { pairs adjacent. }
\end{aligned}$$

Because this is a round table, there are $6!/ 6=5!=120$ ways to seat the six people-there are $6!$ ways to arrange 6 people, but we have to divide by 6 due to the symmetries of rotation.

Suppose we want to sit one specified pair together. We can seat them anywhere at the table (it doesn't matter where because of the rotational symmetry), and then there are 4! ways to seat the remaining 4 people. There are also 2 ways to seat the two people within the pair, so there are a total of $2 \cdot 4!=48$ ways to seat all the people with one specified pair together. There are 3 different pairs, so we have to subtract $3(48)$ from our initial count of 120.

Now suppose we want to sit two specified pairs together. We can seat the first pair anywhere. We then consider the second pair as a unit, so there are 3! ways to seat the second pair and the other two people. There are also 2 ways to seat the people within each pair, so there are a total of $2^{2} \cdot 3!=24$ ways to seat all the people with two specified pairs together. There are 3 choices of two pairs, so we have to add 3(24) back to our running count.

Finally, if we wish to seat all three pairs together, there are 2 ways to arrange the pairs, and 2 ways to arrange the people within each pair, for a total of $2^{3} \cdot 2=16$ ways to seat all the people with all three pairs together.

Therefore, the final answer is:
$$120-3(48)+3(24)-16=32 .$$

**Problem 3.12:** How many 6-digit binary numbers (numbers with 0's and 1's as digits) have a string of three consecutive 1's appearing in them? (For example, 101110 and 111100 both have a string of three consecutive 1's, but 100110 doesn't).

*Solution for Problem 3.12:* There are four possible positions for a run of three ones: 111???, ?111??, ??111?, and ???111.

We can save ourselves a bit of work by noticing that everything of the form ?111?? must have a 1 in the first slot as well (since every 6-digit number begins with a 1), so everything of the form ?111?? is included in those numbers of the form 111???. So we really have only three types of 6-digit numbers to worry about: 111???, 1?111?, and 1??111.

There are 8 numbers of the form 111???, 4 numbers of the form 1?111?, and 4 numbers of the form 1??111 (in each case, there are 2 choices for a digit to replace each "?").

Now we count the numbers that fall into more than one of the above categories. There are 2 numbers of the form 11111?, 1 number of the form 111111, and 2 numbers of the from 1?1111.

Finally, there is one number of all three forms, namely 111111.
So the number of 6-digit numbers with at least one run of three 1's is $8+4+4-2-1-2+1=12$.
It is also pretty easy to list them: 100111, 101110, 101111, 110111, and all 8 numbers of the form 111???.

### Exercises

**3.4.1** In how many ways can we arrange the letters of the word STRATA so that the two A's are nonconsecutive and the two T's are also nonconsecutive?

**3.4.2** How many positive integers less than 211 are relatively prime to 126?

**3.4.3** How many positive integers less than 1000 are relatively prime to both 10 and 12?

**3.4.4** 3 fans each from Austin High School, Butler High School, and Central High School are seated in a row of 9 seats. In how many ways can we seat the fans if no three fans from the same school are all three seated consecutively?

**3.4.5** 15 students are each going to enroll in exactly one of economics, psychology, or sociology. In how many ways can they enroll, provided that no class is left empty? Hints: 222

## 3.5 PIE With Many Properties

Problems

**Problem 3.13:** How many positive integers less than 1000 are not divisible by a 1-digit prime?

**Problem 3.14:** Let $A_{1}, A_{2}, \ldots, A_{n}$ be $n$ sets. Find an expression for the number of elements of $A_{1} \cup A_{2} \cup \cdots \cup A_{n}$.

**Problem 3.15:** In how many ways can we seat 5 pairs of twins in a row of 10 chairs, such that nobody sits next to his or her twin?

In Problem 3.10 we had our first taste of a PIE problem with more than 3 sets. The general concept of PIE is the same no matter how many sets we have-we alternately overcount and undercount, and make sure that every outcome that we want gets counted exactly once.

**Problem 3.13:** How many positive integers less than 1000 are not divisible by a 1-digit prime?

*Solution for Problem 3.13:* We can more easily count the positive integers less than or equal to 1000 that are not divisible by a 1-digit prime. (This will give us the same answer as the original problem, as the number 1000 will not be in our count.)

The one-digit primes are $2,3,5$, and 7. Let $\lfloor n\rfloor$ denote the greatest integer less than or equal to $n$. Then we can proceed in a similar manner as in Problem 3.8, and count the number of positive integers less than or equal to 1000 that are divisible by at least one of $2,3,5$, or 7. The PIE calculation is:
$$\text { \#'s divisible by } 2,3,5 \text {, or } 7=\begin{aligned}
& \left\lfloor\frac{1000}{2}\right\rfloor+\left\lfloor\frac{1000}{3}\right\rfloor+\left\lfloor\frac{1000}{5}\right\rfloor+\left\lfloor\frac{1000}{7}\right\rfloor \\
& -\left(\left\lfloor\frac{1000}{6}\right\rfloor+\left\lfloor\frac{1000}{10}\right\rfloor+\left\lfloor\frac{1000}{14}\right\rfloor+\left\lfloor\frac{1000}{15}\right\rfloor+\left\lfloor\frac{1000}{21}\right\rfloor+\left\lfloor\frac{1000}{35}\right\rfloor\right) \\
& +\left(\left\lfloor\frac{1000}{30}\right\rfloor+\left\lfloor\frac{1000}{42}\right\rfloor+\left\lfloor\frac{1000}{70}\right\rfloor+\left\lfloor\frac{1000}{105}\right\rfloor\right) \\
& -\left\lfloor\frac{1000}{210}\right\rfloor
\end{aligned}$$

This works out to
$$500+333+200+142-(166+100+71+66+47+28)+(33+23+14+9)-4=772$$

Therefore there are $1000-772=228$ positive integers less than (or less than or equal to) 1000 that are not divisible by a 1-digit prime.

**Problem 3.14:** Let $A_{1}, A_{2}, \ldots, A_{n}$ be $n$ sets. Find an expression for the number of elements of $A_{1} \cup A_{2} \cup \cdots \cup A_{n}$.

*Solution for Problem 3.14:* Based on what we've done before, we expect that we should successively add and subtract the sizes of the intersections of more and more sets. Specifically, we should get:
$$\begin{aligned}
\#\left(A_{1} \cup A_{2} \cup \cdots \cup A_{n}\right)= & \#\left(A_{1}\right)+\#\left(A_{2}\right)+\cdots+\#\left(A_{n}\right) \\
& -\left(\#\left(A_{1} \cap A_{2}\right)+\#\left(A_{1} \cap A_{3}\right)+\cdots+\#\left(A_{n-1} \cap A_{n}\right)\right) \\
& +\left(\#\left(A_{1} \cap A_{2} \cap A_{3}\right)+\cdots+\left(A_{n-2} \cap A_{n-1} \cap A_{n}\right)\right) \\
& -\left(\#\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4}\right)+\cdots\right) \\
& +\quad \vdots \\
& +(-1)^{n+1} \#\left(A_{1} \cap A_{2} \cap \cdots \cap A_{n}\right) .
\end{aligned}$$

How can we prove that this is indeed the correct formula?
As always, the goal of PIE is to make sure that every element is counted once and only once. Therefore, we can take an arbitrary element of the union of the sets, and count how many times it is counted in the above expression. We do this by considering the number of individual sets that our element is a member of. In particular, suppose element $x$ is in exactly $k$ of the $A_{i}$'s, where $1 \leq k \leq n$. Let's count the number of terms in which $x$ gets counted.
$x$ appears in $k$ of the sets, so it's counted $+k$ times in the first line of the formula.
$x$ appears in $\binom{k}{2}$ of the intersections of pairs of sets, so it's counted $-\binom{k}{2}$ times in the second line of the formula.
$x$ appears in $\binom{k}{3}$ of the intersections of triples of sets, so it's counted $+\binom{k}{3}$ times in the third line of the formula.

This pattern continues, until we get to the $k^{\text {th }}$ line of the formula, in which $x$ appears in only one intersection of $k$ sets, so it's counted $(-1)^{k+1}$ times (it's counted +1 if $k$ is odd, and -1 if $k$ is even).

Thus $x$ gets counted a total of
$$k-\binom{k}{2}+\binom{k}{3}-\cdots+(-1)^{k+1}$$
times. We need to prove that this quantity equals 1, meaning that our element $x$ gets counted exactly once.

Let's rewrite the above expression so that all the terms are binomial coefficients:
$$\binom{k}{1}-\binom{k}{2}+\binom{k}{3}-\cdots+(-1)^{k+1}\binom{k}{k} .$$

Only one of the binomial coefficients with top entry $k$ is missing, namely $\binom{k}{0}$. If we add and subtract $\binom{k}{0}=1$ to the expression, then things become clear:
$$\left(-\binom{k}{0}+\binom{k}{1}-\binom{k}{2}+\binom{k}{3}-\cdots+(-1)^{k+1}\binom{k}{k}\right)+1 .$$

The term in parentheses in the previous expression is simply the binomial expansion of $0^{k}=(1-1)^{k}$ using the Binomial Theorem. So the element $x$ is counted exactly once by our formula. We've now shown that every element that appears in exactly $k$ sets is counted exactly once, for all $1 \leq k \leq n$. Thus our formula is correct.

Once again, here is the formula for PIE with $n$ sets:

> **Important:** If $A_{1}, A_{2}, \ldots, A_{n}$ are sets, then
> $$\begin{aligned}
> \#\left(A_{1} \cup A_{2} \cup \cdots \cup A_{n}\right)= & \#\left(A_{1}\right)+\#\left(A_{2}\right)+\cdots+\#\left(A_{n}\right) \\
> & -\left(\#\left(A_{1} \cap A_{2}\right)+\#\left(A_{1} \cap A_{3}\right)+\cdots+\#\left(A_{n-1} \cap A_{n}\right)\right) \\
> & +\left(\#\left(A_{1} \cap A_{2} \cap A_{3}\right)+\cdots+\left(A_{n-2} \cap A_{n-1} \cap A_{n}\right)\right) \\
> & -\left(\#\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4}\right)+\cdots\right) \\
> & +\quad \vdots \\
> & +(-1)^{n+1} \#\left(A_{1} \cap A_{2} \cap \cdots \cap A_{n}\right) .
> \end{aligned}$$

Let's try using PIE in a problem with a large number of sets:

**Problem 3.15:** In how many ways can we seat 5 pairs of twins in a row of 10 chairs, such that nobody sits next to his or her twin?

*Solution for Problem 3.15:* Trying to count this directly would involve a lot of messy casework. So instead we count the complement, which is the number of ways to seat the 10 people such that at least one set of twins sit together.

For any pair of twins, there are 9! ways to seat the twins (thought of as a block) and the other 8 people, then 2 ways to seat the twins within their block. So, given a set of twins, there are $2 \cdot 9!$ ways to seat the 10 people so that the given pair of twins sits together. Note also that there are $\binom{5}{1}$ ways to choose the pair of twins to be seated together. So the first term of our PIE calculation will be $\binom{5}{1} 2 \cdot 9!$.

For any two pairs of twins, there are 8! ways to seat the two pairs and the other 6 people, and 2 ways to seat each of the two twins within each pair, so there are $2^{2} \cdot 8!$ ways to seat the 10 people with the designated pairs together. Also, there are $\binom{5}{2}$ ways to choose two pairs of twins, so the second term of our PIE calculation will be $\binom{5}{2} 2^{2} \cdot 8!$.

For any three pairs of twins, there are 7! ways to seat the three pairs and the other 4 people, so there are $2^{3} \cdot 7!$ to seat the 10 people with the three designated pairs together. There are $\binom{5}{3}$ choices for the three pairs of twins. Similarly, there are $2^{4} \cdot 6!$ ways to seat four designated pairs together, and there are $2^{5} \cdot 5!$ ways to seat all five pairs together, with $\binom{5}{4}$ and $\binom{5}{5}$ choices, respectively, for the pairs.

Therefore, there are
$$\binom{5}{1} 2 \cdot 9!-\binom{5}{2} 2^{2} \cdot 8!+\binom{5}{3} 2^{3} \cdot 7!-\binom{5}{4} 2^{4} \cdot 6!+\binom{5}{5} 2^{5} \cdot 5!$$

ways to seat the 10 people so that at least one pair of twins is together. Hence there are
$$10!-\binom{5}{1} 2 \cdot 9!+\binom{5}{2} 2^{2} \cdot 8!-\binom{5}{3} 2^{3} \cdot 7!+\binom{5}{4} 2^{4} \cdot 6!-\binom{5}{5} 2^{5} \cdot 5!$$
ways to seat them so that no pair of twins is together. This can be simplified by factoring out $5!$:
$$5!(30240-30240+13440-3360+480-32)=(120)(10528)=1,263,360 .$$

This may seem like a lot, but it's quite a bit less than $10!=3,628,800$. If we were to seat the twins randomly, then the probability that no person is sitting next to his or her twin is
$$\frac{1,263,360}{3,628,800}=\frac{47}{135} \approx 34.8 \%$$

### Exercises

**3.5.1** How many positive integers less than 529 are relatively prime to 462?

**3.5.2** Yeechi has a deck of cards consisting of the 2 through 5 of hearts and the 2 through 5 of spades. She deals two cards (at random) to each of four players. What is the probability that no player receives a pair? (Source: Mandelbrot) Hints: 195

**3.5.3** $\star$ Three Americans, three Canadians, three Spaniards, and three Russians are flying on a small plane that consists of 6 rows of 2 seats each. In how many ways can they be seated, so that no two people from the same country sit in the same row? Hints: 180

**3.5.4** $\star$ Each square of a $3 \times 3$ grid of squares is painted black or white with equal probability. What is the probability that the grid does not contain a $2 \times 2$ square that is entirely white? (Source: AIME) Hints: 82, 314

## 3.6 Counting Items With More Than 1 of Something

Problems

**Problem 3.16:** My school now offers 3 new foreign languages: Arabic, Japanese, and Russian. There are 50 students enrolled in at least one of the classes. Suppose that 18 are taking both Arabic and Japanese, 15 are taking both Arabic and Russian, 13 are taking both Japanese and Russian, and 7 are taking all three languages. We wish to count how many students are taking at least two languages.
(a) Why is the answer not $18+15+13-7$ ?
(b) What is the answer?

**Problem 3.17:** If $A, B$, and $C$ are three sets, how can we count the number of elements in at least two of the sets?

**Problem 3.18:**
(a) How many positive integers less than 2000 are divisible by at least two of 2, 3, and 5?
(b) How many positive integers less than 2000 are divisible by exactly two of 2, 3, and 5?

**Problem 3.19:** Five standard 6-sided dice are rolled. What is the probability that at least 3 of them show a $\because$

**Problem 3.20:** Suppose $A_{1}, A_{2}, \ldots, A_{7}$ are sets. Determine an expression that counts the number of elements that are in at least 5 of the sets.

We've seen that PIE is a good tool for counting items that have "at least 1" of a set of properties. But what if we want to count items that have "at least 2" of a set of properties? Does PIE work in the same way?

Sort of. Let's see an example:

**Problem 3.16:** My school now offers 3 new foreign languages: Arabic, Japanese, and Russian. There are 50 students enrolled in at least one of the classes. If 18 are taking both Arabic and Japanese, 15 are taking both Arabic and Russian, 13 are taking both Japanese and Russian, and 7 are taking all three languages, then how many students are taking at least two languages?

*Solution for Problem 3.16:* We could naively use PIE as follows:

> **Bogus Solution:** We initially count $18+15+13$ students, but that overcounts the
> students in all three languages, so we subtract 7, and get as our answer $18+15+13-7=39$ students in at least two languages.

This seems right, but a Venn Diagram quickly shows us the error of our ways. We can construct a partial Venn Diagram, starting with the 7 students in all three languages, and filling in the appropriate numbers for the students in two languages; the result is at right. Notice how this Venn Diagram encapsulates all the given information from the problem (except for the 50 total students, which is irrelevant). Then by summing the numbers in the diagram, we see that there are $11+8+7+6=32$ students in at least 2 languages.

Why did our Bogus Solution not work?
Think about how many times a student in all three languages is counted in our initial count of $18+15+13$. Such a student is
counted three times, once for each pair of classes. Since we only want to count every student once, we need to subtract this student twice in order to get a correct count. Therefore, the correct PIE expression is
$$18+15+13-2(7)=46-14=32,$$

which matches the number that we got from the Venn Diagram.

As we saw in Problem 3.16, using PIE properly requires that we think about what we're doing, and not mindlessly add and subtract numbers.

> **Concept:** Don't memorize a "formula" for PIE. Instead, think about how many times each item is counted, and make sure that each item is counted once and only once.

Let's look at the general case of the situation from Problem 3.16.

**Problem 3.17:** If $A, B$, and $C$ are three sets, how can we count the number of elements in at least two of the sets?

*Solution for Problem 3.17:* We start by counting the number of elements in pairs of sets; that is,
$$\#(A \cap B)+\#(A \cap C)+\#(B \cap C) .$$

However, any element that is in all three sets is in all three of these pairs, and will thus be counted 3 times. Since we only want to count it once, we must subtract twice the number of elements in all three sets. So the number of elements in at least 2 sets is
$$\#(A \cap B)+\#(A \cap C)+\#(B \cap C)-2 \#(A \cap B \cap C) .$$

**Problem 3.18:**
(a) How many positive integers less than 2000 are divisible by at least two of 2, 3, and 5?
(b) How many positive integers less than 2000 are divisible by exactly two of 2, 3, and 5?

*Solution for Problem 3.18:*
(a) We can use the expression that we just found in Problem 3.17. The answer is
$$\left\lfloor\frac{1999}{6}\right\rfloor+\left\lfloor\frac{1999}{10}\right\rfloor+\left\lfloor\frac{1999}{15}\right\rfloor-2\left\lfloor\frac{1999}{30}\right\rfloor=333+199+133-2(66)=533 .$$
(b) We simply need to subtract, from our answer to part (a), the number of elements that are divisible by all three of 2, 3, and 5. There are $\left\lfloor\frac{1999}{30}\right\rfloor=66$ of these, so the answer is $533-66=467$.

We've done "at least 2." Let's see if we can do "at least 3."

**Problem 3.19:** Five standard 6-sided dice are rolled. What is the probability that at least 3 of them show a $\because$

*Solution for Problem 3.19:* As hopefully you've come to expect by now, the phrase "at least" in the problem statement is our signal that we want to think about using PIE.

First, of course, there are $6^{5}=7776$ equally likely possible outcomes for rolling the 5 dice. Now we count the successful outcomes, those in which at least three dice show $\because$

We start by counting outcomes in which a specific set of three dice show $\because$ There are $\binom{5}{3}=10$ choices for 3 dice out of 5 to come up $\because$ For any chosen 3 dice, there are $6^{2}$ ways for those three dice to be $\because$ and the other two dice to be anything, since there are 6 choices for each of the "anything" dice. This gives an initial count of $10 \cdot 6^{2}=360$ successful outcomes. However, outcomes with 4 dice showing $\because$ are counted 4 times in our above count, once for each subset of 3 $\because$'s in the set of 4 $\because$'s. Since we only want to count these outcomes once, we must subtract these outcomes 3 times from our original count. There are $\binom{5}{4}=5$ choices for 4 dice out of 5 to show $\because$, and once we have chosen the 4 dice, the $5^{\text {th}}$ die is arbitrary. Thus, there are $5 \cdot 6=30$ outcomes with four dice showing $\because$ As we discussed above, we need to subtract this 3 times from our original count of 360, so at this point we have $360-3(30)=270$ successful outcomes.

We now know that this count of 270 accurately counts the outcomes in which we have exactly 3 $\because$'s

This outcome (all $\because$'s) is counted +10 times in our 360 term, since it appears once for each of the $\binom{5}{3}=10$ subsets of three dice out of the five. It is then counted $-3(5)=-15$ times in our -90 term, since it appears three times for each of the $\binom{5}{4}=5$ subsets of four dice out of the five. Therefore, it is counted a total of $10-15=-5$ times. We need it counted (positively) once, so we need to add it back 6 times, which means that we need to add 6 to our count.

Thus there are $360-90+6=276$ successful outcomes, and the probability of success is
$$\frac{276}{7776}=\frac{23}{648} \approx 3.55 \%$$

Now that we've done "at least 2" and "at least 3," you may wonder if we can count "at least $k$" for any $k$. The answer is yes, we can, but to write a general formula is fairly difficult, and we're going to defer it to later in the book. However, it's not too hard to figure out the formula for a specific example. It does require us to think a little bit and not blindly add and subtract. Let's try one:

**Problem 3.20:** Suppose $A_{1}, A_{2}, \ldots, A_{7}$ are sets. Determine an expression that counts the number of elements that are in at least 5 of the sets.

*Solution for Problem 3.20:* We begin by summing all of the intersections of 5 sets. There are $\binom{7}{5}=21$ of these intersections:
$$\underbrace{\#\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4} \cap A_{5}\right)+\#\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4} \cap A_{6}\right)+\cdots+\#\left(A_{3} \cap A_{4} \cap A_{5} \cap A_{6} \cap A_{7}\right)}_{\binom{7}{5}=21 \text { terms }}$$

This sum counts once each element that appears in exactly 5 sets, since each such element only appears in one term of (*). We will abbreviate this sum using the following somewhat sloppy notation:
$$\sum_{21 \text { terms }} \#(\text { intersections of } 5 \text { sets). }$$

If an element appears in exactly 6 sets, it is counted 6 times in (*), since there are $\binom{6}{5}=6$ ways to choose 5 of the 6 sets that the element appears in. Since we only want to count these elements once, we need to subtract the sum of the 6-fold intersections 5 times:
$$-5 \underbrace{\left(\#\left(A_{1} \cap A_{2} \cap \cdots \cap A_{6}\right)+\#\left(A_{1} \cap A_{2} \cap \cdots \cap A_{7}\right)+\cdots+\#\left(A_{2} \cap A_{3} \cap \cdots \cap A_{7}\right)\right)}_{\binom{7}{6}=7 \text { terms }}$$

Once again, we will abbreviate this term with the notation
$$-5 \cdot \sum_{7 \text { terms }} \#(\text { intersections of } 6 \text { sets). }$$

Finally, we look at the elements that appear in all 7 sets. These elements appear in every term of both (*) and (**), so they are added 21 times in (*) and subtracted $5 \cdot 7=35$ times in (**); hence they have been counted a net $21-35=-14$ times. Since we want to count them exactly once, we need to add them back 15 times.

So our "formula" is
$$\begin{aligned}
\#(\text { elements in at least } 5 \text { sets })= & \sum_{21 \text { terms }} \#(\text { intersections of } 5 \text { sets }) \\
& -5 \cdot \sum_{7 \text { terms }} \#(\text { intersections of } 6 \text { sets }) \\
& +15 \cdot \#(\text { intersection of } 7 \text { sets })
\end{aligned}$$

### Exercises

**3.6.1** How many positive integers less than or equal to 3150 have at least three different prime factors in common with 3150?

**3.6.2** The four sets $A, B, C$, and $D$ satisfy
$$\begin{array}{c}
\#(A \cap B)=166, \quad \#(A \cap C)=100, \quad \#(A \cap D)=71, \quad \#(B \cap C)=66, \quad \#(B \cap D)=47, \quad \#(C \cap D)=28, \\
\#(A \cap B \cap C)=33, \quad \#(A \cap B \cap D)=23, \quad \#(A \cap C \cap D)=14, \quad \#(B \cap C \cap D)=9 \\
\#(A \cap B \cap C \cap D)=4 .
\end{array}$$
(a) How many elements belong to at least two of the sets $A, B, C$, and $D$?
(b) How many elements belong to exactly two of the sets $A, B, C$, and $D$?

**3.6.3** Four standard 6-sided dice are rolled.
(a) What is the probability that at least 3 of them are $\therefore$ or greater?
(b) What is the probability that exactly 3 of them are $\because$ or greater?

Hints: 65

**3.6.4** Let $A, B, C, D, E$ be five sets, and let $S_{2}$ be the set of elements that appear in at least two of the five sets. Find constants $p, q, r$, and $s$ such that
$$\begin{aligned}
\#\left(S_{2}\right)= & p[\#(A \cap B)+\#(A \cap C)+\#(A \cap D)+\#(A \cap E)+\#(B \cap C) \\
& +\#(B \cap D)+\#(B \cap E)+\#(C \cap D)+\#(C \cap E)+\#(D \cap E)] \\
+ & q[\#(A \cap B \cap C)+\#(A \cap B \cap D)+\#(A \cap B \cap E)+\#(A \cap C \cap D)+\#(A \cap C \cap E) \\
& +\#(A \cap D \cap E)+\#(B \cap C \cap D)+\#(B \cap C \cap E)+\#(B \cap D \cap E)+\#(C \cap D \cap E)] \\
+ & r[\#(A \cap B \cap C \cap D)+\#(A \cap B \cap C \cap E)+\#(A \cap B \cap D \cap E)+\#(A \cap C \cap D \cap E)+\#(B \cap C \cap D \cap E)] \\
+ & s \#(A \cap B \cap C \cap D \cap E) .
\end{aligned}$$

Hints: 117

## 3.7 Some Harder PIE Problems

Problems

**Problem 3.21:** 7 people are having a water balloon fight. At the same time, each of the 7 people throws a water balloon at one of the other 6 people, chosen at random. What is the probability that there are 2 people who throw balloons at each other?

**Problem 3.22:** In how many ways can we arrange 5 A's, 7 B's, and 4 C's into a 16-letter word, such that there are at least three 'CA' pairs occurring in the word (in order words, there are at least 3 occurrences of a 'C' immediately followed by an 'A')?

**Problem 3.23:** In how many ways can we choose 4 vertices of a convex $n$-gon (where $n>4$) to form a convex quadrilateral, such that at least 1 side of the quadrilateral is a side of the $n$-gon?

**Problem 3.24:** I have a coat with area 5. The coat has 5 patches on it. Each patch has area at least 2.5. Prove that 2 patches exist with common area of at least 1. (Source: PSS)

> **WARNING!!** This is a very hard problem. It requires both a solid understanding of PIE and a good insight as to how to properly use it. Think about the problem for a little while, but don't be discouraged if you don't make much progress.

In this section we'll be looking at problems that call for a nontrivial use of PIE.

**Problem 3.21:** 7 people are having a water balloon fight. At the same time, each of the 7 people throws a water balloon at one of the other 6 people, chosen at random. What is the probability that there are 2 people who throw balloons at each other?

*Solution for Problem 3.21:* First, we determine the total number of outcomes. Since each person has 6 equally likely choices (each can be throwing at any of the other 6 people), and there are 7 people, we have $6^{7}$ total possibilities.

Now we'd like to count the "successful" outcomes: those outcomes in which at least 2 people are throwing balloons at each other. As we've seen many times before, the "at least" is your signal to consider either PIE or complementary counting. However, a quick look at the complement-trying to count those cases in which no pair is throwing at each other-seems to lead to a calculation that degenerates into some really messy casework (try it and see for yourself if you don't believe me). So we'll try counting this directly, and for that we'll use PIE.

First, we count the number of outcomes in which any particular pair is throwing at each other. There are $\binom{7}{2}=21$ pairs of people. Besides the pair throwing at each other, the other 5 people each have 6 choices each. So there are $21 \cdot 6^{5}$ total possibilities.

However, this overcounts those outcomes in which two or more pairs are throwing at each other. So we have to correct for this overcount. This is the point in the solution where it is most likely that you would make a mistake:

> **Bogus Solution:** There are $\binom{7}{2}\binom{5}{2}=21 \cdot 10=210$ ways to choose two pairs of people, since there are $\binom{7}{2}=21$ ways to choose one pair from 7 people and then $\binom{5}{2}=10$ ways to choose a second pair from the remaining 5 people.

Seems right, but there's a subtle error. The error is that this counts the number of ways to choose a "first" pair and then choose a "second" pair. What we really want to count is the number of ways to choose two pairs, without regard to order. So we must divide $\binom{7}{2}\binom{5}{2}$ by 2 to correct for this overcount. Thus there are $210 / 2=105$ ways to choose two pairs of people.

Once we have chosen our two pairs, there are three people left over who each have 6 choices of person to throw at. Thus there are $105 \cdot 6^{3}$ total possibilities with two pairs. Since each two-pair case is counted twice in our original $21 \cdot 6^{5}$ count, we have to subtract our new count once, so that our running total at this point is
$$\left(21 \cdot 6^{5}\right)-\left(105 \cdot 6^{3}\right)$$

How many times do we count possibilities in which there are 3 pairs of people throwing at each other? These possibilities are counted 3 times in the first term (once for each of the 3 pairs), and subtracted 3 times in the second term (once for each 2-pair subset of the 3 pairs). Thus they currently aren't being counted at all, and we have to add them back in.

There are $\binom{7}{2}=21$ ways to choose the first pair from the 7 people, $\binom{5}{2}=10$ ways to choose the second pair from the 5 remaining people, and $\binom{3}{2}=3$ ways to choose the third pair from the 3 remaining people, so there are $21 \cdot 10 \cdot 3$ ways to choose 3 pairs in order. However, we don't care about the order of the pairs, so we must divide by 3! to correct for this. Therefore there are $21 \cdot 10 \cdot 3 / 3!=105$ ways to choose 3 pairs. The 7th, unpaired, person has 6 choices for whom to throw at, so this gives a total of $105 \cdot 6$ possibilities with 3 pairs.

Therefore, there are
$$\left(21 \cdot 6^{5}\right)-\left(105 \cdot 6^{3}\right)+(105 \cdot 6)=141,246$$

possible outcomes in which there is at least one pair throwing at each other.
Finally, the probability that this occurs is
$$\frac{\left(21 \cdot 6^{5}\right)-\left(105 \cdot 6^{3}\right)+(105 \cdot 6)}{6^{7}}=\frac{23541}{6^{6}}=\frac{7847}{15552} \approx 50.5 \% .$$

**Problem 3.22:** In how many ways can we arrange 5 A's, 7 B's, and $4$ C's into a 16-letter word, such that there are at least three 'CA' pairs occurring in the word (in order words, there are at least 3 occurrences of a 'C' immediately followed by an 'A')?

*Solution for Problem 3.22:* It is possible to solve this problem using casework, where the cases are:

Case 1: Words where all four C's are followed by an A. This is the number of arrangements of 4 (CA)'s, 1 A, and 7 B's, so there are $\binom{12}{4} \times 8=3960$ arrangements in this case.

Case 2: Words where 3 C's are followed by an A and the 4th C is followed by a B. This is the number of arrangements of 3 (CA)'s, 1 (CB), 2 A's, and 6 B's, so there are $\binom{12}{3} \times 9 \times\binom{ 8}{2}=55440$ arrangements in this case.

Case 3: Words where 3 C's are followed by an A and the 4th C is followed by a C. This is the number of arrangements of 1 (CCA), 2 (CA)'s, 2 A's and 7 B's, so there are $12 \times\binom{ 11}{2} \times\binom{ 9}{2}=23760$ arrangements in this case.

Case 4: Words where 3 C's are followed by an A and the 4th C appears at the end. This is the number of arrangements of 3 (CA)'s, 2 A's, and 7 B's, so there are $\binom{12}{3} \times\binom{ 9}{2}=7920$ arrangements in this case.

So there are a total of $3960+55440+23760+7920=91080$ arrangements.

But we can more simply solve this problem using PIE. If we count the number of arrangements of 3 (CA)'s, 1 C, 2 A's, and 7 B's, we see that there are $\binom{13}{3} \times 10 \times\binom{ 9}{2}=102960$ arrangements, but this counts every arrangement with 4 CA's 4 times. So we must subtract 3 times the number of arrangements with 4 CA's, which as we saw above is 3960. Hence there are $102960-3(3960)=91080$ arrangements.

Counting problems involving PIE sometimes appear in geometric settings:

**Problem 3.23:** In how many ways can we choose 4 vertices of a convex $n$-gon (where $n>4$) to form a convex quadrilateral, such that at least 1 side of the quadrilateral is a side of the $n$-gon?

*Solution for Problem 3.23:* We first count how many quadrilaterals have a particular side of the $n$-gon as one of its sides. Once we have a side of the $n$-gon, we need to choose 2 of the remaining $n-2$ vertices to complete the quadrilateral (we can't choose the two vertices that are the endpoints of our already existing side). So there are $\binom{n-2}{2}$ such quadrilaterals. Since there are $n$ sides of the $n$-gon that we could have started with, this gives us an initial count of $n\binom{n-2}{2}$.

This initial count, however, overcounts those quadrilaterals that have 2 or more of its sides as sides of the original $n$-gon, so we have to correct for this. There are essentially two cases to consider for quadrilaterals with 2 sides on the original $n$-gon: its 2 sides (on the original $n$-gon) are either consecutive or nonconsecutive.

We can pick two consecutive sides in $n$ ways. This gives 3 vertices of our quadrilateral. Then, we have to choose a fourth vertex, which we can do in $n-3$ ways. Thus there are a total of $n(n-3)$ quadrilaterals of this type.

Alternatively, we can pick two nonconsecutive sides: we have $n$ choices for the first side, then $n-3$ choices for the second non-adjacent side. We then divide by 2 since this counts every pair of non-adjacent sides twice, once in each order. Therefore we have $n(n-3) / 2$ pairs of non-adjacent sides. This gives us all 4 vertices of the quadrilateral, so there are no more choices to be made.

Thus, adding these two cases, we see that there are $n(n-3)+n(n-3) / 2=\frac{3}{2} n(n-3)$ such quadrilaterals. These quadrilaterals are counted twice in our original count, so we need to subtract them once.

Finally, any quadrilateral with 3 sides on the original $n$-gon must have all 3 of those sides adjacent (otherwise we use up too many vertices). There are $n$ of these quadrilaterals, since there are $n$ choices for the middle of the three adjacent sides on the $n$-gon. These quadrilaterals are counted 3 times in our original count (once for each side on the original $n$-gon), but are subtracted 3 times in our count of quadrilaterals with 2 sides on the $n$-gon (once for each pair of sides on the original $n$-gon). So we need to add these back once.

Thus the number of quadrilaterals is
$$n\binom{n-2}{2}-\frac{3}{2} n(n-3)+n=\frac{n(n-2)(n-3)-3 n(n-3)+2 n}{2}=\frac{n^{3}-8 n^{2}+17 n}{2} .$$

As a quick check, we can verify that this formula works for $n=5,6,7$, and 8. For $n \leq 7$, the answer is just $\binom{n}{4}$ (since any choice of 4 vertices will give a quadrilateral with at least one side on the original $n$-gon). The answer for $n=8$ is $\binom{8}{4}-2=68$, since the only way that we can choose 4 vertices on an octagon that will give a quadrilateral with no sides on the octagon is if we choose every other vertex, and there's only 2 ways we can do that. Checking our formula, we see that it gives 5 when $n=5$, 15 when $n=6$, 35 when $n=7$, and 68 when $n=8$, so we probably didn't make any obvious mistake.

> **Concept:** If it's possible to do a quick check of your answer to a complicated problem, it's usually a good idea to do so.

We'll conclude our study of PIE with a very difficult problem. Solving this problem requires a solid understanding of the principle behind PIE, and not just a "memorize a formula" knowledge of PIE.

The statement of the problem is deceptively simple.

**Problem 3.24:** I have a coat with area 5. The coat has 5 patches on it. Each patch has area at least 2.5. Prove that 2 patches exist with common area of at least 1. (Source: PSS)

*Solution for Problem 3.24:* It may not be immediately clear how to proceed. We can start by introducing some notation and listing facts that we know. Let's call the patches $P_{1}, P_{2}, P_{3}, P_{4}, P_{5}$, and let's use brackets to denote area (for example, $\left[P_{1}\right]$ is the area of patch $P_{1}$).

What do we know? What are we trying to prove?

> **Concept:** In proof problems, one way to start is by listing what you know and what you're trying to prove.

We know that $\left[P_{1}\right] \geq 2.5,\left[P_{2}\right] \geq 2.5$, etc. We also know that the coat has area 5. We're trying to prove that one of $\left[P_{1} \cap P_{2}\right],\left[P_{1} \cap P_{3}\right], \ldots,\left[P_{4} \cap P_{5}\right]$ is at least 1.

How do we relate all of these items?
We know that the area of the union of the patches is no bigger than the entire coat. Therefore $5 \geq\left[P_{1} \cup P_{2} \cup P_{3} \cup P_{4} \cup P_{5}\right]$.

Now it's starting to look like PIE! We can write the area of the union of the patches using PIE. Although we've only used PIE up to now to count discrete elements of sets, the concept works just as well for areas. (Just think of a region as the set consisting of all of the points in the region.)

To shorten what we have to write in what follows, let's introduce some notation for the terms in our PIE expression.
$$\begin{aligned}
A & =\text { sum of areas of patches } \\
& =\left[P_{1}\right]+\left[P_{2}\right]+\cdots+\left[P_{5}\right] \\
B & =\text { sum of areas of overlaps of } 2 \text { patches } \\
& =\left[P_{1} \cap P_{2}\right]+\left[P_{1} \cap P_{3}\right]+\cdots+\left[P_{4} \cap P_{5}\right] \\
C & =\text { sum of areas of overlaps of } 3 \text { patches } \\
& =\left[P_{1} \cap P_{2} \cap P_{3}\right]+\cdots+\left[P_{3} \cap P_{4} \cap P_{5}\right] \\
D & =\text { sum of areas of overlaps of } 4 \text { patches } \\
& =\left[P_{1} \cap P_{2} \cap P_{3} \cap P_{4}\right]+\cdots+\left[P_{2} \cap P_{3} \cap P_{4} \cap P_{5}\right] \\
E & =\text { sum of areas of overlaps of all patches }
\end{aligned}$$

Then, using PIE, we get that
$$\left[P_{1} \cup \cdots \cup P_{5}\right]=A-B+C-D+E,$$
so because the total area of the coat is 5, we have the inequality
$$5 \geq A-B+C-D+E .$$

We're trying to show that at least one pair of patches has common area at least 1. If all 10 pairs of patches were to have area less than 1, then when we sum them, we would get $B<10$. We would like to show that this cannot happen, so we'd like to prove that $B \geq 10$. (This is an example of the Pigeonhole Principle, which we'll cover in great detail in Chapter 5.)

So it makes sense to rewrite our inequality (3.7.1) in terms of $B$:
$$B \geq A+C-D+E-5 .$$

We also know that $A=\left[P_{1}\right]+\cdots+\left[P_{5}\right] \geq 5(2.5)=12.5$, since each patch has area at least 2.5. Therefore we can replace $A$ in (3.7.2) to get
$$B \geq 12.5+C-D+E-5=7.5+C-D+E .$$

This is good, but not good enough: we want to show that $B \geq 10$. But we seem to have used all the information that was provided to us, so what are we going to do?

PIE got us this far, so let's use it again! Let's work on $B$ directly by counting the area of the coat covered by at least two patches. We denote this area by $X$. Don't fall into this trap:

> **Bogus Solution:**
> $$X=B-C+D-E$$

No! As we saw in Section 3.6, PIE is not so simple when we're counting "at least 2" of something. We have to think about how many times each region gets counted. For example, $B$ counts the triple-overlap regions 3 times, so we have to subtract $C$ twice in order to get them counted once. Similarly, $B$ counts the quadruple-overlap regions $\binom{4}{2}=6$ times, but $-2C$ subtracts them $2(4)=8$ times, so we need to add them back three times to get them counted once. Finally, the five-way overlaps are counted $\binom{5}{2}-2\binom{5}{3}+3\binom{5}{4}=10-20+15=5$ times, so we need to subtract $4E$.

Therefore, we know by PIE that
$$X=B-2 C+3 D-4 E .$$

So what? We don't know anything about $X$, right?
Wrong! We know that $X \leq 5$ (since $X$ can't be bigger than the whole coat). This fact, although seemingly trivial, is very important! Thus we have
$$5 \geq B-2 C+3 D-4 E$$

We can use this to eliminate one of the variables in (3.7.3). Let's solve (3.7.5) for $C$:
$$C \geq \frac{1}{2}(B+3 D-4 E-5)$$
and plug this into (3.7.3):
$$\begin{aligned}
B & \geq 7.5+C-D+E \\
& \geq 7.5+\frac{1}{2}(B+3 D-4 E-5)-D+E \\
& =5+\frac{1}{2} B+\frac{1}{2} D-E
\end{aligned}$$
which simplifies to give
$$\frac{1}{2} B \geq 5+\frac{1}{2} D-E$$
or
$$B \geq 10+D-2 E$$

Remember, we wanted to prove that $B \geq 10$, so we're very close. All we need to show to finish the problem is that $D-2 E \geq 0$.

But this is yet another use of PIE! Note that $D$ counts the area in the overlap of all 5 patches five times, once for each subset of 4 patches. Therefore $D \geq 5 E$, which certainly means that $D \geq 2 E$, and hence $D-2 E \geq 0$.

Thus we've proven that $B \geq 10$, which is what we needed to show, so we're done!

### Exercises

**3.7.1** Six children are playing dodgeball. Each child has a ball. At the sound of the whistle, each child chooses another child at random to chase. What is the probability that there is at least one pair of children who are chasing each other?

**3.7.2** In the grid at right, we wish to go from corner $A$ to corner $B$, moving only up and to the right one unit at a time. How many such paths include an edge of the shaded square?

**3.7.3** Let $S$ be a set with six elements. Let $\mathcal{P}$ be the set of all subsets of $S$. Subsets $A$ and $B$ of $S$, not necessarily distinct, are chosen independently and at random from $\mathcal{P}$. Find the probability that $B$ is contained in at least one of $A$ or $S \backslash A$. (Recall that the set $S \backslash A$ is the set of all elements of $S$ that are not in A.) (Source: AIME) Hints: 129, 282

**3.7.4** $\star$ In how many ways can we choose 5 vertices of a convex $n$-gon (where $n>5$) to form a convex pentagon, such that at least 2 sides of the pentagon are sides of the $n$-gon? Hints: 225, 238

**3.7.5** $\star$ Prove that, in Problem 3.24, for all such coats on which no pair of patches overlaps an area of more than 1, no point on the coat is covered by more than 3 patches. Hints: 337, 219

## 3.8 Summary

The principle of inclusion and exclusion (or PIE) is used to count the number of items that are in the union of two or more sets. This can be thought of as counting items that have "at least one" of a number of properties.
- If $A$ and $B$ are two sets, then
$$\#(A \cup B)=\#(A)+\#(B)-\#(A \cap B) .$$

If $A, B$, and $C$ are three sets, then
$$\#(A \cup B \cup C)=\#(A)+\#(B)+\#(C)-\#(A \cap B)-\#(A \cap C)-\#(B \cap C)+\#(A \cap B \cap C) .$$

More generally, if $A_{1}, A_{2}, \ldots, A_{n}$ are sets, then
$$\begin{aligned}
\#\left(A_{1} \cup A_{2} \cup \cdots \cup A_{n}\right)= & \#\left(A_{1}\right)+\#\left(A_{2}\right)+\cdots+\#\left(A_{n}\right) \\
& -\left(\#\left(A_{1} \cap A_{2}\right)+\#\left(A_{1} \cap A_{3}\right)+\cdots+\#\left(A_{n-1} \cap A_{n}\right)\right) \\
& +\left(\#\left(A_{1} \cap A_{2} \cap A_{3}\right)+\cdots+\left(A_{n-2} \cap A_{n-1} \cap A_{n}\right)\right) \\
& -\left(\#\left(A_{1} \cap A_{2} \cap A_{3} \cap A_{4}\right)+\cdots\right) \\
& +\quad \vdots \\
& +(-1)^{n+1} \#\left(A_{1} \cap A_{2} \cap \cdots \cap A_{n}\right) .
\end{aligned}$$

- PIE can also be used whenever we have to count items that have "at least $k$" of a set of properties. Anytime we need to count the items that are in least $k$ sets from a collection of $n$ sets, there will be a PIE expression to calculate it.

Don't blindly apply PIE. Think carefully about how many times each element gets counted. Make sure that elements in exactly 1 set, exactly 2 sets, etc., are each counted once and only once.

Here are a couple of problem-solving concepts regarding PIE:

> **Concept:** Messy casework often means that it's simpler to use complementary counting and PIE.

> **Concept:** If a problem asks you to count how many items have "at least" one property, that's a good sign that you may want to use PIE. Similarly, if a problem asks you to count how many items have "none" of several properties, that may be a sign to use complementary counting with PIE.

> **Concept:** Don't memorize a "formula" for PIE. Instead, think about how many times each item is counted, and make sure that each item is counted once and only once.

We also saw one general good piece of advice when trying to do proofs:

> **Concept:** In proof problems, one way to start is by listing what you know and what you're trying to prove.

## Review Problems

**3.25** How many 4-letter words (consisting of any sequence of 4 letters, possibly repeated) start or end with a vowel? (For the purposes of this problem, consider A, E, I, O, and U to be vowels, and consider Y to be a consonant.)

**3.26** How many 3-digit numbers have two consecutive digits the same?

**3.27** Is it possible that among a group of 20 ninth-graders, 15 of them play lacrosse, 12 of them play soccer, and 6 of them play both? Why or why not?

**3.28** When I go to work, there's a $20 \%$ probability that I'll forget my office keys, and a $30 \%$ probability that I'll forget my wallet. If there's a $5 \%$ probability that I forget both, then what's the probability that I arrive at work with both my keys and my wallet?

**3.29** How many 4-letter "words" (any combination of 4 letters) have no two consecutive letters identical?
(a) Solve the problem using PIE.
(b) Solve the problem using constructive counting.
(c) Can you algebraically explain why your two answers from (a) and (b) are the same? (Of course we know that they must be the same, since they're just two different ways of counting the same thing, but can you explain it in terms of algebra?)

**3.30** Sam can only remember 10-digit numbers if the first four digits are either exactly the same as the next four digits of the number or the last four digits of the number. For example, Sam can remember 1234123456 and 3444533444, but not 3344443334. How many 10-digit numbers can Sam remember?

**3.31** My state uses a sequence of three letters followed by a sequence of three numbers as its standard license plate pattern (for example, GMQ829). Given that each three-letter three-digit arrangement is equally likely, find the probability that such a license plate will contain at least one palindrome (a three-letter arrangement or a three-digit arrangement that reads the same left-to-right as it does right-to-left). (Source: AIME)

**3.32** Let $\pi=\left(x_{1}, x_{2}, x_{3}, x_{4}, x_{5}, x_{6}, x_{7}\right)$ be a permutation of the numbers $(1,2,3,4,5,6,7)$ (recall that a permutation is a rearrangement of the numbers, in which each number appears exactly once). Find the number of such permutations $\pi$ in which $x_{n}=n$ for some odd integer $n$.

**3.33** Twenty five of King Arthur's knights are seated at their customary round table. Three of them are chosen-all choices being equally likely-and are sent off to slay a troublesome dragon. Find the probability that at least two of the three had been sitting next to each other. (Source: AIME)

**3.34** What is the probability that a 13-card bridge hand (dealt at random from a standard 52-card deck) has a void (meaning it has no cards of some suit)?

**3.35** How many 5-digit sequences have a digit that appears at least 3 times? (For instance, 03005 and 22922 are examples of such sequences.)

## Challenge Problems

**3.36** Consider two events $A$ and $B$. Find $P(A$ or $B$ ) in terms of $P(A), P(B)$, and $P(A$ and $B$ ). Hints: 275

**3.37** There are $N$ students at Grant High School. Let $S(F)$ be the number of students at Grant who speak French, $S(J)$ be the number of students who speak Japanese, and $S(A)$ be the number who speak Arabic. Let $S(AF)$ be the number who speak both French and Arabic; define $S(AJ)$ and $S(FJ)$ similarly. Prove that $3 N+S(AF)+S(AJ)+S(FJ) \geq 2 S(A)+2 S(F)+2 S(J)$. Hints: 167

**3.38** Given any set $S$, let $s(S)$ be the number of subsets of $S$ (including $S$ and the empty set). If $X, Y$, and $Z$ are sets such that $s(X)+s(Y)+s(Z)=s(X \cup Y \cup Z)$ and $\#(X)=\#(Y)=100$, what is the minimum possible value of $\#(X \cap Y \cap Z)$ ? (Source: AMC) Hints: 193, 98

**3.39**
(a) Prove that for any positive integer $k$ less than 9,
$$9^{k}-\binom{9}{1} 8^{k}+\binom{9}{2} 7^{k}-\cdots-\binom{9}{7} 2^{k}+\binom{9}{8}=0$$
(b) What happens if $k=9$ ?

Hints: 19, 209, 233

**3.40** Find the number of positive integers that are divisors of at least one of $10^{10}, 15^{7}$, and $18^{11}$. (Source: AIME) Hints: 138

**3.41** There are $n$ chairs at a table, each with a name card with the name of one of $n$ people (with one name card for each person). The $n$ people sit at the table. Let $D_{n}$ be the number of ways the $n$ people can sit at the table such that not a single person is sitting in the correct seat. ($D_{n}$ is called the number of derangements of an $n$-member set.)
(a) Use the Principle of Inclusion-Exclusion to find an expression for $D_{n}$.
(b) Find a counting argument to show that $\sum_{k=0}^{n}\binom{n}{k} D_{n-k}=n!$.

**3.42** In a five-team tournament, each team plays one game with every other team. Each team has a $50 \%$ chance of winning any game it plays. (There are no ties.) Find the probability that the tournament will produce neither an undefeated team nor a winless team. (Source: AIME) Hints: 320

**3.43** $\star$ The goal of this problem is to derive the function for the number of positive integers less than or equal to $n$ which do not have a factor besides 1 in common with $n$. Recall that this function is called the Euler phi function, denoted $\phi(n)$, and was discussed in the box on page 60.
(a) Let the prime factorization of $n$ be $n=p_{1}^{e_{1}} p_{2}^{e_{2}} \cdots p_{k}^{e_{k}}$. How many positive integers less than or equal to $n$ are divisible by $p_{1}$? By $p_{2}$? By $p_{i}$ for $1 \leq i \leq k$?
(b) What's wrong with just subtracting all the numbers we find in (a) from $n$ to get $\phi(n)$ (the number of positive integers less than or equal to $n$ that have no factor besides 1 in common with $n$)?
(c) How can we use PIE to correct for our error in part (b)?
(d) After writing an expression for $\phi(n)$ using PIE, compare your expression to the expansion of the product
$$n\left(1-\frac{1}{p_{1}}\right)\left(1-\frac{1}{p_{2}}\right) \cdots\left(1-\frac{1}{p_{k}}\right)$$

What can you conclude?

**3.44** $\star$ Define a regular $n$-pointed star to be the union of $n$ line segments $P_{1} P_{2}, P_{2} P_{3}, \ldots, P_{n} P_{1}$ such that:
- the points $P_{1}, P_{2}, \ldots, P_{n}$ are coplanar and no three of them are collinear,
- each of the $n$ line segments intersects at least one of the other line segments at a point other than an endpoint,
- all of the angles at $P_{1}, P_{2}, \ldots, P_{n}$ are congruent,
- all of the $n$ line segments $P_{1} P_{2}, P_{2} P_{3}, \ldots, P_{n} P_{1}$ are congruent, and
- the path $P_{1} P_{2}, P_{2} P_{3}, \ldots, P_{n} P_{1}$ turns counterclockwise at an angle of less than 180 degrees at each vertex.

There are no regular 3-pointed, 4-pointed, or 6-pointed stars. All regular 5-pointed stars are similar, but there are two non-similar regular 7-pointed stars. How many non-similar regular 1000-pointed stars are there? (Source: AIME) Hints: 95, 169
