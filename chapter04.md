# Chapter 4: Constructive Counting and 1-1 Correspondences

*I've learned that something constructive comes from every defeat.* -- Tom Landry

## 4.1 Introduction

You may recall the concept of **constructive counting** from the book *Introduction to Counting & Probability*. The basic idea is that in order to count the number of items in a certain set, we think about how we would construct an item belonging to that set. During the construction, we keep track of the number of choices that we have at each step. Although this sounds simple, it is a very powerful way to count! In fact, many of the counting problems that we've solved up to now have essentially used this idea.

This chapter consists of constructive counting problems: we're trying to count the number of elements of some set, and we do so by thinking about how we can construct the elements of the set. We've seen lots of problems of this type before, especially in the *Introduction to Counting & Probability* book, but the problems in this section will generally be harder than the ones you've seen before.

We'll also introduce a new tool that's closely related to constructive counting, called a **1-1 correspondence** (read as "one-to-one correspondence"). Here's the basic idea: we want to count the items in some set $A$. For whatever reason, set $A$ is hard to count. But suppose that we can find another set $B$ such that:

- $B$ has the same number of elements as $A$, and
- $B$ is easy to count.

Then to count $A$, all we have to do is count $B$, and we have our answer! Simple as that!

A "1-1 correspondence" is the tool that we use to do the first part of the above: finding a set $B$ that has the same number of elements as $A$. We do this by showing that every element in $A$ somehow "matches" a corresponding element in $B$, and vice versa. Since the elements of $A$ and $B$ come in matching pairs, we know that the sets have the same number of elements.

We can think of using a 1-1 correspondence as a more general version of one of our basic problem-solving strategies: if we don't know how to solve a problem, try to find a simpler, related problem that we do know how to solve. That's really what a 1-1 correspondence allows us to do: if we have a set that's hard to count, try to find a related set that's easy to count, and count the easy set instead! As you might expect, the tricky part is finding the "easy" set and showing that it's the same size as the "hard" set.

## 4.2 Some Basic Problems

<div class="problems"></div>

**Problem 4.1:** How many license plates consist of 1 number followed by 3 letters followed by 3 numbers?

**Problem 4.2:** How many 5-digit palindromes are there? (A **palindrome** is a number that reads the same way forwards and backwards. For example, 27872 and 48484 are palindromes, but 28389 and 12541 are not.)

**Problem 4.3:** How many 7-digit numbers have no two adjacent digits equal?

**Problem 4.4:** Four points are chosen at random from the grid at right. What is the probability that the four points are the vertices of a rectangle whose sides are parallel to the sides of the grid?

---

The general idea with constructive counting is that we build (or "construct") the items that we're trying to count, and while doing so, keep track of the number of choices that we have at each step in the construction.

The problems in this section are all relatively basic examples of constructive counting, and should be review for you if you've mastered the *Introduction to Counting & Probability* textbook.

**Problem 4.1:** How many license plates consist of 1 number followed by 3 letters followed by 3 numbers?

*Solution for Problem 4.1:* We have 10 choices for the first number, then 26 choices for each of the 3 letters, then 10 choices for each of the last three numbers, for a total of $10 \cdot 26^3 \cdot 10^3 = 10^4 \cdot 26^3 = 175{,}760{,}000$ possible license plates. $\square$

**Problem 4.2:** How many 5-digit palindromes are there? (A **palindrome** is a number that reads the same way forwards and backwards. For example, 27872 and 48484 are palindromes, but 28389 and 12541 are not.)

*Solution for Problem 4.2:* We construct the number from left-to-right. We have 9 choices for the first digit (since it can't be 0), then 10 choices for the second digit, then 10 choices for the third digit. But now we're out of choices -- the fourth digit must match the second, and the last digit must match the first. Therefore, there are $9 \cdot 10 \cdot 10 = 900$ such numbers. $\square$

**Problem 4.3:** How many 7-digit numbers have no two adjacent digits equal?

*Solution for Problem 4.3:* As in Problem 4.2, we construct these numbers from left-to-right. We have 9 choices for the first digit (since it cannot be 0). Then, no matter what we choose for the first digit, we have 9 choices for the second digit -- any digit except the one that we chose for the first digit. Similarly, for each subsequent digit, we have 9 choices, since each digit can be any of 0 through 9 as long as it does not match the previous digit. Therefore, there are 9 choices for every digit, and hence there are $9^7 = 4{,}782{,}969$ such numbers. $\square$

**Problem 4.4:** Four points are chosen at random from the grid at right. What is the probability that the four points are the vertices of a rectangle whose sides are parallel to the sides of the grid?

*Solution for Problem 4.4:* There are $\binom{25}{4}$ ways in which we can choose 4 vertices (without regard to order). We need to determine how many of these sets of 4 vertices produce a valid rectangle. How can we construct such a rectangle? There are a couple of different ways we could proceed.

*Solution 1:* A rectangle whose sides are parallel to the sides of the grid is determined by its two opposite corners. There are $\binom{25}{2} = 300$ pairs of points in the grid, but there are two things we have to worry about. First, if we pick two points in the same row or same column, then we won't get a rectangle. There are 5 rows and 5 columns, and each has $\binom{5}{2} = 10$ pairs of points, so we have to subtract $10(10) = 100$ from our count, leaving $300 - 100 = 200$ pairs of points left. Second, each rectangle has two pairs of opposite corners, so we've overcounted by a factor of 2, and hence our final count is $200/2 = 100$.

*Solution 2:* A rectangle whose sides are parallel to the sides of the grid can be determined by choosing two rows to form the horizontal sides and choosing two columns to form the vertical sides. We can choose two rows in $\binom{5}{2} = 10$ ways and choose two columns in $\binom{5}{2} = 10$ ways, so the number of rectangles is $(10)(10) = 100$.

Therefore, 100 of the $\binom{25}{4}$ sets of 4 vertices form valid rectangles, and hence our probability is $\frac{100}{\binom{25}{4}} = \frac{2}{253}$.

We could also constructively count the probability directly, without counting the number of rectangles. For this, we think about selecting the vertices in order, one at a time. The first vertex is arbitrarily chosen. For the second vertex, there are two exclusive possibilities:

*Case 1:* The second vertex is in the same row or column as the first vertex. This occurs with probability $\frac{8}{24} = \frac{1}{3}$. Then, in order to produce a valid rectangle, the third vertex must be on one of the lines containing one of the first two vertices and perpendicular to the line containing the first two vertices. There are 8 such points on these lines, and 23 points remaining to choose from, so the probability of choosing one is $\frac{8}{23}$. Finally, only one point of the 22 remaining will complete the rectangle, and the probability of choosing it is $\frac{1}{22}$.

*Case 2:* The second vertex is not in the same row or column as the first vertex. This occurs with probability $\frac{16}{24} = \frac{2}{3}$. These two points must be opposite corners of our rectangle, so the final two points that we choose must be the other two corners. They are chosen with probability $\frac{2}{23} \cdot \frac{1}{22}$.

Therefore, the probability of choosing the four corners of a valid rectangle is

$$\frac{1}{3} \cdot \frac{8}{23} \cdot \frac{1}{22} + \frac{2}{3} \cdot \frac{2}{23} \cdot \frac{1}{22} = \frac{8 + 4}{3 \cdot 23 \cdot 22} = \frac{12}{1518} = \frac{2}{253}.$$

$\square$

### Exercises

**4.2.1** A dot is marked at each vertex of a triangle $ABC$. Then 2, 3, and 7 more dots are marked on the sides $\overline{AB}$, $\overline{BC}$, and $\overline{CA}$, respectively. How many triangles have their vertices at these dots? *(Source: HMMT)*

**4.2.2** Consider the set $S = \{1, 2, 3, \ldots, 34\}$. How many ways are there to choose (without regard to order) three numbers from $S$ whose sum is divisible by 3? *(Source: ARML)*

**4.2.3** How many orderings of the letters in MISSISSIPPI read the same forwards as backwards?

**4.2.4** Nine tiles are numbered $1, 2, 3, \ldots, 9$. Each of three players randomly selects and keeps three of the tiles, and sums those three values. Find the probability that all three players obtain an odd sum. *(Source: AIME)* Hints: 131

**4.2.5**$\star$ Robert has 4 indistinguishable gold coins and 4 indistinguishable silver coins. Each coin has an engraving of a face on one side, but not on the other. He wants to stack the eight coins on a table into a single stack so that no two adjacent coins are face to face. Find the number of possible distinguishable arrangements of the 8 coins. *(Source: AIME)* Hints: 13

## 4.3 Harder Constructive Counting Problems

<div class="problems"></div>

**Problem 4.5:** We wish to compute the sum of all of the 5-digit palindromes.
(a) How many 5-digit palindromes are there?
(b) How many have '1' as the last digit? How many have '2' as the last digit? And so on?
(c) What is the units digit of the sum of all of the 5-digit palindromes?
(d) Can you extend your reasoning from parts (a)-(c) above to find the sum of all of the 5-digit palindromes?

**Problem 4.6:** In a special sort of lottery called *reverse keno*, a player may buy a ticket on which he selects 10 numbers from 1--100 (inclusive). Then, 10 of the numbers are drawn at random. The player wins if his ticket contains none of the numbers which are drawn.
(a) What is the probability that a ticket wins?
(b) Is it possible to carefully select numbers on 10 tickets so that I am guaranteed that one of them will win, regardless of what numbers are drawn?
(c) What if I have 12 tickets? Can I now guarantee that one of them will win?

**Problem 4.7:**
(a) How many 2-digit numbers have distinct digits and are multiples of 9?
(b) How many 10-digit numbers have all digits distinct and are multiples of 11111?
(c) What is the sum of the digits of any 10-digit number that has all its digits distinct? What can you conclude?
(d) Use an argument similar to part (a) and your conclusion from (c) to count the numbers. Don't forget that a number cannot start with 0.
*(Source: Russia)*

**Problem 4.8:** In the course of a day, star tennis player Martina Combinova receives 10 different tennis rackets from fans who want her to sign and return the rackets. At various points during the day, Martina takes a break from whatever she is doing to sign some of the rackets. Whenever she decides to sign a racket, she grabs the most recently arrived racket, takes a few strokes with it, then signs it and sends it back. During lunch, Martina's coach tells her that she has signed the 9th racket that arrived. Given that the order of the rackets' arrival is fixed, how many possible post-lunch racket signing sequences are there? *(Source: AIME)*

---

**Problem 4.5:** What is the sum of all of the 5-digit palindromes?

*Solution for Problem 4.5:* In Problem 4.2, we found that there are 900 of these numbers. But how does that help us sum them up?

One idea is to sum each digit separately. Since we constructed the digits one at a time, it makes sense to think that we might be able to sum them one at a time.

> **Concept:** If doing the entire problem at once seems too complicated to handle, try breaking it up into manageable parts.

Start with the first digit. We know that there are 9 choices, so each choice appears in $900/9 = 100$ numbers. Therefore, the first digits sum to $100(1 + 2 + 3 + \cdots + 9) = 4500$. Since the last digits match the first digits, they also sum to 4500.

Now on to the second digit. We know that there are 10 choices, so each choice appears in $900/10 = 90$ numbers. Therefore, the second digits sum to $90(0 + 1 + 2 + \cdots + 9) = 4050$. Similarly, since the third and fourth digits are constructed in the same way, they also sum to 4050.

Therefore, all of the numbers sum to

$$4500(10^4) + 4050(10^3) + 4050(10^2) + 4050(10^1) + 4500(1) = 4500(10001) + 4050(1110) = 49{,}500{,}000.$$

Another way we could approach this is to calculate the *average* 5-digit palindrome. Based on our construction, we know that the average first and last digit is 5 (the average of 1 through 9), and the average of each of the middle three digits is 4.5 (the average of 0 through 9). So the average number is

$$5(10^4) + 4.5(10^3) + 4.5(10^2) + 4.5(10^1) + 5(1) = 55000,$$

and hence, since there are 900 such numbers, the sum of all of them is $(900)(55000) = 49{,}500{,}000$. $\square$

> **Concept:** In order to determine the sum of a set of numbers, we can often use a two-step process:
> 1. Count the number of elements in the set.
> 2. Determine the average element of the set.
>
> Then, we multiply the answers from our two steps to get the sum of the elements in the set. Note that this is essentially what we do when we sum an arithmetic series, such as $1 + 2 + \cdots + n$. There are $n$ elements in the series, and the average is $\frac{n+1}{2}$, so the sum is $\frac{n(n+1)}{2}$.

Sometimes just figuring out if a construction exists or not is a big part of the problem.

**Problem 4.6:** In a special sort of lottery called *reverse keno*, a player may buy a ticket on which he selects 10 numbers from 1--100 (inclusive). Then, 10 of the numbers are drawn at random. The player wins if his ticket contains none of the numbers which are drawn.

**(a)** What is the probability that a ticket wins?

**(b)** Is it possible to carefully select numbers on 10 tickets so that I am guaranteed that one of them will win, regardless of what numbers are drawn?

**(c)** What if I have 12 tickets? Can I now guarantee that one of them will win?

*Solution for Problem 4.6:*

**(a)** There are $\binom{100}{10}$ equally likely possible drawings. To count the number of winning drawings, we think about how we would construct a drawing for which our ticket wins. Our ticket wins if the 10 numbers drawn are all among the 90 numbers that are not on the ticket. Thus, the probability of winning is

$$\frac{\binom{90}{10}}{\binom{100}{10}} = \frac{90 \times 89 \times \cdots \times 81}{100 \times 99 \times \cdots \times 91} \approx 33.05\%.$$

**(b)** We need to think about whether we can construct 10 tickets that guarantee a win for any possible drawing. We may find the opposite problem easier: whether, given any 10 tickets, we can construct a drawing that loses on all 10 tickets. In fact, since every drawing has 10 numbers, we might get very unlucky and have the first number drawn on ticket #1, the second number drawn on ticket #2, and so on, so that each ticket contains one of the 10 numbers drawn, and thus we would lose on all tickets. So it is not possible to guarantee a win using 10 tickets.

**(c)** Given our answer to part (b), there is some hope that we might be able to construct a way to pick numbers for 12 tickets so that every drawing must miss at least one of the tickets (since there are only 10 numbers in a drawing). We fail if there is some drawing that matches a number on all 12 tickets.

Our first observation is that if a drawing loses on all tickets, then there must be a drawn number that appears on more than one ticket, since there are only 10 numbers in the drawing but there are 12 tickets. So our first idea might be to try to make sure that no numbers appear on more than one ticket -- if we could guarantee this, then there's no way that any drawing could lose. However, we can't arrange this: we must choose a total of 120 numbers for our 12 tickets (10 numbers per ticket), but we only have 100 numbers to choose from. Therefore, some numbers must appear on more than 1 ticket.

What happens if any number appears on more than two tickets? Then we're in big trouble. For example, suppose that 72 appears on tickets #1, #2, and #3. If the drawing consists of 72 plus one number from each of the other nine tickets #4 through #12, then we lose on all 12 tickets. So if we hope to guarantee a win, we cannot put the same number on more than two tickets. But as we discussed above, we can't avoid duplicating numbers on different tickets. In fact, there must be at least 20 numbers that appear on two tickets.

This means that there must be some number (call it $x$) that appears on two different tickets. There are 9 other numbers on the first of these tickets, and also 9 other numbers on the second of these tickets. Note that these sets of 9 numbers might overlap, but even if these give us 18 different numbers, and each of them is a 2-ticket number, there's still at least one 2-ticket number left over (since there are at least 20 of them total and we've only accounted for at most $1 + 9 + 9 = 19$ of them). Therefore, there must be another number (call it $y$) that appears on two other tickets, different from the tickets containing $x$. But now we're doomed: if the drawing comes up $x$, $y$, and one number from each of the remaining 8 tickets, we lose.

