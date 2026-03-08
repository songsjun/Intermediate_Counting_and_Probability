# Chapter 2: Sets and Logic

*Logic is the beginning of wisdom, not the end. -Mr. Spock*

## 2.1 Introduction

In order to discuss some of the more advanced concepts in this book, we'll first need to discuss two very fundamental areas of mathematics: sets and logic.

Some of these concepts may be familiar to you, but you should nonetheless read through this chapter carefully-there may be some subtleties that you're not already familiar with. Also, you'll see that there are relatively few problems in the text in this chapter. The concepts in this chapter are tools that we use to describe and solve problems later in the book, but these tools don't necessarily give rise to many interesting problems in their own right.

The notation and terminology might seem a bit heavy in this chapter. Try not to worry too much about all the new notation and terminology, especially in the logic sections. It's much more important to try to keep the big picture in mind: sets and logic are tools that we use to formulate and solve more complicated ideas and problems. (Although, to be fair, set theory and the theory of formal logic are rich branches of mathematics in their own right, and many mathematicians have made careers studying them.) As you use sets and logic in more and more problems, the terminology will become more and more natural to you.

Also, because a lot of the exercises in this chapter depend on knowing the appropriate definitions and notation, we're not using our usual style of putting practice problems at the start of every section, because without knowing the terminology or notation, you wouldn't be able to make any headway. Instead, for this chapter only, we'll just be introducing problems as we go through the text. When you reach a problem in the text, try to solve it before reading the solution; then, whether you think you've solved it or not, carefully read the solution presented.

## 2.2 Sets

Sets are the building blocks of mathematics. Like many other extremely fundamental mathematical concepts (such as "point" or "number"), sets are difficult to precisely define, and we're not going to try to be precise here.

Roughly speaking, a set is a collection of objects. The objects can be essentially anything: number, functions, other sets, any combination of these, or nothing at all. The order of the objects in the set is unimportant. All that matters is what objects are in the set. There might only be a finite number of objects in the set (meaning basically that we could count them if we liked), in which case the set is called (big surprise) a finite set. Otherwise we call it an infinite set. The objects in the set are called the elements or members of the set.

There are two basic ways that we can describe a set. The first is to simply list its elements. For example:
$$A=\{2,9,22\} .$$

This is a set with three elements, namely 2,9 , and 22 . This is the most basic way to define or describe a set: We list the elements inside of curly braces, and separate the different elements by commas. As we said above, the order of the elements doesn't matter, so $A=\{9,22,2\}$ is exactly the same set as $A=\{2,9,22\}$. Also, each element can only be in the set once, so for example $B=\{3,6,3\}$ is not a legal set (or, alternatively, we can think of the second " 3 " in $\{3,6,3\}$ as being redundant and write $\{3,6,3\}=\{3,6\}$ ).

Sometimes it's impractical to list a big set, so we use ellipses if the pattern of the elements in the set is clear. For example, we feel pretty safe describing a set as $\{1,2,3, \ldots, 99,100\}$ and knowing that this is the set of the first 100 positive integers.

If a set is infinite, then we obviously have no hope of being able to list all the elements, since such a list would go on forever! But if it is clear which elements are in the set, then we can list the elements using ellipses. For example, the set of all positive integers can be written as $\{1,2,3, \ldots\}$, because the pattern is clear. As another example, we can be pretty sure that $\{1,2,4,8,16,32, \ldots\}$, without any further description, is the set of all nonnegative powers of 2 . Be careful though: you should only do this if your pattern is absolutely clear. Listing a set as $\{1,2,4, \ldots\}$ is pretty ambiguous: is it the set of all nonnegative powers of 2 , or the set of all positive integers not divisible by 3 , or something else that we didn't think of? It's not at all clear, so we need more sample elements to make the pattern clear, or some words describing the set, or we can define the set via the properties of its elements, as we're about to see.

Aside from listing the elements, the other basic way to describe a set is to provide a property that precisely defines the elements of the set. For example:
$$B=\{x \mid x \text { is an integer }\} .$$

In this example, the set $B$ consists of all the integers. Some people use colon (:) instead of the vertical bar (|); in either case, you should read the symbol as "such that." For example, we would read our set $B$ above as "the set of all $x$ such that $x$ is an integer." Another common example is an interval on the real line; for example,
$$\{x \mid x \text { is a real number and } 2<x \leq 3\}$$
is the interval of all real numbers that are greater than 2 and less than or equal to 3 . One of the major strengths of this way of describing a set is that we can use this even if we don't know explicitly what the elements are. For example,
$$\left\{y \mid y \text { is a real number and } 2 y^{4}-y^{3}+6 y^{2}-11 y+12=0\right\}$$
is perfectly valid, even if we don't necessarily know at first glance exactly what values of $y$ are in the set, or even if there are any elements in the set.

Most of the time, we will be using sets whose elements are numbers or other mathematical objects. However, a set can contain pretty much anything as elements, as long as the elements are precisely defined. For example, we could define a set
$$S=\{x \mid x \text { is a state in the United States }\} .$$

Then $S=\{$ Alabama, Alaska, ... $\}$. We can even "mix and match" different types of elements to our heart's content. For example,
$$T=\{5,\{2, \pi\}, \text { Boston }\}$$
is a set with three elements: a number ( 5 ), a set (with elements 2 and $\pi$ ), and a city (Boston). If an object $x$ is an element of $S$, we write this as $x \in S$. If $x$ is not an element of $S$, we write $x \notin S$. For any object $x$ and any set $S$, either $x \in S$ or $x \notin S$, but (of course) never both. Indeed, this is the whole point of sets: a set is a collection of the objects that belong to it, and everything else does not belong.

There is a very special set called the empty set, denoted by $\emptyset$. This is the set with no elements at all. For example,
$$\left\{x \mid x \text { is a real number and } x^{2}<0\right\}=\emptyset,$$
because there is no real number satisfying the property that its square is less than 0 . Note that $x \notin \emptyset$ for any $x$. We sometimes also write the empty set as a list: $\emptyset=\{ \}$. Of course, it's an empty list, since the empty set has no elements.

