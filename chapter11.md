# Chapter 11: Conditional Probability

*"The thing about science fiction is that it's totally wide open. But it's wide open in a conditional way."* -- Octavia Butler

## 11.1 Introduction

As the name suggests, conditional probability is probability with some added restriction. For many of these problems, we can use our usual method of computing probability:
$$P(\text { event })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }} .$$

The main difference with conditional probability is that the number of "possible" outcomes is usually restricted by some condition. Like many concepts in this book, it's really not as confusing as it sounds.

However, it is true that some conditional probability problems produce results that may seem rather counterintuitive. We'll see several examples of this, including a famous problem that sparked a lot of controversy in the mathematical community.

## 11.2 Basic Examples of Conditional Probability

### Problems

**Problem 11.1:** A fair 6-sided die is rolled. If we know that the result is even, then what is the probability that we rolled a:
(a) In how many ways can we roll an even number?
(b) In how many ways can we roll a E?
(c) What is the desired probability?

Therefore, we see that if the contestant switches, he has a probability $\frac{1}{3}+\frac{1}{3}=\frac{2}{3}$ of winning, and probability $\frac{1}{6}+\frac{1}{6}=\frac{1}{3}$ of losing.

> **Sidenote:** The controversy surrounding the publication of the Monty Hall problem in the popular Sunday newspaper supplement Parade was detailed in a July 21, 1991 front-page story in The New York Times.

**Problem 11.10:** You and two other prisoners are in jail. Tomorrow, two of you will be sentenced to life in prison, but the third will be set free; any one of the three of you is equally likely to be the one set free. The jailer is sitting just outside the bars. You ask the jailer if you are the one to be set free.
(a) The jailer says he knows who will be let free, but he won't tell you if you are the one to be freed. He does, however, point at one of the other two and tells you that that person will not be released. What is the probability that you will be set free?
(b) The jailer says that he can't give out that information, but he does have the names of the two to be sentenced to life written on two scraps of paper in his pocket. When the jailer turns away from you, you're able to sneak a hand through the bars and snatch one piece of paper out of his pocket. It doesn't have your name on it. What is the probability that you will be set free?
(c) Your probability of being freed is different in these two cases. Why?

*Solution for Problem 11.10:* We first note that before the jailer responds, the probability that you will be set free is $\frac{1}{3}$, since you are told that the three prisoners are all equally likely to be freed.
(a) The jailer, unfortunately, is not giving you any additional information. You already knew that one of your two cellmates was going to be sentenced to life. So your probability of being freed is still $\frac{1}{3}$.
(b) You will be set free if and only if your name is not in the jailer's pocket. If your name was in his pocket, which occurs with probability $\frac{2}{3}$, then you would draw somebody else's name with probability $\frac{1}{2}$. If your name was not in his pocket, which occurs with probability $\frac{1}{3}$, then you would draw somebody else's name with probability 1. Therefore, the probability of drawing someone else's name is
$$\frac{2}{3} \cdot \frac{1}{2}+\frac{1}{3} \cdot 1=\frac{2}{3}$$