So we cannot guarantee a win with 12 tickets. $\square$

As a hard challenge, see if you can figure out some system, using as few tickets as possible, that does guarantee at least one winning ticket regardless of the numbers drawn.

**Problem 4.7:**
**(a)** How many 2-digit numbers have distinct digits and are multiples of 9?
**(b)** How many 10-digit numbers have all digits distinct and are multiples of 11111?
*(Source: Russia)*

*Solution for Problem 4.7:* In both of these parts, we'll use the notation that an overbar indicates that we should treat each letter as a digit, and not as a product. For example, if $a = 6$ and $b = 3$, then $\overline{ab}$ is 63, and not 18 (the product of $a$ and $b$).

**(a)** Since all of the numbers are small, we could solve this part simply by listing them:

$$18, 27, 36, 45, 54, 63, 72, 81, 90,$$

so there are 9 such numbers. (Note that we didn't list 99, since it doesn't have distinct digits.)

We notice that our list has one number for each possible choice of first digit. That might make us wonder why, and if there's a more clever solution.

Suppose that $\overline{ab}$ is a 2-digit multiple of 9 and $a \neq b$. We know that $a + b$ must be a multiple of 9, so the only possibility is $a + b = 9$. (We can't have $a + b = 18$ since then we'd have to have $a = b = 9$, and that's not allowed.) Thus $b = 9 - a$. We conclude that for every choice of $a$ between 1 and 9 (inclusive), we get one valid number, by setting $b = 9 - a$. Therefore there are 9 numbers.

> **Sidenote:** If you aren't familiar with why $a + b$ must be a multiple of 9 in order for $\overline{ab}$ to be a multiple of 9, write
>
> $$\overline{ab} = 10a + b = 9a + (a + b).$$
>
> Clearly $9a$ is a multiple of 9, so for the whole expression to be a multiple of 9, $(a + b)$ must be a multiple of 9 as well.

**(b)** Since we are looking for 10-digit numbers with all digits different, we know that each digit 0 through 9 must be used exactly once. Surely that must help somehow.

We can use the same observation that we used in part (a), which is that a number is a multiple of 9 if and only if the sum of its digits is a multiple of 9. If our digits are 0 through 9, their sum is $0 + 1 + \cdots + 9 = 45$, which is a multiple of 9. So, every 10-digit number with all different digits is a multiple of 9, and since 9 and 11111 are relatively prime, we may conclude that every 10-digit multiple of 11111 with all different digits is a multiple of $99999$. How can we use this observation?

Note that $99999 = 100000 - 1$. If we write a 10-digit number $n$ as $n = \overline{uv}$, where $u$ and $v$ are each 5-digit numbers, then

$$n = \overline{uv} = 100000u + v = 99999u + (u + v).$$

So $n$ is a multiple of 99999 if and only if $u + v$ is. This means that $u + v = 99999$, since that's the only multiple of 99999 that could possibly be the sum of $u + v$.

Note that the digits come in pairs that sum to 9: the units digit of $u$ and the units digit of $v$ must sum to 9, the tens digits of $u$ and $v$ must sum to 9, and so on. Also, there are 5 pairs of digits that sum to 9: 0 and 9, 1 and 8, 2 and 7, 3 and 6, and 4 and 5.

We have to allocate the five pairs of digits that sum to 9 to the five positions in $u$ and $v$. This can be done in $5!$ ways. We also have to choose which digit in each pair goes to $u$ and which goes to $v$, so this is 2 choices for each pair.

This might lead you to finish the problem by concluding:

> **Bogus Solution:** Hence, the answer is $5!(2^5) = (120)(32) = 3840$.

The problem is that a 10-digit number can't begin with 0. Since in our count above, any digit is equally likely to end up in any position, 1/10 of the numbers that we constructed above start with 0. That's not allowed. So only 9/10 of the numbers we constructed are actually allowed, hence our final answer is $(9/10)(5!)(2^5) = (9/10)(3840) = 3456$. $\square$

The last problem in this section is tough. Remember that your first rule of problem solving should be to read the problem carefully!

**Problem 4.8:** In the course of a day, star tennis player Martina Combinova receives 10 different tennis rackets from fans who want her to sign and return the rackets. At various points during the day, Martina takes a break from whatever she is doing to sign some of the rackets. Whenever she decides to sign a racket, she grabs the most recently arrived racket, takes a few strokes with it, then signs it and sends it back. During lunch, Martina's coach tells her that she has signed the 9th racket that arrived. Given that the order of the rackets' arrival is fixed, how many possible post-lunch racket signing sequences are there? *(Source: AIME)*

*Solution for Problem 4.8:* Before diving into the solution, it's important to understand what's going on here. Rackets #1 through #10 arrive at various points of the day. Whenever she signs one, Martina signs the most recently-arrived racket.

Here's an example:

- Rackets #1, #2, and #3 arrive
- Martina signs #3
- Rackets #4, #5, #6, #7 arrive
- Martina signs #7 and #6
- Racket #8 arrives
- Martina signs #8
- Rackets #9 and #10 arrive
- Martina signs #10, #9, and #5
- Lunch!
- Martina signs #4, #2, and #1.

The post-lunch signing order in this example is: #4, #2, #1. The question is: how many different post-lunch orderings are possible?

> **Concept:** Before diving into a problem, make sure that you:
> - Read the problem carefully.
> - Understand what the problem is asking.
> - If necessary, work through an example to get a feel for the problem.

We start by listing what we know and what we don't know. We know that #9 has already arrived and been signed. This means that #1 through #8 have already arrived, but we don't know which of them (if any) have already been signed. We also don't know if #10 has arrived yet, or if it has been signed.

So there are 9 rackets left that could potentially be signed after lunch. Rackets #1 through #8, if remaining to be signed, must be signed in descending order (the opposite order in which they arrived). On the other hand, racket #10 might already have been signed, or might arrive any time, and thus could be signed at any time (or not at all).

Therefore, we are trying to count the number of lists containing none, some, or all of the numbers 1-8 and 10, where the numbers 1-8 must appear in descending order, but 10 can appear anywhere (or nowhere).

Constructing the ways that 1 through 8 can appear is relatively easy -- we only need to choose which of the numbers are in our list, since once we choose which numbers are in the list, they must be placed in descending order. For each of these possible lists of rackets 1-8, the 10 can appear at any point in the list, or not at all. However, the number of choices for where the 10 can appear is dependent on the number of elements already in the list. If there are $k$ numbers in the list before adding 10, the 10 can appear in any of the $k + 1$ "slots" between numbers (including the first and last slot), or may not appear at all, for $k + 2$ possibilities.

So we need to sum over the different possible lengths of the lists of numbers from 1 through 8 (before possibly adding the 10). There are $\binom{8}{k}$ ways to list $k$ numbers out of 1-8, and $k + 2$ ways to include 10 in the list (or leave it off).

Adding over the possible values of $k$, we see that the total number of possible orders is

$$2\binom{8}{0} + 3\binom{8}{1} + 4\binom{8}{2} + \cdots + 10\binom{8}{8} = \sum_{k=0}^{8}(k+2)\binom{8}{k}.$$

We could work this sum out by hand, but is there a more clever way?

In fact, there are two clever methods!

*Method 1:* We can pull $2\left(\binom{8}{0} + \binom{8}{1} + \cdots + \binom{8}{8}\right)$ out, so that our sum is

$$2\left(\binom{8}{0} + \cdots + \binom{8}{8}\right) + \left(0\binom{8}{0} + 1\binom{8}{1} + \cdots + 8\binom{8}{8}\right) = 512 + \left(0\binom{8}{0} + 1\binom{8}{1} + \cdots + 8\binom{8}{8}\right),$$

using the fact that $\binom{8}{0} + \cdots + \binom{8}{8} = 2^8 = 256$. Now we apply a bit of algebra:

$$k\binom{8}{k} = k \cdot \frac{8!}{k!(8-k)!} = \frac{8!}{(k-1)!(8-k)!} = 8 \cdot \frac{7!}{(k-1)!(7-k+1)!} = 8\binom{7}{k-1}.$$

Therefore, our sum is

$$512 + 8\left(\binom{7}{0} + \binom{7}{1} + \cdots + \binom{7}{7}\right) = 512 + 8(128) = 1536.$$

*Method 2:* Let

$$S = 2\binom{8}{0} + 3\binom{8}{1} + 4\binom{8}{2} + \cdots + 10\binom{8}{8}.$$

Use the identity $\binom{8}{k} = \binom{8}{8-k}$ to rewrite $S$ as

$$S = 2\binom{8}{8} + 3\binom{8}{7} + 4\binom{8}{6} + \cdots + 10\binom{8}{0}.$$

Add these two expressions for $S$ together to get

$$2S = 12\left(\binom{8}{0} + \binom{8}{1} + \cdots + \binom{8}{8}\right) = 12 \cdot 2^8 = 12(256),$$

and divide by 2 to get $S = 6(256) = 1536$. $\square$

> **Sidenote:** The rackets in Problem 4.8 behave like a structure called a **stack**. A stack is characterized by the property that the last item that arrives is the first item that is processed (in this case, the "processing" is the signing of the racket). This is also sometimes called a **FILO** structure (FILO stands for "First In, Last Out") or a **LIFO** structure ("Last In, First Out"), and is used extensively in computer programming.

### Exercises

**4.3.1** Suppose that palindromes with $n$ digits are formed using only the digits 1 and 2 and that each palindrome contains at least one of each digit. Compute the least value of $n$ such that the number of palindromes formed exceeds 2002. *(Source: ARML)* Hints: 218

**4.3.2** We wish to color the integers 1, 2, 3, ..., 10 in red, green, and blue, so that no two numbers $a$ and $b$, with $a - b$ odd, have the same color. (We do not require that all three colors be used.) In how many ways can this be done? *(Source: HMMT)* Hints: 75

**4.3.3** Let $S = \{1, 2, 3, \ldots, 24, 25\}$. Compute the number of elements in the largest subset of $S$ such that no two elements in the subset differ by the square of an integer. *(Source: ARML)*

**4.3.4** How many pairs of positive integers $(m, n)$ are there such that the least common multiple of $m$ and $n$ is 21,600?

**4.3.5** An $n$-digit positive integer is **cute** if its $n$ digits are an arrangement of the set $\{1, 2, \ldots, n\}$ and its first $k$ digits form an integer that is divisible by $k$, for $k = 1, 2, \ldots, n$. For example, 321 is a cute 3-digit integer because 1 divides 3, 2 divides 32, and 3 divides 321. How many cute 6-digit numbers are there? *(Source: AMC)*

**4.3.6**$\star$ A classroom consists of a $5 \times 5$ array of desks, to be filled by anywhere from 0 to 25 students, inclusive. No student will sit at a desk unless either all other desks in its row or all others in its column are filled (or both). Considering only the set of desks that are occupied (and not which student sits at each desk), how many possible arrangements are there? *(Source: HMMT)* Hints: 190

> **Extra!** *The greatest real thrill that life offers is to create, to construct, to develop something useful.*
> -- Alfred P. Sloan

## 4.4 1-1 Correspondence Basics

Informally, we say that two finite sets $A$ and $B$ are in **1-1 correspondence** if they have the same number of elements; that is, if $\#(A) = \#(B)$. But this begs the question -- how do we tell if $A$ and $B$ have the same number of elements?

We do so by matching up the elements of $A$ and $B$, such that for every element of $A$ there is a **corresponding** element of $B$, and for every element of $B$ there is a **corresponding** element of $A$. In other words, the elements of $A$ and $B$ come in matching pairs, one element of $A$ matching with one element of $B$.

Here's a more formal definition:

> **Definition:** We say that the sets $A$ and $B$ are in **1-1 correspondence** if there exists a function $f$, mapping elements of $A$ to elements of $B$, that satisfies both of the following properties:
> (a) $f$ is **one-to-one** or **1-1**: if $f(x) = f(y)$, then $x = y$. (This also goes by the fancier name **injective**.)
> (b) $f$ is **onto**: for every $b \in B$, there exists $a \in A$ such that $f(a) = b$. (This also goes by the fancier name **surjective**.)
>
> The function $f$ is also sometimes called a **bijection**.

Think about what the two parts of the above definition mean. Part (a) means that no two distinct elements of $A$ can correspond to the same element of $B$. Part (b) means that every element of $B$ has to match to some element of $A$. When we put these together, we see that every element of $A$ matches to exactly one element of $B$, and no elements of $B$ get "skipped" in this matching.

> **Concept:** Don't worry about the terminology. The main thing to keep in mind is that a 1-1 correspondence between $A$ and $B$ has to pair up elements of $A$ with elements of $B$, such that every element of $A$ matches up with exactly one element of $B$, and every element of $B$ matches up with exactly one element of $A$. Hence the name "1-1 correspondence."

Sometimes we write $a \leftrightarrow f(a)$ to describe the 1-1 correspondence, meaning that element $a$ in set $A$ matches with element $f(a)$ in set $B$.

> **Sidenote:** **1-1 correspondences between infinite sets**
> Our formal definition above works just as well for infinite sets as for finite sets. However, we don't "count" infinite sets, so if sets $A$ and $B$ are in 1-1 correspondence, it doesn't necessarily mean that they have the "same number" of elements. For one thing, $\#(A)$ is undefined if $A$ is an infinite set. But even weirder things can happen. For example, can we show that the sets $\{1, 2, 3, \ldots\}$ and $\{0, 1, 2, 3, \ldots\}$ are in 1-1 correspondence? Certainly: take an element in the first set and subtract 1 to get an element in the second set. This satisfies our definition. Yet, somehow the first set seems "smaller" than the second one. More about this on page 98.

<div class="problems"></div>

**Problem 4.9:** Which of the following pairs of sets are in 1-1 correspondence?
(a) Integers from 1-10 (inclusive) and integers from 23-32 (inclusive).
(b) Integers from 1-10 (inclusive) and integers from 1-100 (inclusive) that are perfect squares.
(c) Integers from 1-10 (inclusive) and unordered pairs of integers from 1-5 (inclusive).
(d) Integers from 1-10 (inclusive) and even integers from $(-10)$-10 (inclusive).
(e) 2-digit positive integers in base 10 and 2-digit positive integers in base 8.

**Problem 4.10:** Show that the 7-step paths from $A$ to $B$ in the grid below are in 1-1 correspondence with arrangements of the letters RRRRUUU.

**Problem 4.11:** How many 4-letter words can we form such that each word has 4 different letters in increasing alphabetical order (such as FHMR)?

---

In the most basic examples, showing that two sets are in 1-1 correspondence is just a matter of finding a way to match every element in the first set to exactly one element in the second set, and vice versa.

**Problem 4.9:** Which of the following pairs of sets are in 1-1 correspondence?
(a) Integers from 1-10 (inclusive) and integers from 23-32 (inclusive).
(b) Integers from 1-10 (inclusive) and integers from 1-100 (inclusive) that are perfect squares.
(c) Integers from 1-10 (inclusive) and unordered pairs of integers from 1-5 (inclusive).
(d) Integers from 1-10 (inclusive) and even integers from $(-10)$-10 (inclusive).
(e) 2-digit positive integers in base 10 and 2-digit positive integers in base 8.

*Solution for Problem 4.9:*

**(a)** The elements match up $1 \leftrightarrow 23$, $2 \leftrightarrow 24$, etc., up through $10 \leftrightarrow 32$; in general, $x \leftrightarrow 22 + x$. This matches up each element of 1-10 (inclusive) with exactly one element of 23-32 (inclusive), and vice versa. So the sets are in 1-1 correspondence.

**(b)** The 1-1 correspondence is $x \leftrightarrow x^2$, which can also be written as $\sqrt{y} \leftrightarrow y$.

**(c)** We can list the unordered pairs from 1-5, and match them with integers 1-10, as follows:

$$1 \leftrightarrow \{1,2\} \quad 2 \leftrightarrow \{1,3\} \quad 3 \leftrightarrow \{1,4\} \quad 4 \leftrightarrow \{1,5\} \quad 5 \leftrightarrow \{2,3\}$$
$$6 \leftrightarrow \{2,4\} \quad 7 \leftrightarrow \{2,5\} \quad 8 \leftrightarrow \{3,4\} \quad 9 \leftrightarrow \{3,5\} \quad 10 \leftrightarrow \{4,5\}$$

There are, of course, many other ways that you could have matched up the sets. It doesn't matter that there's no "formula" for the matching: as long as we can match each element of one set with exactly one element of the other set, and vice versa, we have a 1-1 correspondence.

**(d)** These sets are not in 1-1 correspondence. There are 10 integers from 1-10 (inclusive), but 11 even integers from $(-10)$-10 (inclusive), so no matter how we try to match them, there will always be one integer in the second set "left over."

**(e)** This is also not a 1-1 correspondence. There are $9 \cdot 10 = 90$ integers of the form $\overline{ab}_{10}$ but only $7 \cdot 8 = 56$ integers of the form $\overline{ab}_8$. So if we try to match up the 90 integers in base 10 with the 56 integers in base 8, we'll quickly run out of base 8 integers to use.

$\square$

Notice in Problem 4.9 that all of our examples that were in 1-1 correspondence with the integers 1-10 (inclusive) had 10 elements. In part (a), there are 10 integers between 23 and 32 (inclusive); in part (b), there are 10 perfect squares between 1 and 100 (inclusive); in part (c), there are $\binom{5}{2} = 10$ unordered pairs of integers between 1 and 5 (inclusive). This is the basic feature of 1-1 correspondence.

> **Concept:** Two finite sets can be placed in 1-1 correspondence if and only if they have the same number of elements.

1-1 correspondences are sometimes used to relate two different ways of representing the same information, as in the next example:

**Problem 4.10:** Show that the 7-step paths from $A$ to $B$ in the grid below are in 1-1 correspondence with arrangements of the letters RRRRUUU.

*Solution for Problem 4.10:* In order to travel in 7 steps from $A$ to $B$, we must take 4 steps to the right and 3 steps up. Each different arrangement of these 7 steps will give a different path. So, given a path, we can write it as a 7-step sequence of R's and U's, where the letter R corresponds to a step to the right, and the letter U corresponds to a step up. For example, see Figure 4.1 below:

**Figure 4.1:** Path corresponding to RRURUUR

Conversely, every sequence of 4 R's and 3 U's corresponds to a unique path with 4 right steps and 3 up steps. Therefore the two sets are in 1-1 correspondence. $\square$

The point of Problem 4.10 is that while we may not necessarily know how to count paths, we certainly know how to count sequences of 4 R's and 3 U's: there are $\binom{7}{3} = 35$ of them. Therefore, there are 35 paths from $A$ to $B$.

Generally, in counting problems, we use a 1-1 correspondence to replace a difficult-to-count set with a set that's easier to count. The next problem shows a basic example of this.

**Problem 4.11:** How many 4-letter words can we form such that each word has 4 different letters in increasing alphabetical order (such as FHMR)?

*Solution for Problem 4.11:* Directly counting 4-letter words whose letters are in alphabetical order (for example, using constructive counting) leads to extremely nasty casework. For example, if the word starts with A, then there are 25 choices for the second letter; if this second letter is B, then there are 24 choices for the third letter; however if this second letter is C, then there are only 23 choices for the third letter. Furthermore, if the word starts with B, then there are only 24 choices for the second letter... the casework would go on like this seemingly forever!

Fortunately, we can create a nice 1-1 correspondence between the set

$$A = \{\text{4-letter words whose letters are all different and in alphabetical order}\}$$

and the set

$$B = \{\text{(unordered) sets of 4 distinct letters}\}.$$

The correspondence is simple: given a 4-letter word in $A$, we simply use the letters in the word as our element of $B$. To go the other way, given any four distinct letters in $B$, we just list them in alphabetical order to get a word in $A$. Every word in $A$ corresponds uniquely to a set of 4 letters in $B$, and every set of 4 letters in $B$ gives us a unique word in $A$.

So $A$ and $B$ are in 1-1 correspondence, and therefore $\#(A) = \#(B)$. But $B$ is easy to count -- it's just $\binom{26}{4} = 14{,}950$. Hence there are 14,950 elements of $A$. $\square$

Obviously, the examples in this section were pretty easy, and included nothing that you didn't already know how to count. In the next couple of sections, we'll do some more complicated examples.

### Exercises

**4.4.1** Which of the following pairs of sets are in 1-1 correspondence? If the pair is in 1-1 correspondence, show the correspondence.
(a) $\{1, 2, 3, \ldots, 12\}$ and $\{66, 68, 70, \ldots, 88\}$
(b) $\{3, 6, 9, \ldots, 60\}$ and $\{4, 9, 14, \ldots, 104\}$
(c) $\{0, 1, \ldots, 15\}$ and $\mathcal{P}(\{1, 2, 3, 4\})$
(d) $\{$ways to choose 2 items from a group of 5, where order does not matter$\}$ and $\{$ways to choose 1 item from a group of 10$\}$
(e) $\{$3-digit numbers with no 2$\}$ and $\{$3-digit numbers with no 4$\}$
(f) $\{$2-digit numbers with no 5$\}$ and $\{$2-digit numbers with no 0$\}$

**4.4.2** How many 3-letter "words" have their middle letter later in the alphabet than both of the other two letters? (For instance, CYJ and FKF are examples of such words, but RPB and WWL are not.)

**4.4.3** Compute the number of distinct paths not passing through point $(2, 2, 2)$ that travel from point $(0, 0, 0)$ to point $(4, 4, 4)$ in 12 steps, changing a coordinate by 1 at each step. *(Source: ARML)*

**4.4.4** If $A$ is in 1-1 correspondence with $B$, and $B$ is in 1-1 correspondence with $C$, show that $A$ is in 1-1 correspondence with $C$.

**4.4.5** Can a finite set $A$ be in 1-1 correspondence with a proper subset $B \subset A$? (Recall that a subset $B \subset A$ is **proper** if $B \neq A$.)

**4.4.6**$\star$

(a) Show that the odd divisors of 42 are in 1-1 correspondence with the even divisors of 42.
(b) Show that the odd divisors of 28 are *not* in 1-1 correspondence with the even divisors of 28.
(c) For what positive integers $n$ are the odd divisors of $n$ in 1-1 correspondence with the even divisors of $n$? Hints: 224, 183

> **Sidenote:** **More about 1-1 correspondences and infinite sets**
> As we saw on page 94, some strange things can happen when we look at 1-1 correspondences between infinite sets. In particular, Exercise 4.4.5 above is not necessarily true if the set $A$ is infinite; for example, the sets $\{0, 1, 2, 3, \ldots\}$ and $\{1, 2, 3, \ldots\}$ are in 1-1 correspondence even though the latter is a proper subset of the former. Any infinite set that is in 1-1 correspondence with the set of positive integers is called **countable**. However, not every infinite set is countable. It turns out that $\mathbb{Q}$ (the set of rational numbers) is countable but that $\mathbb{R}$ (the set of real numbers) is uncountable.
>
> More about this on page 104.

## 4.5 More Complicated 1-1 Correspondences

<div class="problems"></div>

**Problem 4.12:** What is the maximum number of intersection points of diagonals inside a convex $n$-gon? For example, the picture at right shows a pentagon with 5 such intersection points circled.
(a) Compute this by hand for $n = 3, 4, 5, 6, 7$ by drawing a picture and carefully counting the diagonal points.
(b) Do you see a pattern in the numbers that you found in part (a)?
(c) Use your answer to (b) to find an appropriate 1-1 correspondence, and finish the problem.

**Problem 4.13:** Let $n = 2^{12}3^{8}5^{6}$. How many divisors of $n^2$ are less than $n$?
(a) Try the question for small values of $n$, such as $n = 4$, $n = 5$, and $n = 6$. Do you notice anything interesting?
(b) What other set is in 1-1 correspondence with divisors of $n^2$ less than $n$?
(c) Finish the problem.

**Problem 4.14:** Let $k$ be an odd number. Show that there are fewer odd divisors of $4k$ than even divisors of $4k$.

**Problem 4.15:** The tennis club has 100 members, and Stephanie is the president. Which is larger: the number of ways to choose a 10-person advisory committee (which does not contain Stephanie) to advise Stephanie on what new rackets to buy, or the number of 11-person committees (which may include Stephanie) to plan an upcoming tournament? *Note: you should be able to do this problem without a calculator!*

---

In the last section, the problems were pretty easy. In this section, things get a bit more difficult.

**Problem 4.12:** What is the maximum number of intersection points of diagonals inside a convex $n$-gon? For example, the picture at right shows a pentagon with 5 such intersection points circled.

*Solution for Problem 4.12:* For a problem like this, where we're trying to find a formula in terms of a positive integer $n$, it often helps to try some small values of $n$ and see if we discover a pattern.

> **Concept:** When stuck on a "find a general formula"-type problem, experiment with some small values, and look for a pattern.

We can draw pictures for some small polygons. You should be able to draw this for triangles, quadrilaterals, and pentagons yourself; Figure 4.2 below shows a hexagon with 15 intersection points and a heptagon with 35 intersection points.

**Figure 4.2:** Convex hexagon and heptagon with diagonals

From our examples, we have the following chart:

| $n$ | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|
| Points | 0 | 1 | 5 | 15 | 35 |

It's probably going to be pretty messy to draw an octagon! And maybe it's hard to see a pattern in the above numbers. But where do we often look for counting numbers? Pascal's Triangle, of course!

> **Concept:** Look inside Pascal's Triangle to find counting numbers.

So let's go ahead and draw Pascal's Triangle, and we'll highlight the numbers that we found:

$$1$$
$$1 \quad 1$$
$$1 \quad 2 \quad 1$$
$$1 \quad 3 \quad 3 \quad 1$$
$$1 \quad 4 \quad 6 \quad 4 \quad 1$$
$$1 \quad \boxed{5} \quad 10 \quad 10 \quad \boxed{5} \quad 1$$
$$1 \quad 6 \quad \boxed{15} \quad 20 \quad \boxed{15} \quad 6 \quad 1$$
$$1 \quad 7 \quad 21 \quad \boxed{35} \quad \boxed{35} \quad 21 \quad 7 \quad 1$$

Aha, now a clear pattern emerges! The boxed numbers on the left sides of each row are $\binom{5}{2}$, $\binom{6}{2}$, $\binom{7}{2}$, etc. But the (same) boxed numbers on the right side are even easier to write as binomial coefficients: $\binom{5}{4}$, $\binom{6}{4}$, $\binom{7}{4}$, etc. Now we can see pretty clearly that the answer looks like $\binom{n}{4}$. So now that we think we know what the answer is, how can we prove it?

We know one "obvious" set with $\binom{n}{4}$ elements: the possible choices of sets of 4 vertices out of the $n$ total vertices. Perhaps we can show that this set is in 1-1 correspondence with intersection points of diagonals inside the $n$-gon.

> **Concept:** When you suspect that a set that you're trying to count has the same number of elements as a set that's easy to count, look for a 1-1 correspondence between the set you have and the "easy" set.

In fact, we can find the 1-1 correspondence. Given any intersection point of diagonals, we can get 4 vertices by taking the two pairs of endpoints of the diagonals intersecting at that point. Conversely, any 4 vertices uniquely determine two intersecting diagonals, by looking at the (unique) convex quadrilateral with those 4 vertices. For example, Figure 4.3 below shows an intersection point (circled) and its corresponding 4 vertices (in bold):

**Figure 4.3:** Hexagon with intersection point and 4 vertices in correspondence

So we've established a 1-1 correspondence between

$$\{\text{intersection points of diagonals}\} \leftrightarrow \{\text{sets of 4 vertices}\},$$

and since it is easy to see that the latter set has $\binom{n}{4}$ elements, we can conclude that the former set does as well.

Note that we've glossed over one significant detail: what happens if more than 2 diagonals intersect at the same point? Then we don't have our 1-1 correspondence, but this means that the set on the left in our above correspondence is strictly smaller than the set on the right, so that the number of intersection points is strictly less than $\binom{n}{4}$.

Hence $\binom{n}{4}$ is the maximum number of intersection points of diagonals inside a convex $n$-gon. $\square$

**Problem 4.13:** Let $n = 2^{12}3^{8}5^{6}$. How many divisors of $n^2$ are less than $n$?

*Solution for Problem 4.13:* A logical place to start is to count the number of divisors of $n^2$. Notice that $n^2 = 2^{24}3^{16}5^{12}$. A divisor of $n^2$ is a number of the form $2^a 3^b 5^c$, where $a \le 24$, $b \le 16$, and $c \le 12$. Therefore, since $a$ can be anything from 0 to 24, and we have similar choices for $b$ and $c$, there are $25 \cdot 17 \cdot 13 = 5525$ factors of $n^2$ (including $n^2$ itself).

So what's wrong with the following?

> **Bogus Solution:** A factor is less than $n$ if and only if $a \le 12$, $b \le 8$, and $c \le 6$, and there are $13 \cdot 9 \cdot 7 = 819$ of these. This includes $n$ itself, so we must subtract 1, and we get a final answer of 818.

The problem is that there are a lot of divisors of $n^2$ that are less than $n$ but that are not themselves divisors of $n$. For example, $2^{13}$ is not a divisor of $n$, but it is a divisor of $n^2$, and it is a lot smaller than $n$. Deciding what choices of $a$, $b$, $c$ make $2^a 3^b 5^c < n$ is a quite difficult number theory problem.

There doesn't seem to be any obvious way to directly count what we want. So instead, we might look for a 1-1 correspondence, from our set of divisors of $n^2$ less than $n$ to some other set that we know how to count. Is there an "obvious" set that is in 1-1 correspondence to the set of divisors of $n^2$ less than $n$? Remember: a 1-1 correspondence is essentially a pairing between elements of two sets, so is there anything that we can pair a divisor of $n^2$ less than $n$ to?

> **Concept:** 1-1 correspondences are essentially pairings. So look for a set of things to pair elements of your set to.

Indeed, divisors of $n^2$ come in pairs: if $n^2 = xy$ for some integers $x$ and $y$, then either $x = y = n$, or $x < n$ and $y > n$, or $x > n$ and $y < n$. In particular, a divisor $x < n$ of $n^2$ is naturally paired with the divisor $\frac{n^2}{x} > n$.

Therefore, we have a 1-1 correspondence between the sets

$$\{\text{divisors of } n^2 \text{ less than } n\} \leftrightarrow \{\text{divisors of } n^2 \text{ greater than } n\}.$$

Since these sets are of equal size, and together they total $5525 - 1 = 5524$ elements (since they contain all of the divisors of $n^2$ except for $n$), we conclude that they each have $5524/2 = 2762$ elements. Hence the answer to our problem is 2762. $\square$

The last step of the previous problem indicates another important way in which we can use 1-1 correspondences.

> **Important:** If you can partition a finite set $A$ into two non-overlapping subsets $B$ and $C$ (meaning that $B \cup C = A$ and $B \cap C = \emptyset$), and you can find a 1-1 correspondence between $B$ and $C$, then $B$ and $C$ are each exactly one-half the size of $A$.

A slight variation of this is in the next problem.

**Problem 4.14:** Let $k$ be an odd number. Show that there are fewer odd divisors of $4k$ than even divisors of $4k$.

*Solution for Problem 4.14:* Let's try a simple example to get a feel for things. Suppose $k = 5$, so $4k = 20$. The odd divisors of 20 are 1 and 5. The even divisors of 20 are 2, 4, 10, and 20. Indeed, we see that there are only two odd divisors whereas there are four even divisors.

Let's look at another example. Suppose $k = 15$, so $4k = 60$. The odd divisors of 60 are 1, 3, 5, and 15. The even divisors of 60 are 2, 4, 6, 10, 12, 20, 30, and 60. We see that there are four odd divisors and eight even divisors.

A pattern seems to have emerged. In both examples, there are exactly twice as many even divisors as odd divisors. This might suggest trying to split the divisors of $4k$ into three groups, one of which is the odd divisors, and showing a "1-to-1-to-1" correspondence between the three groups. Then each group will be equal size, and the odd divisors will be exactly one-third of all the divisors, whereas the even divisors, which make up the other two groups, will be the other two-thirds of the divisors.

A little experimentation will indicate how we should form the three groups. We notice that every divisor of $4k$ contains either 0, 1, or 2 powers of 2 as a factor (since $4k = 2^2 \cdot k$, and $k$ is odd). So those are our three groups: odd divisors (which contain no power of 2), divisors that are multiples of 2 but not of 4 (which contain one power of 2), and divisors that are multiples of 4 (which contain two powers of 2).

Let's draw a chart for our initial two examples $k = 5$ and $k = 15$:

| | Divisors of $4k$ | |
|---|---|---|
| $k$ | Odd | Multiples of 2, not 4 | Multiples of 4 |
| 5 | 1, 5 | 2, 10 | 4, 20 |
| 15 | 1, 3, 5, 15 | 2, 6, 10, 30 | 4, 12, 20, 60 |

Now it's clear what the 1-to-1-to-1 correspondence is. If $m$ is an odd divisor of $4k$, then $2m$ is the corresponding divisor of $4k$ that's a multiple of 2 but not of 4, and $4m$ is the corresponding divisor of $4k$ that's a multiple of 4. And it's also clear that all of these correspondences are reversible: for example, if we have a divisor of $4k$ that's a multiple of 4, then we can divide it by 4 to get an odd divisor of $4k$.

Therefore, not only have we proven the original problem statement, we've in fact established something stronger: the odd divisors of $4k$ make up exactly one-third of the total number of divisors of $4k$. (If you know some number theory, try to prove this using number-theory techniques as well.) $\square$

In the next problem, we're trying to determine not that two sets are of equal size, but which of two sets is the larger. Although the next problem also has algebraic solutions, think about how we might use a correspondence to solve it.

**Problem 4.15:** The tennis club has 100 members, and Stephanie is the president. Which is larger: the number of ways to choose a 10-person advisory committee (which does not contain Stephanie) to advise Stephanie on what new rackets to buy, or the number of 11-person committees (which may include Stephanie) to plan an upcoming tournament?

*Solution for Problem 4.15:* Both of these sets are relatively easy to count. The racket-advisory committee needs 10 members from a set of 99, so there are $\binom{99}{10}$ ways to form the committee. The tournament-planning committee needs 11 members from a set of 100, so there are $\binom{100}{11}$ ways to form the committee. So which is larger, $\binom{99}{10}$ or $\binom{100}{11}$?

Since we know that Stephanie is never on the 10-person committee, we can always add her and get an 11-person committee. Similarly, given an 11-person committee with Stephanie on it, we can always remove her and get a 10-person committee without her. Therefore, we have a 1-1 correspondence

$$\{\text{10-person committees without Stephanie}\} \leftrightarrow \{11\text{-person committees with Stephanie}\}.$$

However, the number of 11-person committees with Stephanie is certainly less than the total number of 11-person committees (with no restriction on the membership). Therefore, the number of 11-person committees is larger than the number of 10-person committees without Stephanie.

As we mentioned earlier, there are algebraic solutions to this as well. We can use Pascal's identity in reverse:

$$\binom{100}{11} - \binom{99}{10} = \binom{99}{11} > 0.$$

or we can write out the definitions of the binomial coefficients:

$$\binom{100}{11} = \frac{100!}{11! \cdot 89!} = \frac{100}{11} \cdot \frac{99!}{10! \cdot 89!} = \frac{100}{11} \cdot \binom{99}{10} > \binom{99}{10}.$$

However, the 1-1 correspondence solution has the slight advantage that we perhaps see more clearly why the statement is true. $\square$

### Exercises

**4.5.1** Annie the Ant starts at the lattice point $(0,0)$ and each minute moves 1 space up or 1 space to the right (with equal probability). Benny the Beetle starts at $(5,7)$ and each minute moves 1 space down or 1 space to the left (with equal probability). What is the probability that they meet? *(Source: AMC)*

**4.5.2** Compute $\displaystyle\sum_{n_{60}=0}^{2} \sum_{n_{59}=0}^{n_{60}} \cdots \sum_{n_{2}=0}^{n_{3}} \sum_{n_{1}=0}^{n_{2}} \sum_{n_{0}=0}^{n_{1}} 1$. *(Source: HMMT)*

**4.5.3** I roll 101 fair 6-sided dice.
(a) What is the probability that an even number of them come up even?
(b) Find the smallest integer $s$ such that the probability that the sum is greater than $s$ is less than $\frac{1}{2}$.

**4.5.4**$\star$ Suppose $n$ points are selected on the circumference of a circle and all $\binom{n}{2}$ chords connecting a pair of these points are drawn. Given that no three chords pass through the same point inside the circle, find the number of triangles that are formed by portions of the chords inside the circle and do not have any of the $n$ points as vertices. Hints: 73

> **Sidenote:** **More about 1-1 correspondences between infinite sets**
> Given any set $S$, finite or infinite, we can show that $S$ is not in 1-1 correspondence with its power set $\mathcal{P}(S)$. The proof uses a very clever argument called the **Cantor diagonalization argument**, due to the German mathematician Georg Cantor.
>
> Suppose on the contrary that there is a map $f : S \to \mathcal{P}(S)$ establishing the 1-1 correspondence. Define the set
>
> $$A = \{s \in S \mid s \notin f(s)\}.$$
>
> In words, $A$ contains each element $s$ that is not contained in its corresponding subset $f(s)$ in $\mathcal{P}(S)$. The question then is: what element $a \in S$ corresponds to $A \in \mathcal{P}(S)$? In other words, what element $a \in S$ has $f(a) = A$?
>
> There must be such an element if $f$ gives a 1-1 correspondence. But this leads to a paradox: if $a \in A$, then by definition $a \notin f(a) = A$, and if $a \notin A = f(a)$, then again by definition $a \in A$.
>
> In other words, the set $\mathcal{P}(S)$ is always "bigger" than the set $S$, even if $S$ is infinite. We'll continue this discussion in Challenge Problem 4.47 on page 117.

## 4.6 Clever 1-1 Correspondences

<div class="problems"></div>

**Problem 4.16:** The game **Chomp** is played as follows: We start with a $5 \times 7$ array of cookies, as in the picture below. The players alternate turns, and on each turn, the player chooses any cookie remaining on the board and removes (or "chomps") that cookie along with all the cookies above and/or to the right of the selected cookie. For example, a possible first move is:

The cookie in the lower-left corner of the board is poison: the player who is forced to chomp it loses. We wish to determine how many positions of the board are possible in the game.
(a) In English, how can we describe a possible position of the game?
(b) How does your English description from (a) lead to a mathematical description that we can count?
(c) Count the number of possible positions.

> **Definition:** A **partition** of a positive integer $n$ is a decomposition of $n$ into a sum of positive integers (not necessarily distinct), where we don't care about the order of the integers in the sum.

For example, the partitions of 3 are 3, $1 + 2$, and $1 + 1 + 1$. Note that $1 + 2$ and $2 + 1$ are considered the same partition, since we don't care about the order of the integers in the sum.

**Problem 4.17:** List all of the partitions of 4, 5, and 6.

**Problem 4.18:** Prove that the number of partitions of an integer $n$ into 3 parts is equal to the number of partitions of the integer $2n$ into 3 parts, where each part is less than $n$.
(a) Try to prove it for $n = 3$, $n = 4$, $n = 5$, $n = 6$.
(b) Try to prove it for general $n$.

**Problem 4.19:**
(a) List the partitions of 8 into exactly 3 parts.
(b) List the partitions of 8 in which the largest term is 3.
(c) How many partitions are there in your lists from (a) and (b)?
(d) Prove the general result: the number of partitions of $n$ into exactly $r$ parts is equal to the number of partitions of $n$ in which the largest term is $r$.

**Problem 4.20:**
(a) Steve flips 1 coin and Marissa flips 2 coins. What is the probability that Marissa flips more heads than Steve does?
(b) Steve flips 2 coins and Marissa flips 3 coins. What is the probability that Marissa flips more heads than Steve does?
(c) Steve flips 499 coins and Marissa flips 500 coins. What is the probability that Marissa flips more heads than Steve does?

---

**Problem 4.16:** The game **Chomp** is played as follows: We start with a $5 \times 7$ array of cookies, as in the picture below. The players alternate turns, and on each turn, the player chooses any cookie remaining on the board and removes (or "chomps") that cookie along with all the cookies above and/or to the right of the selected cookie. For example, a possible first move is:

The cookie in the lower-left corner of the board is poison: the player who is forced to chomp it loses. How many possible positions of the board are possible in the game?

*Solution for Problem 4.16:* Constructive counting might get complicated, because the legal positions are a bit hard to describe. In particular, if we start to focus on possible *moves*, as opposed to possible *positions*, we get into really nasty casework, and we also have the problem that the same position can often be reached by a variety of different sequences of moves.

So not really knowing what else to do, let's focus on a particular legal position to try to get a handle on the problem.

> **Concept:** When unsure how to proceed, look at some examples and see if you can find a pattern.

For example, the following might be the position after each player has moved twice:

> **Extra!** *C is for cookie, that's good enough for me.* -- Cookie Monster

How can we describe such a position? What's the most "obvious" thing that we notice?

We definitely notice that the number of cookies in each row is nondecreasing as we go from top to bottom. More specifically, each row has at least as many cookies in it as the row immediately above.

This gives us our first 1-1 correspondence:

$$\{\text{Legal Chomp positions}\} \leftrightarrow \left\{\text{Arrangements in which the number of cookies in each row is nondecreasing from top to bottom}\right\}$$

Note that we haven't shown all the steps necessary to prove that this is a 1-1 correspondence, but by now you should be able to manage that on your own.

So fine, we have a 1-1 correspondence, but how do we count those arrangements?

Maybe it will help if we put the cookies in a grid, and include spaces for the cookies already chomped.

Hmmm...let's draw in the "border" of the cookies:

Aha! We see that the border of the cookies is a path from the top-left corner to the bottom-right corner, where the steps of the path are down or to the right. This is true for every arrangement of rows of cookies in nondecreasing numbers: as we move along a row, we're moving right, and as we go down from one row to the next, we're moving down. We know that we never have to move left or up since the rows are nondecreasing.

Therefore, we have the following 1-1 correspondences:

$$\{\text{Legal Chomp positions}\} \leftrightarrow \left\{\text{Arrangements in which the number of cookies in each row is nondecreasing from top to bottom}\right\}$$
$$\leftrightarrow \left\{\text{Paths from the top-left corner to the bottom-right corner of a } 5 \times 7 \text{ grid, where all the steps are down or to the right}\right\}$$

Fortunately, this last set is easy to count! We need to take 12 steps total, and must choose 5 of them to be down, so the number of paths is $\binom{12}{5} = 792$.

Thus there are 792 legal Chomp positions, including the start of the game (where all 35 cookies are present) and the end of the game (where all the cookies are gone and one player is poisoned). $\square$

> **Sidenote:** **So how do I win?**
> We've just counted the number of legal positions in a Chomp game on a $5 \times 7$ grid. But we didn't really discuss the game itself -- in particular, if both players play intelligently, which player has a winning strategy? Chomp is a very interesting game, in that it turns out that the first player always has a winning strategy (except on the trivial $1 \times 1$ board), but except for certain board sizes, nobody knows what that strategy is! We'll discuss this more in Chapter 13.

For the next few problems, we'll introduce the notion of a **partition**. This comes up quite often in counting and number theory problems.

> **Definition:** A **partition** of a positive integer $n$ is a decomposition of $n$ into a sum of positive integers (not necessarily distinct), where we don't care about the order of the integers in the sum.

For example, the partitions of 3 are 3, $2 + 1$, and $1 + 1 + 1$. Note that $1 + 2$ and $2 + 1$ are considered the same partition, since we don't care about the order of the integers in the sum.

**Problem 4.17:** List all of the partitions of 4, 5, and 6.

*Solution for Problem 4.17:* The partitions of 4 are 4, $3 + 1$, $2 + 2$, $2 + 1 + 1$, and $1 + 1 + 1 + 1$. There are 5 different partitions of 4.

The partitions of 5 are 5, $4 + 1$, $3 + 2$, $3 + 1 + 1$, $2 + 2 + 1$, $2 + 1 + 1 + 1$, and $1 + 1 + 1 + 1 + 1$. There are 7 different partitions of 5.

The partitions of 6 are 6, $5 + 1$, $4 + 2$, $4 + 1 + 1$, $3 + 3$, $3 + 2 + 1$, $3 + 1 + 1 + 1$, $2 + 2 + 2$, $2 + 2 + 1 + 1$, $2 + 1 + 1 + 1 + 1$, and $1 + 1 + 1 + 1 + 1 + 1$. There are 11 different partitions of 6. $\square$

Determining the number of partitions of an arbitrary positive integer $n$ is difficult, and there is no nice formula for this. However, there are many nice relations among partitions; the next two problems will give two examples.

**Problem 4.18:** Prove that the number of partitions of an integer $n$ into 3 parts is equal to the number of partitions of the integer $2n$ into 3 parts, where each part is less than $n$.

*Solution for Problem 4.18:* As we often do, to get a handle on this problem, let's look at a few small values of $n$ and see if we notice anything interesting.

> **Concept:** When trying to prove something for all positive integers $n$, first try a few small values of $n$ and see if you notice a pattern.

| $n$ | Partitions of $n$ into 3 parts | Partitions of $2n$ into 3 parts less than $n$ |
|---|---|---|
| 2 | None | None |
| 3 | $1 + 1 + 1$ | $2 + 2 + 2$ |
| 4 | $2 + 1 + 1$ | $3 + 3 + 2$ |
| 5 | $3 + 1 + 1$ | $4 + 4 + 2$ |
| | $2 + 2 + 1$ | $4 + 3 + 3$ |
| 6 | $4 + 1 + 1$ | $5 + 5 + 2$ |
| | $3 + 2 + 1$ | $5 + 4 + 3$ |
| | $2 + 2 + 2$ | $4 + 4 + 4$ |

Besides confirming that the result seems to be true -- there are the same number of partitions in each column -- do we notice anything?

Since we want to show that the two sets are equal, it makes sense to look for a 1-1 correspondence between them. So the question becomes: how does a partition of $n$ with 3 parts correspond to a partition of $2n$ with 3 parts all less than $n$?

Let's experiment with the $n = 6$ case. We'd like to exhibit a 1-1 correspondence:

$$\{4 + 1 + 1, 3 + 2 + 1, 2 + 2 + 2\} \leftrightarrow \{5 + 5 + 2, 5 + 4 + 3, 4 + 4 + 4\}$$

and do it in such a way that it generalizes for arbitrary $n$.

The observation that should jump out is that each set has one partition with three equal terms ($2 + 2 + 2$ and $4 + 4 + 4$), one partition with three distinct terms ($3 + 2 + 1$ and $5 + 4 + 3$), and one partition with two equal terms and a third different term ($4 + 1 + 1$ and $5 + 5 + 2$). It makes sense that these are going to end up as the pairs in our correspondence.

Further observation leads to the insight that the corresponding terms in our above pairs all add to $n$. This leads to our correspondence:

$$4 + 1 + 1 \quad \leftrightarrow \quad (6-4) + (6-1) + (6-1) = 2 + 5 + 5$$
$$3 + 2 + 1 \quad \leftrightarrow \quad (6-3) + (6-2) + (6-1) = 3 + 4 + 5$$
$$2 + 2 + 2 \quad \leftrightarrow \quad (6-2) + (6-2) + (6-2) = 4 + 4 + 4$$

So our general conjecture is that given a partition of $n$ with 3 parts, we can subtract each part from $n$ to get a partition of $2n$ with 3 parts all less than $n$, and vice versa. Now we have to prove it.

Suppose that $n = a + b + c$ is a partition of $n$. Then

$$(n - a) + (n - b) + (n - c) = 3n - (a + b + c) = 3n - n = 2n,$$

so $(n-a) + (n-b) + (n-c)$ is a partition of $2n$. Furthermore, since $a$, $b$, and $c$ are all positive integers strictly between 0 and $n$, so are $n - a$, $n - b$, and $n - c$. Therefore, each partition of $n$ with 3 parts corresponds to a partition of $2n$ with 3 parts, each less than $n$.

But we're not done! We need to show that the correspondence works in the other direction as well.

> **Important:** When proving a 1-1 correspondence, you need to demonstrate that the correspondence is indeed 1-1, meaning that it must be reversible. You need to be able to go back and forth between the two sets. If you only show one direction, you're not done yet.

Conversely, suppose that $2n = d + e + f$ is a partition of $2n$, with each of $d$, $e$, and $f$ less than $n$. Then

$$(n - d) + (n - e) + (n - f) = 3n - (d + e + f) = 3n - 2n = n,$$

so $(n - d) + (n - e) + (n - f)$ is a partition of $n$. Furthermore, since $d$, $e$, and $f$ are all positive integers strictly between 0 and $n$, so are $n - d$, $n - e$, and $n - f$. Therefore each partition of $2n$ with 3 parts all less than $n$ corresponds to a partition of $n$ with 3 parts.

Thus we have established a 1-1 correspondence between the sets

$$\{\text{Partitions of } n \text{ with 3 parts}\} \leftrightarrow \{\text{Partitions of } 2n \text{ with 3 parts all less than } n\},$$

and hence these sets have an equal number of elements. $\square$

**Problem 4.19:** Prove that the number of partitions of $n$ into exactly $r$ parts is equal to the number of partitions of $n$ in which the largest term is $r$, for all positive integers $1 \le r \le n$.

*Solution for Problem 4.19:* In this problem, it's a bit trickier to list examples, since we have to pick values for both $n$ and $r$; our goal is to pick one pair of values for $n$ and $r$ small enough so that they're easy to work with, but big enough so that any pattern (if it exists) will hopefully emerge.

Let's pick $n = 8$ and $r = 3$, and list the partitions in each set.

| Partitions of 8 into 3 parts | Partitions of 8 with largest term 3 |
|---|---|
| $6 + 1 + 1$ | $3 + 3 + 2$ |
| $5 + 2 + 1$ | $3 + 3 + 1 + 1$ |
| $4 + 3 + 1$ | $3 + 2 + 2 + 1$ |
| $4 + 2 + 2$ | $3 + 2 + 1 + 1 + 1$ |
| $3 + 3 + 2$ | $3 + 1 + 1 + 1 + 1 + 1$ |

It's a little more difficult to see a pattern here than it was in the last problem.

One pattern that you might notice is that list of the largest terms $(6, 5, 4, 4, 3)$ in each of the partitions in the left column matches the list of the number of terms $(3, 4, 4, 5, 6)$ in each of the partitions in the right column. This is sufficiently interesting that we might pick different values of $n$ and/or $r$ and see if this still holds. Let's try another example, with $n = 9$ and $r = 3$.

| Partitions of 9 into 3 parts | Partitions of 9 with largest term 3 |
|---|---|
| $7 + 1 + 1$ | $3 + 3 + 3$ |
| $6 + 2 + 1$ | $3 + 3 + 2 + 1$ |
| $5 + 3 + 1$ | $3 + 3 + 1 + 1 + 1$ |
| $5 + 2 + 2$ | $3 + 2 + 2 + 2$ |
| $4 + 4 + 1$ | $3 + 2 + 2 + 1 + 1$ |
| $4 + 3 + 2$ | $3 + 2 + 1 + 1 + 1 + 1$ |
| $3 + 3 + 3$ | $3 + 1 + 1 + 1 + 1 + 1 + 1$ |

It still works: the largest terms $(7,6,5,5,4,4,3)$ of the partitions in the left column match the number of terms in the partitions in the right column.

This gives us an important clue towards how to build our 1-1 correspondence. It's easiest to describe with an example, so let's show the correspondence between

$$5 + 3 + 1 \leftrightarrow 3 + 2 + 1 + 1 + 1.$$

Start with the 5 in the left partition, and write it as $1 + 1 + 1 + 1 + 1$. Now take the 3 and add 1 to each of the first 3 terms, giving $2 + 2 + 2 + 1 + 1$. Finally, take the 1 and add 1 to the first term, giving $3 + 2 + 2 + 1 + 1$.

To go the other way, start with $3 + 2 + 1 + 1 + 1$, and take the number of terms (5) as the first term in our new partition. Subtract 1 from each term: $2 + 1 + 0 + 0 + 0$. Remove the zeros, giving $2 + 1$, and take the number of remaining terms (2) as the next term. Wait -- that doesn't work for this example. Let's try yet again more carefully.

To go the other way, start with $3 + 2 + 2 + 1 + 1$, and take the number of terms (5) as the first term in our new partition. Subtract 1 from each term: $2 + 1 + 1$. Remove the zeros, and take the number of remaining terms (3) as the next term in our new partition. Subtract 1 again from each remaining term: $1$. Take the number of remaining terms (1) as the next term. Subtract 1 again: $0$. We're done. The numbers we've extracted along the way give us our new partition: $5 + 3 + 1$.

Let's run through this algorithm again, with a different choice of partition:

| Old | New | Old | New |
|---|---|---|---|
| Given: partition with 3 parts | | Given: partition with largest part 3 | |
| $4 + 3 + 2$ | | $3 + 3 + 2 + 1$ | |
| Start with 4 1's | $1 + 1 + 1 + 1$ | 4 terms; subtract 1 from each term | |
| | | $2 + 2 + 1$ | 4 |
| $3 + 2$ | | 3 terms; subtract 1 from each term | |
| Add 1 to first 3 terms | $2 + 2 + 2 + 1$ | $1 + 1$ | $4 + 3$ |
| | | 2 terms; subtract 1 from each term | |
| 2 | | | |
| Add 1 to first 2 terms | $3 + 3 + 2 + 1$ | | $4 + 3 + 2$ |

This is a bit wordy. Fortunately, we can more easily describe the correspondence using a tool called a **Ferrers diagram**.

> **Concept:** Often, we can better understand complicated concepts by using a suitable diagram.

We can represent a partition with $r$ parts as $r$ rows of dots, in which each row contains a number of dots equal to the number in the partition. Similarly, we can represent a partition whose largest element is $r$ as $r$ rows of dots, in which each column has a number of dots equal to a number in the partition.

$$4 \rightarrow \bullet \bullet \bullet \bullet$$
$$3 \rightarrow \bullet \bullet \bullet$$
$$2 \rightarrow \bullet \bullet$$
$$\quad\quad\quad 1 \quad 1 \quad 3$$
$$\quad\quad\quad 3 \quad 2$$

Thus, we have 1-1 correspondences

$$\{\text{Partitions of } n \text{ with } r \text{ parts}\} \xrightarrow{\text{Read as rows}} \{\text{Ferrers diagrams with } r \text{ rows}\} \xrightarrow{\text{Read as columns}} \left\{\text{Partitions of } n \text{ whose largest element is } r\right\}$$

Hence the numbers of partitions in each set are equal. $\square$

We will explore partitions further in Chapter 14.

**Problem 4.20:** Steve flips 499 coins and Marissa flips 500 coins. What is the probability that Marissa flips more heads than Steve does?

*Solution for Problem 4.20:* As usual, we can look at some small examples to try to get a feel for the problem.

If Steve has 1 coin and Marissa has 2 coins, then since there are 3 flips total, there are $2^3 = 8$ possible outcomes. We can easily list the outcomes in which Marissa "wins" by flipping more heads than Steve:

(T,HT), (T,TH), (T,HH), (H,HH)

In each pair, the first entry is Steve's flip and the second entry is Marissa's two flips. Since Marissa wins 4 out of 8 times, the probability of her winning is $\frac{4}{8} = \frac{1}{2}$.

If Steve has 2 coins and Marissa has 3 coins, there are now $2^5 = 32$ possible outcomes. We could try to list them all out, but instead we can do a bit of casework.

If Steve flips 0 heads (which he can do in 1 way), then Marissa wins as long as she avoids TTT. This gives her 7 ways to win.

If Steve flips 1 head (which he can do in 2 ways), then Marissa wins if she flips 2 or 3 heads, which she can do in 4 ways. This gives her 8 ways to win.

If Steve flips 2 heads (which he can do in 1 way), then Marissa must flip HHH to win. This gives her 1 way to win.

So Marissa has $7 + 8 + 1 = 16$ successful outcomes, and the probability of her winning is $\frac{16}{32} = \frac{1}{2}$.

This is probably not a coincidence, so we now conjecture that as long as Marissa has one more coin than Steve, her probability of winning is $\frac{1}{2}$. This suggests looking for a 1-1 correspondence between the winning outcomes and the non-winning outcomes. (This is similar to the method we used in Problem 4.13.)

The natural way to get a 1-1 correspondence between coin-flipping outcomes is to reverse the outcome of every coin flip (in other words, change every H to T and every T to H). This does indeed give a 1-1 correspondence between winning and non-winning outcomes, as follows: Suppose we have a winning outcome where Steve has $a$ heads and Marissa has $b$ heads, with $a < b$. When we reverse heads and tails, Steve now has $499 - a$ heads and Marissa has $500 - b$ heads. We would like to show that this is a non-winning outcome for Marissa, meaning that Steve has at least as many heads as Marissa does. We see this as follows:

$$499 - a \ge 500 - b \quad \Leftrightarrow \quad -a \ge 1 - b,$$
$$\Leftrightarrow \quad a \le b - 1,$$
$$\Leftrightarrow \quad a < b,$$

where the last equivalence follows since $a$ and $b$ are integers. This works the other way as well: if we start with an outcome in which Steve has at least as many heads as Marissa, and reverse all the heads and tails, then we have an outcome in which Marissa has more heads than Steve.

So winning and non-winning outcomes are in 1-1 correspondence, hence each make up half of the total outcomes, and Marissa has a $\frac{1}{2}$ chance of winning. $\square$

### Exercises

**4.6.1** Use an argument similar to that in Problem 4.16 to find the number of legal positions in a game of Chomp played on an $m \times n$ board, where $m$ and $n$ are positive integers.

**4.6.2** Show that the number of partitions of $n$ into parts of even size equals the number of partitions of $n$ into parts that occur an even number of times. Hints: 236

**4.6.3** A class of 10 students took a math test. Each problem was solved by exactly 7 of the students. If the first nine students each solved 4 problems, how many problems did the tenth student solve? *(Source: HMMT)* Hints: 76

**4.6.4**$\star$ In the diagram at right, the side length of the large equilateral triangle is 3. There are 15 parallelograms of various sizes that are formed by segments in the grid (one example is shown in bold). Find a formula for the number of parallelograms that are formed by an analogous triangular grid with side length $n$. *(Source: Canada)* Hints: 266, 338, 342

**4.6.5** Let $\lfloor x \rfloor$ denote the greatest integer less than or equal to $x$. (For example, $\lfloor 3 \rfloor = 3$ and $\lfloor 6.73 \rfloor = 6$.) Prove that for any positive integer $n$,

$$\left\lfloor \frac{n+1}{2} \right\rfloor + \left\lfloor \frac{n+2}{4} \right\rfloor + \left\lfloor \frac{n+4}{8} \right\rfloor + \left\lfloor \frac{n+8}{16} \right\rfloor + \cdots = n.$$

Hints: 283, 14

**4.6.6** Are there more partitions of 2006 into only even parts or into only odd parts?

**4.6.7**$\star$ Let $S$ be the set $\{1, 2, \ldots, n\}$. Let $k$ be the number of subsets $T$ of $S$ such that the elements of $T$ have an integer average. Prove that $n + k$ is even. *(Source: Putnam)* Hints: 112, 340

## 4.7 Summary

$\triangleright$ The basic idea of constructive counting is to think about how you would construct the items that you're trying to count, while keeping track of the number of possibilities at each stage of the construction.

$\triangleright$ Often, a big part of the problem is simply figuring out if a construction exists or not.

$\triangleright$ Whenever we can match every element in set $A$ to exactly one element in set $B$ and vice versa, we have a 1-1 correspondence.

$\triangleright$ Two finite sets can be placed into 1-1 correspondence if and only if they have the same number of elements.

$\triangleright$ We generally use 1-1 correspondences to count a hard-to-count set, by placing the set in 1-1 correspondence with an easy-to-count set, which then necessarily has the same number of elements as our original set.

$\triangleright$ To prove that two sets $A$ and $B$ are in 1-1 correspondence, we have to show that every element of $A$ corresponds to exactly one element of $B$, and that every element of $B$ corresponds to exactly one element of $A$. Showing the correspondence in only one direction is not sufficient.

$\triangleright$ When you suspect that a set that you're trying to count has the same number of elements as a set that's easy to count, look for a 1-1 correspondence between the set you have and the "easy" set.

$\triangleright$ A **partition** of a positive integer $n$ is a decomposition of $n$ into a sum of positive integers (not necessarily distinct), where we don't care about the order of the integers in the sum. Many problems involving partitions can be solved using Ferrers diagrams.

Here are some general problem-solving strategies that are applicable to constructive counting:

> **Concept:** If doing the entire problem at once seems too complicated to handle, try breaking it up into manageable parts.

> **Concept:** Sometimes, it's easier to think about how you would construct the items that you don't want to count, and subtract the count of these items from the total.

> **Concept:** When stuck on a "find a general formula"-type problem, experiment with some small values, and look for a pattern.

> **Concept:** Often, we can better understand complicated concepts by using a suitable diagram.

> **Concept:** Before diving into a problem, make sure that you:
> - Read the problem carefully.
> - Understand what the problem is asking.
> - If necessary, work through an example to get a feel for the problem.

## Review Problems

**4.21** For how many ordered triples $(a, b, c)$ of positive integers less than 10 is the product $abc$ divisible by $20$? *(Source: HMMT)*

**4.22** How many nonempty subsets of $\{1, 2, 3, \ldots, 12\}$ have the property that the sum of the largest element and the smallest element is 13? *(Source: HMMT)*

**4.23** Each face of a cube is painted either red or blue, each with probability $\frac{1}{2}$. The color of each face is determined independently. What is the probability that the painted cube can be placed on a horizontal surface so that the four vertical faces are all the same color? *(Source: AMC)*

**4.24** What is the probability that a randomly chosen divisor of $30^{39}$ is a multiple of $30^{29}$?

**4.25** Forty slips are placed into a hat, each bearing a number 1, 2, 3, 4, 5, 6, 7, 8, 9, or 10, with each number entered on four slips. Four slips are drawn from the hat at random without replacement. What is the probability that two of the slips bear a number $a$ and the other two bear a number $b \neq a$? *(Source: AMC)*

**4.26** A hotel packed a breakfast for each of three guests. Each breakfast should have consisted of three types of rolls, one each of nut, cheese, and fruit rolls. The preparer wrapped each of the nine rolls, and, once they were wrapped, the rolls were indistinguishable from one another. She then randomly put three rolls in a bag for each of the guests. Find the probability that each guest got one roll of each type. *(Source: AIME)*

**4.27** Suppose we have a $10 \times 10$ grid of points, such as the set of lattice points with both coordinates between 0 and 9 (inclusive). How many squares (with sides parallel to the sides of the grid) can be formed by connecting 4 of these points?

**4.28** Consider the sequence $1, 4, 5, 16, 17, 20, 21, 64, 65, \ldots$, which is formed by including only positive integers that can be expressed as the sum of distinct powers of 4. What is the $50^{\text{th}}$ term in this sequence?

**4.29** Show that, for any nonempty finite set $S$, the number of subsets of $S$ with an even number of elements is equal to the number of subsets of $S$ with an odd number of elements.

**4.30** Show that the number of partitions of an integer $n$ into at most $r$ parts is equal to the number of partitions of $n$ into parts of at most $r$.

**4.31** Let $f(n,k)$ denote the number of partitions of $n$ into $k$ parts. Prove that

$$f(n, k) = f(n - 1, k - 1) + f(n - k, k).$$

**4.32** On the Cartesian plane, Johnny wants to travel from $(0,0)$ to $(5,1)$, and he wants to pass through all twelve lattice points $(x, y)$ such that $0 \le x \le 5$ and $0 \le y \le 1$. On each step, Johnny can go from one point to any other point via the straight line segment connecting the two points. How many paths are there from $(0,0)$ to $(5,1)$, passing through all 12 points, such that the path never crosses itself? One such path is shown below. *(Source: HMMT)*

## Challenge Problems

**4.33** Eight knights are randomly placed on a chessboard (not necessarily on distinct squares). A knight on a given square attacks all the squares that can be reached by moving either (1) two squares up or down followed by one square left or right, or (2) two squares left or right followed by one square up or down. Find the probability that every square, occupied or not, is attacked by some knight. *(Source: HMMT)* Hints: 331

**4.34** A true-false test has 10 questions. Suppose that if you answer any five questions "true" and the remaining five questions "false," then your score is guaranteed to be at least four. How many answer keys are there for which this is true? *(Source: HMMT)* Hints: 34, 178

**4.35** In how many ways can 4 purple balls and 4 green balls be placed into a $4 \times 4$ grid such that every row and column contains one purple ball and one green ball? Only one ball may be placed in each box, and rotations and reflections of a single configuration are considered different. *(Source: HMMT)* Hints: 109, 198

**4.36** How many $4 \times 4$ matrices whose entries are each 1 or $-1$ are such that the sum of the entries in each row is 0 and the sum of the entries in each column is 0? *(Source: AIME)* Hints: 94, 24

**4.37** A lattice point is a point $(x, y)$ such that $x$ and $y$ are both integers. Suppose we color each of the lattice points within the square $0 \le x, y \le 10$ either black or white. Find the number of colorings in which each of the 100 unit squares (bounded by the colored lattice points) has exactly two white vertices. Hints: 107

**4.38** 10 points in the plane are given, with no 3 collinear. 4 distinct segments joining pairs of these points are chosen at random, all such segments being equally likely. Find the probability that some 3 of the segments form a triangle whose vertices are among the 10 given points. *(Source: AIME)*

**4.39** Consider the set $S = \{1, 2, 3, 4, 5, \ldots, 100\}$. How many subsets of this set with 2 or more elements satisfy:
(a) the terms of the subset form an arithmetic sequence, and
(b) we cannot include another element from $S$ with this subset to form an even longer arithmetic sequence?
Hints: 311, 47

**4.40** Define the *alternating sum* of a set of positive integers as follows: List the elements of the set in decreasing order. Take the first number in the list, subtract the second, add the third, subtract the fourth, and so on. For example, the alternating sum of the set $\{3, 5, 11, 7\}$ is $11 - 7 + 5 - 3 = 6$. Find the sum of the alternating sums of all of the subsets of $\{1, 2, 3, 4, 5, 6, 7, 8, 9, 10\}$. *(Source: AIME)* Hints: 133, 270

**4.41** In a classroom, 34 students are seated in 5 rows of 7 chairs. The place at the center of the room is unoccupied. A teacher decides to reassign the seats such that each student will occupy a chair adjacent to his/her present one (i.e. move one desk forward, back, left, or right). In how many ways can this assignment be made? *(Source: HMMT)* Hints: 187, 164

**4.42** In how many ways can we place a positive number of rooks on an $8 \times 8$ chessboard, such that no two lie in the same row or the same column, and so that none of the rooks lies to the left of and below another rook? *(Source: HMMT)* Hints: 325

**4.43** Eight congruent equilateral triangles, each of a different color, are used to construct a regular octahedron. How many distinguishable ways are there to construct the octahedron? (Two colored octahedrons are distinguishable if neither can be rotated to look just like the other.) *(Source: AMC)* Hints: 307, 181

**4.44**$\star$ Is there a 2000-element subset of the set $\{1, 2, 3, \ldots, 3000\}$ such that no element in the subset is exactly double another element of the subset? Hints: 113, 155

**4.45**$\star$ Find the number of ways to color each square of a $2007 \times 2007$ square grid either black or white such that each row and each column has an even number of black squares. *(Source: Mandelbrot)* Hints: 96, 151

**4.46**$\star$ Three numbers, $a_1, a_2, a_3$, are drawn randomly, without replacement, from the set $\{1, 2, 3, \ldots, 1000\}$. Three other numbers, $b_1, b_2, b_3$, are then drawn randomly, without replacement, from the remaining set of 997 numbers. What is the probability that, after suitable rotation, a brick of dimensions $a_1 \times a_2 \times a_3$ can be enclosed in a box of dimensions $b_1 \times b_2 \times b_3$, with the sides of the brick parallel to the sides of the box? *(Source: AIME)* Hints: 297, 300

**4.47** This problem continues our discussion (from page 104) of 1-1 correspondences between infinite sets. Recall that any infinite set that can be placed into 1-1 correspondence with the set of all positive integers is called **countable**, and any infinite set that cannot is called **uncountable**.

(a) Prove that $\mathbb{Z}$ (the set of all integers) is countable. Hints: 26
(b)$\star$ Prove that $\mathbb{Q}$ (the set of rational numbers) is countable. Hints: 223
(c)$\star$ Prove that $\mathbb{R}$ (the set of real numbers) is uncountable. (You may use the fact, discussed on page 104, that no set $S$ can be placed in 1-1 correspondence with its power set $\mathcal{P}(S)$.) Hints: 101, 144