If $S$ is a finite set, then we let $\#(S)$ denote the number of elements of $S$. We say that $\#(S)$ is the cardinality of $S$. (Note that many sources use the notation $|S|$ in place of $\#(S)$.) For example, if $S=\{2,4,9,11\}$ then $\#(S)=4$, since $S$ has four elements. Note that $\#(\emptyset)=0$, since $\emptyset$ has zero elements. If $S$ is an infinite set (such as the set of all integers), then we cannot define $\#(S)$ without resorting to so-called transfinite cardinal numbers, which are beyond the scope of this book.

A set $A$ is called a subset of a set $B$ if every element of $A$ is also an element of $B$. We think of $A$ as a smaller set that is made up of some of the elements of $B$. More informally, we think of $A$ as sitting "inside" $B$. The notation that we use is $A \subseteq B$. For example,
$$\{3,8,11\} \subseteq\{2,3,8,10,11,14,16\}$$
and
$$\{x \mid x \text { is an even integer }\} \subseteq\{x \mid x \text { is an integer }\} .$$

If $A$ is a subset of $B$, we also say that $B$ is a superset of $A$.

Sometimes it is convenient to have a notation for when a set is a proper subset of another set, meaning that it is a subset but not equal to the larger set. For example, $\{1,2,3\}$ is a proper subset of $\{1,2,3,4\}$, but $\{1,2,3,4\}$ is not a proper subset of $\{1,2,3,4\}$, although it is a subset.

We use the notation $A \subset B$ to denote that $A$ is a proper subset of $B$. (This is very similar to the notations $<$ for "less than" and $\leq$ for "less than or equal to": $3<4$ and $3 \leq 4$ and $4 \leq 4$, but $4 \nless 4$.) Another way to think of this is that $A \subset B$ means that $A$ is a subset of $B$, but there is some element of $B$ that is not in $A$. For example, $\{1,2,3\} \subset\{1,2,3,4\}$ because 4 is not in $\{1,2,3\}$.

Let's practice with some basic exercises involving elements and subsets:

**Problem 2.1:** Consider the following sets:
$$A=\{1,2,3,4,5\}, \quad B=\{2,3,4\}, \quad C=\{3,\{4,5\}\} .$$
(a) Is $A \subseteq A$ ? Is $A \subset A$ ?
(b) Is $B \subseteq A$ ? Is $B \subset A$ ?
(c) Is $C \subseteq A$ ? Is $C \subset A$ ?
(d) Is $4 \in B$ ? Is $4 \in C$ ?
(e) List all of the subsets of $B$. How many are there?

*Solution for Problem 2.1:*
(a) The elements of $A$ are $1,2,3,4$, and 5 . All of these elements are elements of $A$, so $A \subseteq A$. However, $A=A$, so $A$ is not a proper subset of $A$. Therefore, $A \not \subset A$.
(b) All of the elements of $B$ are also elements of $A$, so $B \subseteq A$. Further, $A$ contains elements (namely, 1 and 5) that are not in $B$, so $B$ is a proper subset of $A$; that is, $B \subset A$.
(c) One of the elements of $C$ is $\{4,5\}$. This is not an element of $A$ (it is a subset of $A$, which is not the same thing). So $C \nsubseteq A$ and by the same reasoning $C \not \subset A$.
(d) 4 is an element of $B$, so $4 \in B$. However, 4 is not an element of $C$. The set $C$ has two elements, the number 3 and the set $\{4,5\}$. So $4 \notin C$.