Hence, the probability that you will be freed (which is the same as the probability that your name is not in the jailer's pocket), given that you drew someone else's name, is
$$\frac{P(\text { you're freed and you draw another name })}{P(\text { you draw another name })}=\frac{\frac{1}{3}}{\frac{3}{3}}=\frac{1}{2} .$$
(c) Why the difference? It's subtle. In part (a), you got no information: whether you were going to be freed or not, the jailer can still give you someone else's name. But in part (b), when you reached into the jailer's pocket, there was always a chance that you might have drawn your own name. But you didn't, and that's information that you can use.

## 11.5 Exercises

**11.5.1** Suppose there are 10 curtains with 1 car and 9 goats. After the initial selection, the host reveals 8 of the goats. What's the probability of winning if the contestant switches?

**11.5.2$\star$** Suppose there are 4 curtains with 1 car and 3 goats. The host reveals one goat and gives the contestant the opportunity to switch. Then the host reveals a second goat and again gives the contestant the opportunity to switch. What's the best strategy, and what's the probability of winning the car if it is followed? **Hints:** 7

## 11.6 Summary

- Conditional probability is the probability of an event occurring, subject to some extra additional condition.
- If all events are equally likely, it's just
$$P(\text { event })=\frac{\text { Number of successful outcomes }}{\text { Number of possible outcomes }} .$$

The only difference is that all of the outcomes must satisfy the condition.
- More formally, if $A$ is the outcome and $B$ is the condition, then the probability of $A$ given that $B$ occurs, denoted $P(A \mid B)$, is:
$$P(A \mid B)=\frac{P(A \cap B)}{P(B)} .$$
- Conditional probability problems sometimes lead to counterintuitive answers, so check your work carefully! Make sure that you properly identify what is the condition and what is the successful outcome.

Here are some general problem-solving concepts:

> **Concept:** Checking the extreme cases is often an easy way to do a quick check of a formula.

> **Concept:** Don't just blindly jump into calculations until you've first determined what it is you need to calculate.

## Review Problems

**Problem 11.11:** An integer is randomly chosen from 1 to 20, inclusive. Given that the number is prime, what is the probability it is even?

**Problem 11.12:** Bag $A$ has three white and two black marbles. Bag $B$ has four white and three black marbles. A marble is taken at random from Bag A and placed in Bag B. A marble is then taken at random from Bag B. Given that the marble taken from Bag B is white, what is the probability that the marble taken from Bag $A$ was white?

**Problem 11.13:** A jar has 499 fair pennies and one penny with heads on both sides. A penny is chosen from the jar at random and flipped 9 times. It comes up heads every time. What is the probability that the coin is the two-headed coin?

**Problem 11.14:** On average, one in five Martians is a compulsive liar, and the rest always tell the truth. It rains $30 \%$ of the time on Mars. If three randomly-chosen Martians tell Astronaut Sue that it is raining, then what is the probability that it is actually raining? (Source: Mandelbrot)

**Problem 11.15:** A point on a circular table of radius 5 cm is chosen, and a quarter (of radius 1 cm) is placed on the table with its center at the chosen point. If no part of the quarter hangs over the edge of the table, then what is the probability that part of the quarter overlaps the center of the table?

**Problem 11.16:** Louise has a $75 \%$ probability of attending the annual Mathematical Association of America (MAA) convention. Thelma has an $80 \%$ chance of attending if Louise also attends; otherwise she has a $50 \%$ chance of attending. If I go to the convention and see Themla there, then what is the probability that Louise is also there? (Source: Mandelbrot)

## Challenge Problems

**Problem 11.17:** The Royals and the Cubs play in the World Series while you fly to the moon and back. You find out when you return that the series lasted 6 games. You know that the Royals had a $\frac{2}{3}$ probability of winning each game. What is the probability that the Royals won the World Series? (Note that the World Series is a series of games played between two teams until one team has won 4 games.) **Hints:** 205

**Problem 11.18:** Roger and Stacy each go to the county fair on the same day. They each separately show up at a random time between 12:00 and 6:00. Roger stays for an hour, whereas Stacy stays for 2 hours. If we know that at some time they were both at the fair simultaneously, what is the probability that they were both there at exactly 3:00? **Hints:** 254

**Problem 11.19:** A coin is flipped 20 times in a row. Given that exactly 14 heads appeared, find the probability that no two consecutive coin flips were both tails. **Hints:** 64, 85

**Problem 11.20$\star$** At the Lucky Losers' Casino, the craps game is played with a set of 5 dice. The pit boss notices one of the customers cheating by replacing one of the dice with a loaded die that rolls with probability $\frac{1}{2}$ (each of the other numbers on the loaded die show up with equal probability). Unfortunately, the boss can't tell which die is the loaded die (they all look identical), so he chooses one at random and rolls it 10 times. How many $\$$ s would he have to roll in order to be at least $90 \%$ sure that the chosen die is the loaded die? **Hints:** 257

**Problem 11.21$\star$** 3 points $A, B, C$ are randomly chosen on the circumference of a circle. If $A, B, C$ all lie on a semicircle, then what is the probability that all of the angles of triangle ABC are less than $120^{\circ}$ ? **Hints:** 192