(e) We can list the subsets of $B$ :
$$\emptyset,\{2\},\{3\},\{4\},\{2,3\},\{2,4\},\{3,4\},\{2,3,4\}$$
(Don't forget that $\emptyset$ and $B$ itself are subsets of $B$.) There are 8 subsets of $B$.

Note some special properties of subsets:
- Every set is a subset of itself; that is, $A \subseteq A$ for any set $A$.
- The empty set is a subset of any set; that is, $\emptyset \subseteq A$ for any set $A$.
- If $A, B$ are two sets such that $A \subseteq B$ and $B \subseteq A$, then $A=B$.
- If $A$ and $B$ are any two sets, then we cannot have both $A \subset B$ and $B \subset A$.

Let's explain one of these properties now, and you'll be asked to explain the others in the exercises.

**Problem 2.2:** Show that the empty set is a subset of any set.

*Solution for Problem 2.2:* By the definition of subset, we know that $\emptyset \subseteq A$ if every element of $\emptyset$ is an element of $A$. But $\emptyset$ has no elements, so every element of $\emptyset$ (there aren't any of them!) is in $A$ (there's nothing to check!).

Every set $S$ has a special associated set called its power set, denoted by $\mathcal{P}(S)$. This is a set whose elements are all of the subsets of $S$. More precisely,
$$\mathcal{P}(S)=\{T \mid T \subseteq S\}$$

For example, if $S=\{1,3,4\}$, then
$$\mathcal{P}(S)=\{\emptyset,\{1\},\{3\},\{4\},\{1,3\},\{1,4\},\{3,4\},\{1,3,4\}\}$$

Notice that the elements of $\mathcal{P}(S)$ are sets, not numbers. This is perfectly legal-remember that "set" is a very general concept, and that elements of sets can be anything! Also notice that $\mathcal{P}(\emptyset)=\{\emptyset\}$, which is not the empty set: $\{\emptyset\}$ is a set with one element, and that element is the set $\emptyset$.

This can get a bit confusing, so let's look at an example.

**Problem 2.3:** Let $A=\{1,2,3,6\}$ be the set of positive divisors of 6 . Define
$$B=\{S \in \mathcal{P}(A) \mid 1 \notin S\} .$$

List the elements of $B$.

*Solution for Problem 2.3:* This problem is most easily solved by trying to get past all the notation and thinking about it in words. The elements of $B$ are exactly the subsets of $A$ that don't contain 1 as an element. So we can list them:
$$B=\{\emptyset,\{2\},\{3\},\{6\},\{2,3\},\{2,6\},\{3,6\},\{2,3,6\}\} .$$

Note also that $B=\mathcal{P}(\{2,3,6\})$.

> **Sidenote:** Some special sets
> Some sets are so common that they have special names. (We've already seen one such set, namely $\emptyset$.) Some others are:
> - $\mathbb{Z}$, the set of integers
> - $\mathbb{Q}$, the set of rational numbers
> - $\mathbb{R}$, the set of real numbers
> - $\mathbb{C}$, the set of complex numbers
>
> Note that $\mathbb{Z} \subset \mathbb{Q} \subset \mathbb{R} \subset \mathbb{C}$. (These sets are usually written, as they are here, in a font called "blackboard bold," which consists of regular capital letters with an extra line in them.)

### Exercises

2.2.1 Is $\emptyset=\{\emptyset\}$ ? Why or why not?

2.2.2 For each part, determine if the statement is true or false, and explain why or why not.
(a) $3 \in\{1,3,5,9\}$
(b) $\{2,6\}=\{6,2,2\}$
(c) $\{5\} \in\{3,5,9\}$
(d) $4 \in\{\{4\}\}$
(e) $\emptyset \subset\{1,2,9\}$
(f) $\emptyset \in\{\emptyset,\{1\}, 82\}$
(g) $\{x \mid x$ is an even integer $\} \subset \mathbb{Z}$

2.2.3 Explain why $A \subseteq A$ for any set $A$.

2.2.4 Explain why if $A \subseteq B$ and $B \subseteq A$, then $A=B$.

2.2.5 Is the subset relationship transitive? In other words, if $A \subseteq B$ and $B \subseteq C$, can we conclude that $A \subseteq C$ ? Why or why not? How about for proper subsets?

2.2.6 Suppose that $B$ is a set such that $B \subseteq \emptyset$. What can we conclude about $B$ ?

2.2.7 Explain why it is true that if $A$ and $B$ are finite sets and $A \subseteq B$, then $\#(A) \leq \#(B)$. What does it mean if $A \subseteq B$ and $\#(A)=\#(B)$ ? If $A$ and $B$ are finite sets such that $A \subset B$, what can we conclude about $\#(A)$ and \#( $B$ )?

2.2.8 Explain why it is impossible for two sets $A$ and $B$ simultaneously to satisfy $A \subset B$ and $B \subset A$.

2.2.9 ★ What is $\mathcal{P}(\mathcal{P}(\emptyset))$ ? Hints: 145

2.2.10★ Prove that if $S$ is a finite set and $\#(S)=n$, then $\#(\mathcal{P}(S))=2^{n}$. Hints: 316, 276

## 2.3 Operations on Sets

Just as we can perform operations on numbers, such as addition and multiplication, to get new numbers, we can perform operations on sets to get new sets. We start by defining the two basic operations on sets.

**Definition:** The union $A \cup B$ of two sets $A$ and $B$ is the set of all objects that are elements of at least one of $A$ and $B$.

We can write this more formally as:
$$A \cup B=\{x \mid x \in A \text { or } x \in B\} .$$

Note that our use of the word "or" in the line above does not mean "one or the other, but not both." Instead, we use the word "or" to mean "one or the other, or possibly both." (This is the way that logicians define "or," which we'll see in the next section of this chapter.) Elements that are in both $A$ and $B$ are also in their union.

Here are some examples:
- $\{2,3,8\} \cup\{1,7,11,13\}=\{1,2,3,7,8,11,13\}$.
- $\{4,8,9\} \cup\{2,4,9,11\}=\{2,4,8,9,11\}$. (We don't list 4 or 9 twice, even though they appear in both sets, since elements are not duplicated in a set.)
- $\{1,2,4\} \cup\{1,2,4,8\}=\{1,2,4,8\}$.
- $\{x \mid x$ is an even integer $\} \cup\{x \mid x$ is an odd integer $\}=\{x \mid x$ is an integer $\}$.

**Definition:** The intersection $A \cap B$ of two sets $A$ and $B$ is the set of all objects that are elements of both of $A$ and $B$.

We can write this more formally as:
$$A \cap B=\{x \mid x \in A \text { and } x \in B\} .$$

Some examples:
- $\{3,5,9,11\} \cap\{2,5,8,11,13\}=\{5,11\}$.
- $\{2,6,9,11\} \cap\{2,9\}=\{2,9\}$.
- $\{4,9,11,16\} \cap\{2,8,10,14\}=\emptyset$, since these two sets have no elements in common.
- $\{x \mid x$ is an even integer $\} \cap\{x \mid x$ is an odd integer $\}=\emptyset$.
- $\{x \mid x$ is an even positive integer $\} \cap\{x \mid x$ is a prime number $\}=\{2\}$.

A special case of union and intersection is shown in the following problem.

**Problem 2.4:** Suppose $A$ and $B$ are sets such that $A \subseteq B$.
(a) What is $A \cup B$ ?
(b) What is $A \cap B$ ?

*Solution for Problem 2.4:*
(a) If $A \subseteq B$, then every element of $A$ is also an element of $B$. This means that any element in $A$ or $B$ must be in $B$. Therefore, $A \cup B \subseteq B$. On the other hand, every element of $B$ is also an element of $A \cup B$, so $B \subseteq A \cup B$. Hence, $A \cup B=B$.
(b) Any element in $A$ and $B$ must be in $A$, so $A \cap B \subseteq A$. On the other hand, every element of $A$ is also an element of $B$, and thus also an element of $A \cap B$, so $A \subseteq A \cap B$. Therefore, $A \cap B=A$.

> **Important:** In order to show that two sets $A$ and $B$ are equal, we have to show that every element of $A$ is also an element of $B$, and we have to show that every element of $B$ is also an element of $A$.
>
> If we only do one of these but not both, all we're showing is that one set is a subset of the other. For example, if we show that every element of $A$ is also an element of $B$, then we've shown that $A \subseteq B$. In order to show that they're equal, we have to show the reverse as well.

It is useful to have a word describing when two sets have no elements in common:

**Definition:** If $A \cap B=\emptyset$, then we say that $A$ and $B$ are disjoint.

We can visualize the operations of union and intersection using Venn diagrams. In particular, if $A$ are $B$ are sets, represented by circles in a Venn diagram, then $A \cup B$ is the region inside of the two circles combined, and $A \cap B$ is the region inside of both circles.

These two operations-union and intersection-are distributive with respect to each other. We'll prove one of the distributive laws and leave the other as an exercise.

> **Extra!** Logic (and therefore probability as a branch of logic) is not concerned with what men do believe, but what they ought to believe, if they are to believe correctly. - John Venn

**Problem 2.5:** Prove that if $A, B$, and $C$ are sets, then
$$A \cap(B \cup C)=(A \cap B) \cup(A \cap C) .$$

*Solution for Problem 2.5:* To prove that two sets are equal, we must show that they have the same elements. This means that we must show that every element in one set is also in the other set, and vice versa.

So we start by letting $x$ be an element of $A \cap(B \cup C)$. This means that $x \in A$ and $x \in(B \cup C)$, which means that
$$x \in A \text { and }((x \in B) \text { or }(x \in C)) .$$

This can be rewritten as
$$(x \in A \text { and } x \in B) \text { or }(x \in A \text { and } x \in C) .$$

Now, rewriting our statement using union and intersection of sets, we have
$$x \in((A \cap B) \cup(A \cap C)) .$$

So all elements of $A \cap(B \cup C)$ are also elements of $(A \cap B) \cup(A \cap C)$, which means that
$$A \cap(B \cup C) \subseteq(A \cap B) \cup(A \cap C) .$$

We're not done! We have to show the reverse as well. To do so, let $y$ be an element of $(A \cap B) \cup(A \cap C)$. Then
$$(y \in A \text { and } y \in B) \text { or }(y \in A \text { and } y \in C) .$$

This can be written as
$$y \in A \text { and }(y \in B \text { or } y \in C)$$
which means that $y \in A \cap(B \cup C)$. Thus,
$$(A \cap B) \cup(A \cap C) \subseteq A \cap(B \cup C) .$$

Combining $\left(^{*}\right)$ and $\left({ }^{* *}\right)$, we see that $A \cap(B \cup C)$ and $(A \cap B) \cup(A \cap C)$ have the same elements, so they are equal.

The logic steps in the middle of the above argument might be a bit unclear-we'll cover more details of the logic involved in the next section-but we can also visualize the result using Venn diagrams.

The first diagram, at right, shows $A$ filled with diagonal lines in one direction, and $B \cup C$ filled with diagonal lines in the other direction. Their overlap, filled with the crossed diagonal lines, is the region that is in both sets; that is, it is the region $A \cap(B \cup C)$.

On the other hand, the diagrams below show $A \cap B$ shaded in the first picture, and $A \cap C$ shaded in the second picture. When we combine the pictures, the shaded region is the region that is in at least one of the intersections, so the shaded region in the right picture is $(A \cap B) \cup(A \cap C)$.

This is visual evidence that
$$A \cap(B \cup C)=(A \cap B) \cup(A \cap C) .$$

Note that using Venn diagrams in this way is not a proof, but it does allow us to see visually why the identity in question is true.

There are a couple more set-theory concepts that come up occasionally. One is the idea of a universal set, which is a set that contains all possible elements in a given problem or situation. For example, in an introductory algebra setting, the universal set might be the set $\mathbb{R}$ of real numbers, so that, for example,
$$\left\{x \mid x^{2}+1=0\right\}=\emptyset$$
because it is assumed that we are only considering elements $x \in \mathbb{R}$. On the other hand, if the universal set were the complex numbers, then
$$\left\{x \mid x^{2}+1=0\right\}=\{i,-i\}$$

Note that the universal set may vary from problem to problem, and it is not always explicitly stated.

In a Venn Diagram, often a universal set is denoted by a large box surrounding the diagram, as shown to the right. In any context in which we have a universal set, we have the implicit assumption that every set under discussion is automatically a subset of the universal set. In other words, we're not allowed to go "outside the box" of the universal set.

Generally, we prefer not to use universal sets unless the context is absolutely clear. For example, as discussed above, without a clear universal set, the set
$$\left\{x \mid x^{2}+1=0\right\}$$
is unclear. If the universal set is $\mathbb{R}$, then this set is empty, but if the universal set is $\mathbb{C}$, then this set is $\{i,-i\}$. It's usually much better to be upfront with our assumptions. For example, if we write
$$\left\{x \in \mathbb{R} \mid x^{2}+1=0\right\},$$
then it's clear that this is the empty set.

We also talk about the complement of a set $A$ with respect to a universal set $U$. This is the set of all elements (in $U$ ) that are not in $A$. For example, if $U=\mathbb{Z}$, the set of integers, and $A$ is the set of all odd integers, then the complement of $A$ is the set of all even integers. The complement of $A$ is sometimes denoted $A^{C}$ or $U-A$ or $U \backslash A$. In a Venn Diagram, the complement of $A$ is the shaded region in the diagram at left.

We can also define the set-theoretic difference of two sets $A$ and $B$. This set, denoted either $A-B$ or $A \backslash B$, is the set of all elements of $A$ that are not elements of $B$. For example, if
$$A=\{1,4,5,9,11\} \quad \text { and } \quad B=\{2,4,5,8,10\},$$
then
$$A \backslash B=\{1,9,11\},$$
since those are the elements of $A$ that are not elements of $B$. The "extra" elements of $B(2,8$, and 10$)$ are irrelevant. The set-theoretic difference $A \backslash B$ is represented by the shaded area in the Venn Diagram above to the right.

### Exercises

2.3.1 For any set $A$, what are $A \cup \emptyset$ and $A \cap \emptyset$ ?

2.3.2 Prove that $A \cup A=A \cap A=A$.

2.3.3 If $x \in S$, what are $S \cup\{x\}$ and $S \cap\{x\}$ ?

2.3.4 Show that $A \cup(B \cap C)=(A \cup B) \cap(A \cup C)$.

2.3.5
(a) Suppose that $A \cup B=A$. What can we conclude about $A$ and $B$ ?
(b) Suppose that $A \cap B=A$. What can we conclude about $A$ and $B$ ?

2.3.6★ If $S$ and $T$ are sets, describe $\mathcal{P}(S \cap T)$ in terms of $\mathcal{P}(S)$ and $\mathcal{P}(T)$. Can you similarly describe $P(S \cup T)$ ? Hints: 103

## 2.4 Truth and Logic

Informally, for our purposes in this book, logic is the way that we interpret statements of fact and use them to prove new statements of fact. (What a professional mathematician means by "logic" is something far different, much more abstract, and well beyond the scope of this book.) In most cases, you will find that logic is just an extension of your natural common sense, but in this section we will be careful to try to explicitly state all of our assumptions and conclusions.

To start with, a statement (or proposition) is an assertion that is either true or false (but never both). "False" is the opposite of "true." We are not able to define what "true" or "false" means, but you should use your common sense. (Philosophers, mathematicians, and logicians have been debating for centuries about the meaning of "truth," and we're certainly not going to enter that debate here.)

Some examples of statements are:
- Paris is the capital of France. (This is a true statement.)
- New York is the capital of the United States. (This is a false statement.)
- $0=1$. (False.)
- $3<8$. (True.)
- All even integers are divisible by 2 . (True. The word "all" means that this is an example of a quantified statement, which we'll talk more about in the next section of the chapter.)
- There exists an integer whose square is 7 . (False. The phrase "there exists" is another example of a quantified statement.)
- There exists a real number whose square is 7. (True.)

Some examples of things that are not statements are:
- Is Madrid the capital of Spain? (This is a question, not a statement.)
- Pizza is good. (This is an opinion, not a statement of fact.)
- Kaflooy is the capital of Garglbox. (This is just nonsense; it's not true nor false since the words have no meaning.)
- $2+9$. (This is a value.)
- There exists a number whose square is 7 . (This is not a statement unless we more carefully define what "number" means. If "number" means "integer," then it's false. If "number" means "real number," then it's true.)
- This statement is false. (This cannot be true or false without contradicting itself, so it is not a statement.)

There are three basic operations that we can perform on statements to get new statements, sometimes called compound statements.
- The negation of a statement $p$, denoted $\neg p$, is the statement that is true when $p$ is false and is false when $p$ is true. Stated more simply, $\neg p$ is the opposite of $p$. For example, if $p$ is the statement "Paris is the capital of France," then $\neg p$ is the statement "Paris is not the capital of France."
- The conjunction of two statements $p$ and $q$, denoted $p \wedge q$, is the statement " $p$ and $q$ ". For example, if $p$ is "Paris is the capital of France" and $q$ is "Madrid is the capital of Spain," then $p \wedge q$ is "Paris is the capital of France and Madrid is the capital of Spain." The statement $p \wedge q$ is true provided that both $p$ is true and $q$ is true; otherwise $p \wedge q$ is false.
- The disjunction of two statements $p$ and $q$, denoted $p \vee q$, is the statement " $p$ or $q$ ". As above, if $p$ is "Paris is the capital of France" and $q$ is "Madrid is the capital of Spain," then $p \vee q$ is "Paris is the capital of France or Madrid is the capital of Spain." It is true provided that at least one of $p$ and $q$ is true (perhaps both); otherwise $p \vee q$ is false.

> **Concept:** Don't worry about learning or memorizing the names (like "conjunction") or the symbols (like " $\wedge$ "). What's important is that you know what the terms "and", "or", and "not" mean. We'll almost never use the names, and we'll only rarely use the symbols.

Sometimes we analyze more complicated statements by means of a truth table. A truth table simply lists all of the possible values of a compound statement, given the possible values of its component parts. For example, we show the truth tables of our basic operations in Figure 2.1 below. In these tables, T represents "true" and F represents "false." For example, the table on the right in Figure 2.1 lists the truth value of " $p$ or $q$ " for each possible pair of values for $p$ and for $q$.

Figure 2.1: Truth tables for the basic logic operations

> **Concept:** You should get comfortable enough with "and", "or", and "not" so that these truth tables are as automatic to you as an addition table.

> **Important:** In order to prove that a statement of the form " $p$ and $q$ " is true, you must prove that both $p$ and $q$ are true. In order to prove that a statement of the form " $p$ or $q$ " is true, you must prove that at least one of $p$ and $q$ are true.

Let's do a simple example of proving the truth value of a more complicated statement.

**Problem 2.6:** Prove that, for any statement $p$, the statement " $p$ and (not $p$ )" is always false.

*Solution for Problem 2.6:* First, we know that this statement must be false, just by common sense. There's no way that a statement and its opposite can both be true: in fact, we always have that one is true and the other is false.

But to formally establish this, we can resort to a truth table. The statement $p$ can itself be either true or false. So we make a table listing the possible values of $p$, and the resulting values of " $p$ and (not $p$ )."

\begin{tabular}{c|c|c}
$p$ & not $p$ & $p$ and $(\operatorname{not} p)$ \\
\hline T & F & F \\
F & T & F
\end{tabular}

As we can see from the table, any input value of $p$ makes the statement false.

Here is a slightly more complicated example. We'll write it using symbols because it's a bit complicated to write it in words.

**Problem 2.7:** Prove that, for any statements $p$ and $q$, the statements $p \vee q$ and $\neg((\neg p) \wedge(\neg q))$ are either both true or both false.

*Solution for Problem 2.7:* This one is a bit too complicated for us to use "common sense," so let's go straight to the truth table. We list the truth table for all possible values of $p$ and $q$. Note that we show the truth value of all the intermediate terms, to make the results clear.

\begin{tabular}{c|c|c|c|c|c|c}
$p$ & $q$ & $p \vee q$ & $\neg p$ & $\neg q$ & $(\neg p) \wedge(\neg q)$ & $\neg((\neg p) \wedge(\neg q))$ \\
\hline T & T & T & F & F & F & T \\
T & F & T & F & T & F & T \\
F & T & T & T & F & F & T \\
F & F & F & T & T & T & F
\end{tabular}

Note that the $3^{\text {rd }}$ and last columns are identical, proving the assertion.

By the way, the statement of Problem 2.7 is known as one of DeMorgan's Laws. In English, we would say that " $p$ or $q$ " is equivalent to the statement "not((not $p$ ) and (not $q$ ))." Think about, in English, why that makes sense. You'll get a chance to prove a version of another one of DeMorgan's Laws in the exercises.

The other very important operation that we use to make compound statements out of simple statements is that of implication. This is the operation given by the statement "If $p$, then $q$ " and is denoted by $p \Rightarrow q$. We may also read $p \Rightarrow q$ as " $p$ implies $q$." This is a true statement unless $p$ is true and $q$ is false, in which case it is false. For example, if $p$ is the statement " 4 is an odd number" and $q$ is the statement " 10 is prime," then $p \Rightarrow q$ is the statement "If 4 is an odd number, then 10 is prime." This is an example of a true statement, although some people find this a bit counterintuitive, and draw the following incorrect conclusion:

This is incorrect logic. 4 is an even number, so "If 4 is an odd number, then 10 is prime" is true. If the part following the "If" in an implication is false, then the implication is automatically true. For example, "If pigs can fly, then I am a billionaire" is a true statement: pigs can't fly, so we can put any statement we like after the "then" and get a true statement (even though, sadly, I am not a billionaire).

We can also list the truth table of $p \Rightarrow q$ :

\begin{tabular}{c|c|c}
$p$ & $q$ & $p \Rightarrow q$ \\
\hline T & T & T \\
T & F & F \\
F & T & T \\
F & F & T
\end{tabular}

The only time that $p \Rightarrow q$ is false is if $p$ is true and $q$ is false. For example, "If 9 is odd, then 28 is a perfect square" is false.

We also have the two-way implication $p \Leftrightarrow q$, which is a shorthand for $(p \Rightarrow q) \wedge(q \Rightarrow p)$. In words, we would write " $p$ if and only if $q$." Some people abbreviate this to " $p$ iff $q$," but this should be considered shorthand only, and not correct mathematical writing. Here's the truth table:

\begin{tabular}{c|c|c|c|c}
$p$ & $q$ & $p \Rightarrow q$ & $q \Rightarrow p$ & $p \Leftrightarrow q$ \\
\hline T & T & T & T & T \\
T & F & F & T & F \\
F & T & T & F & F \\
F & F & T & T & T
\end{tabular}

Note that $p \Leftrightarrow q$ is true whenever $p$ and $q$ have the same truth value (they're either both true or both false), and $p \Leftrightarrow q$ is false whenever $p$ and $q$ have different truth values (one is true and the other is false). So we could have rewritten Problem 2.7 as:

**Problem 2.7:** Prove that, for any statements $p$ and $q$, the statement
$$(p \vee q) \Leftrightarrow(\neg((\neg p) \wedge(\neg q)))$$
is always true.

There are two important logical operations that we can do to an implication. The first is to take its converse.

**Definition:** The converse of the statement $p \Rightarrow q$ is the statement $q \Rightarrow p$.

In other words, we swap the "if" and "then" parts.

Note that the truth or falsehood of an inference gives us no information about the truth or falsehood of its converse. For example, the statement "If a man lives in Los Angeles, then he lives in California" is true, but its converse "If a man lives in California, then he lives in Los Angeles" is false (since, for example, he might live in San Diego).

We can also list a truth table to see that the truth values of $p \Rightarrow q$ and $q \Rightarrow p$ are not necessarily the same:

\begin{tabular}{c|c|c|c}
$p$ & $q$ & $p \Rightarrow q$ & $q \Rightarrow p$ \\
\hline T & T & T & T \\
T & F & F & T \\
F & T & T & F \\
F & F & T & T
\end{tabular}

> **Important:** A very common logical mistake that students often make when working proof-style problems is to prove the converse of what the problem is asking. As we have seen, the converse of an implication can be true even if the original implication is false.

The other common operation that we can do to an implication is to take its contrapositive.

**Definition:** The contrapositive of the statement $p \Rightarrow q$ is the statement $\neg q \Rightarrow \neg p$.

In other words, we swap the "if" and "then" parts and take the negation of both.

In contrast to the converse, the contrapositive of an implication has the same truth value as the original implication. For example, the statement "If a man lives in Los Angeles, then he lives in California" is true, and its contrapositive "If a man does not live in California, then he does not live in Los Angeles" is also true. We can also see this in a truth table:

\begin{tabular}{c|c|c|c|c|c}
$p$ & $q$ & $p \Rightarrow q$ & $\neg p$ & $\neg q$ & $\neg q \Rightarrow \neg p$ \\
\hline T & T & T & F & F & T \\
T & F & F & F & T & F \\
F & T & T & T & F & T \\
F & F & T & T & T & T
\end{tabular}

> **Concept:** Sometimes in proof-style problems, it's easier to prove the contrapositive of what the problem is asking than it is to prove the original problem statement. As we've just seen, this is logically valid: an implication is logically equivalent to its contrapositive.

### Exercises

2.4.1 Which of the following are statements? (For any that are not statements, briefly explain why not.)
(a) 2 is an odd number.
(b) The author of this book has brown eyes.
(c) Infinity is really cool.
(d) George Washington was the first president of the United States if and only if (a touchdown in football is worth 11 points) and $\left.\left(8+3^{2}=2^{4}+1\right)\right)$.
(e) Can you drive a car?
(f) $x^{2}+x-3$

2.4.2 Prove that " $p$ or (not $p$ )" is always true for any statement $p$.

2.4.3 Prove that, for any statements $p$ and $q$, the statements $\neg(p \wedge q)$ and $(\neg p) \vee(\neg q)$ are either both true or both false. (This is another of DeMorgan's Laws.)

## 2.5 Quantifiers

- The universal quantifier is the equivalent of the words "for all" or "every." It is sometimes denoted by an upside-down "A", like so: $\forall$. For example, we can write the (false) statement "All integers are divisible by $2^{\prime \prime}$ as
$$\forall x \in \mathbb{Z}, 2 \mid x .$$

In English, we would read this as "For all elements $x$ of the set of integers, 2 divides $x$." This means, naturally, that 2 divides every element of $\mathbb{Z}$, the integers. Of course, this is a false statement, but it is a legal statement nonetheless.

- The existential quantifier is the equivalent of the words "there exists." It is sometimes denoted by a backwards "E", like so: $\exists$. For example, we can write the statement "There exists an integer $x$ such that $x^{2}-5 x+6=0^{\prime \prime}$ as
$$\exists x \in \mathbb{Z}, x^{2}-5 x+6=0$$

In English, this reads "There exists an element $x$ in the set of integers such that $x^{2}-5 x+6=0$." This means that there is some element of $\mathbb{Z}$ that makes the statement true.

Here is the general description of the two quantifiers:

> **Concept:** If $S$ is a set and $p(x)$ is a statement that depends on an element $x$ of $S$, then:
> - $\forall x \in S, p(x)$ means that $p(x)$ is true for all elements $x$ of $S$.
> - $\exists x \in S, p(x)$ means that $p(x)$ is true for at least one element $x$ of $S$.

> **Important:** The symbols are not that important, and you won't see them that often. The meaning of the quantifiers is what's important. It is very important to understand the difference between a statement being true for all elements of a set, and merely that there exists an element of the set that makes the statement true.

For example, the statement "All triangles are equilateral" is clearly false. But the statement "There exists an equilateral triangle" is clearly true.

We can combine quantifiers in the same statement; for example, the statement:
For every positive real number $x$, there exists a positive real number $y$ such that $x=y^{2}$. This statement can be written symbolically as
$$\forall x \in \mathbb{R}, x>0 \Rightarrow\left(\exists y \in \mathbb{R},(y>0) \wedge\left(x=y^{2}\right)\right) .$$

I said that the statement can be written symbolically, but we almost never do so, because as you can see, it's pretty unreadable. Just use English.

Note that the order of quantifiers is important! The following is wrong:

> **Bogus Solution:** There exists some positive real number $y$ such that for every positive real number $x$, we have $x=y^{2}$.

Clearly this is not true: this would mean that every real number has the same square root!

> **Important:** Make sure your quantifiers are in the correct order!

When we want to negate a statement that involves a quantifier, we have to be careful to also reverse the quantifier. For example, the negation of the statement "All cars have four wheels" is the statement "There exists a car that does not have four wheels." In the first statement, all cars have four wheels, so to get the opposite of that statement, we don't need that all cars don't have four wheels, we just need some car without four wheels. Another example is "There exists a person from Canada who plays hockey." The negation of this statement is "All people from Canada do not play hockey."

Symbolically, if $p(x)$ is a statement that depends on a variable $x$ that is an element of a set $S$, then the opposite of the statement

For all $x \in S, p(x)$ is true

is

There exists $x \in S$ such that $p(x)$ is false.

> **Important:** To prove a universally-quantified statement-a statement that is true "for all $x \in S^{\text {" }}$-you must prove that the statement is true for every $x$ in the set $S$. On the other hand, to prove an existentially-quantified statement-a statement for which "there exists $x \in S^{\prime \prime}$ that makes it true-you only have to find a single $x$ in the set $S$ that makes the statement true.

### Exercises

2.5.1 Explain why the statements

There exists $x \in S$ such that $p(x)$ is true

and

For all $x \in S, p(x)$ is false

are opposites.

2.5.2 Find an example of a statement $p(x, y)$ in terms of two integers $x$ and $y$ such that the statement
$$\exists x \in \mathbb{Z}, \forall y \in \mathbb{Z}, p(x, y)$$
is true, whereas the statement
$$\forall x \in \mathbb{Z}, \exists y \in \mathbb{Z}, p(x, y)$$
is false.

## 2.6 Summary

In this section, we discussed some of the basic building blocks of higher mathematics: sets and logic. The point of this chapter is not to study these topics very deeply in and of themselves, but rather to make sure that we have the necessary tools to construct valid proofs. The symbolism in this chapter is not really that important.

What's important is to understand the concepts that underlie set theory and basic logic. Some of these concepts are:
- What sets are and how they can be described
- How sets are related to their subsets
- The empty set $\emptyset$
- The power set $\mathcal{P}(S)$ of a set $S$
- How to combine sets by union and intersection
- The basics of truth and logic: statements are either true or false
- The meanings of "and", "or", and "not"
- The meaning of an "if. . . then. . ." inference
- The converse and contrapositive of an inference
- The meanings of, and difference between, "for all" and "there exists"

## Review Problems

**2.8** Let
$$\begin{aligned}
S & =\{1,2,3, \ldots, 30\}, \\
D & =\{n \in S \mid n \geq 0 \text { and the units digit of } n \text { is } 9\}, \\
P & =\{p \in S \mid p \text { is a positive prime }\}, \\
U & =\{n \in S \mid n \equiv 1(\bmod 4)\}=\{n \in S \mid \exists k \in \mathbb{Z}, n=4 k+1\}, \\
V & =\{n \in S \mid n \equiv 3(\bmod 4)\}=\{n \in S \mid \exists k \in \mathbb{Z}, n=4 k+3\}, \\
W & =\{n \in S \mid n \equiv 2(\bmod 4)\}=\{n \in S \mid \exists k \in \mathbb{Z}, n=4 k+2\} .
\end{aligned}$$

(a) Find the sets $D, P, U, V, W, D \cap U, P \cap W, S \backslash P$, and $P \backslash(D \cup V)$, by explicitly listing the elements of each set.
(b) Which is greater, $\#(P \cap U)$ or $\#(P \cap V)$ ?

**2.9** Let $T=\{-2,-1,0,1,2,3,4,5\}$.
(a) What is $\left\{x^{2} \mid x \in T\right\}$ ?
(b) What is $\left\{x \in \mathbb{Z} \mid x^{2} \in T\right\}$ ?

**2.10** The sets $A, B$, and $C$ satisfy $A \cap B=B \cap C=\emptyset$. Is it necessarily true that $A \cap C=\emptyset$ ?

**2.11** Are the converses of the statements in Problem 2.4 true? In other words:
(a) If $A$ and $B$ are sets such that $A \cup B=B$, must $A \subseteq B$ ?
(b) If $A$ and $B$ are sets such that $A \cap B=A$, must $A \subseteq B$ ?

If they are true, explain why. If they are not true, show an example where they fail.

**2.12** If $A \backslash B=A$, then what can we say about sets $A$ and $B$ ?

**2.13** The finite sets $A$ and $B$ satisfy $\#(A \backslash B)=\#(B \backslash A)$. Does it follow that $\#(A)=\#(B)$ ?

**2.14** Show that for any statements $p, q$, and $r$, the statement
$$((p \Rightarrow q) \wedge(q \Rightarrow r)) \Rightarrow(p \Rightarrow r)$$
is always true.

**2.15** Let $A$ be the set of mathematicians, let $B$ be the set of snobs, let $C$ be the set of scientists, let $D$ be the set of people who have been to Mars, let $E$ be the set of people who have drunk coffee, and let $U$ be the set of all people. Let $p(x, y)$ denote the statement " $x$ has taken a photo of $y$ ". Express the following statements in plain English:
(a) $B \subset U$.
(b) $A \subseteq C$.
(c) $(A \cap D) \subseteq E$.
(d) $U=C \cup E$.
(e) $\forall x \in U,(p(x, x) \Rightarrow x \in B)$.
(f) $\forall x \in C, \exists y \in E, p(x, y)$.
(g) $\exists y \in E, \forall x \in C, p(x, y)$.

**2.16** Using the same notation as in the last problem, express the following statements using set and logic notation.
(a) Only snobs drink coffee.
(b) Not all scientists are snobs.
(c) Some mathematician has drunk a coffee.
(d) If everyone has been to Mars, then every scientist has drunk a coffee.
(e) Every mathematician has taken a photo of a snob.
(f) Everyone who has been to Mars is a snob, except for scientists.
(g) The only people who have taken a photo of everyone who has drunk a coffee are scientists.

**2.17** Let $p(x)$ be a statement that depends on the element $x$.
(a) What can you say about the truth of the statement " $\forall x \in \emptyset, p(x)$ "?
(b) What can you say about the truth of the statement " $\exists x \in \emptyset, p(x)$ "?

## Challenge Problems

**2.18** Show that for any sets $A, B$, and $C$, we have $C \subseteq A$ if and only if $(A \cap B) \cup C=A \cap(B \cup C)$.

**2.19** A set $S$ of real numbers is called an interval if for all $x, y \in S$, we have
$$\{z \in \mathbb{R} \mid x \leq z \leq y\} \subseteq S$$

For example, the sets $[0,1],(-10,5)$, and $[3, \infty)$ are all intervals.
(a) Is the union of two intervals always an interval?
(b) Is the intersection of two intervals always an interval?

**2.20** The exclusive or operation, denoted by $\oplus$, is defined so that $p \oplus q$ is true if and only if $p$ is true or $q$ is true, but not both.
(a) Show that for any statements $p, q$, and $r$, the statements $(p \oplus q) \oplus r$ and $p \oplus(q \oplus r)$ are equivalent.
(b) Show that for any statements $p, q$, and $r$, the statements $p \wedge(q \oplus r)$ and $(p \wedge q) \oplus(p \wedge r)$ are equivalent.

**2.21** Which of the following statements are equivalent to $\neg(\forall x \in S, \exists y \in T, p(x, y))$ ? (More than one may be equivalent.)
(i) $\forall x \in S, \exists y \in T, \neg p(x, y)$.
(ii) $\exists x \in S, \forall y \in T, \neg p(x, y)$.
(iii) $\forall x \in S, \neg(\exists y \in T, p(x, y))$.
(iv) $\exists x \in S, \neg(\exists y \in T, p(x, y))$.
(v) $\exists x \in S, \neg(\forall y \in T, p(x, y))$.

**2.22** The symmetric difference of two sets $A$ and $B$ is defined as $(A \backslash B) \cup(B \backslash A)$, and is denoted by $A \ominus B$.
(a) Let $A=\{1,2,3,4,7,8\}, B=\{2,4,5,7,9,10\}$, and $C=\{3,6,7,8,9\}$. Find $A \ominus B,(A \ominus B) \ominus C, B \ominus C$, and $A \ominus(B \ominus C)$.
(b) Use part (a) of Problem 2.20 to show that $(A \ominus B) \ominus C=A \ominus(B \ominus C)$ for all sets $A, B$, and $C$.
(c) What identity of set theory does part (b) of Problem 2.20 give rise to?
