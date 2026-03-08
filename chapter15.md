# Chapter 15: Graph Theory

> At what point on the graph do "must" and "cannot" meet? Yet I must, but I cannot! - Ro-Man, Robot Monster

## 15.1 Introduction

A graph is a visual tool that is very useful for solving a large number of problems. More specifically, a graph depicts connections or relationships between objects.

For example, we can use a graph to show the six New England states, and which of them border each other:

Whenever we have a set and we also have relationships between some pairs of items in the set, we can represent the set and its relationships as a graph. Drawing a graph is usually a better way for us to imagine and work with the relationships than simply listing them. For instance, which is easier to work with, the graph of the New England states above, or the list of bordering states shown below?
$$\text { \{(VT, NH), (NH, ME), (MA, VT), (NH, MA), (MA, CT), (MA, RI), (CT, RI)\} }$$

The graph lets us see complex relationships a lot more easily than a simple list of pairs does. To continue

## 15.6 Exercises

15.6.4 ★ An $n$-dimensional cube (for $n \geq 2$) is a graph with $2^{n}$ vertices that are in 1-1 correspondence with $n$-tuples of 0's and 1's. Two vertices are connected by an edge if and only if they differ in exactly one coordinate. (The graph of the 3-dimensional cube is show at right.) Show that an $n$-dimensional cube has a Hamiltonian cycle. Hints: 84

## 15.7 Summary

- For our purposes, "graph" means a simple graph with no loops, no directed edges, and at most one edge between any pair of vertices.
- Whenever we have a set and we also have relationships between some pairs of items in the set, we can represent the set and its relationships as a graph. The elements of the set are the vertices of the graph, and the relationships between pairs of elements are the edges.
- It is often easier to visualize complex relationships using a graph.
- If a graph has $n$ vertices and each vertex has degree $d$, then the graph has $n d / 2$ edges. More generally, if the degrees of the vertices of a graph sum to $s$, then the graph has $s / 2$ edges.
- In any graph, the number of vertices with odd degree must be even.
- A path between two vertices $A$ and $B$ is a (finite) sequence of edges $e_{1}, e_{2}, \ldots, e_{k}$ such that edge $e_{1}$ connects $A$ with some vertex $V_{1}$, edge $e_{2}$ connects $V_{1}$ with some vertex $V_{2}$, and so on, until edge $e_{k}$ connects vertex $V_{k-1}$ with $B$. The positive integer $k$ is called the length of the path. A path with no repeated edges is called a simple path. A simple path that starts and ends at the same vertex is called a cycle.
- A graph is called connected if, for every pair of distinct vertices $A$ and $B$, there exists a path from $A$ to $B$.
- A connected graph with no cycles is called a tree.
- A connected graph with $n$ vertices has at least $n-1$ edges. A tree with $n$ vertices has exactly $n-1$ edges, and contains at least 2 vertices of degree 1 (called leaves). A graph with at least as many edges as vertices must contain a cycle.
- A graph $G$ is called bipartite if the vertices of $G$ can be partitioned into two sets $S$ and $T$, such that every edge of $G$ connects a vertex in $S$ with a vertex in $T$. A graph is bipartite if and only if it has no cycle of odd length.
- A connected graph that can be drawn on the plane so that none of its edges intersect at a non-vertex point is called planar.
- Euler's formula for connected planar graphs: $V+F=E+2$, where $V$ is the number of vertices, $E$ is the number of edges, and $F$ is the number of faces.
- If a graph is planar, connected, and has more than 1 edge, then $E \leq 3 V-6$. Therefore, if a connected graph with more than 1 edge satisfies $E>3 V-6$, then the graph is not planar.
- An Eulerian path of a graph is a path that contains every edge of the graph exactly once. If an Eulerian path is also a cycle, then it is called an Eulerian cycle. A Hamiltonian path of a graph is a path that contains every vertex of the graph exactly once. A Hamiltonian cycle is a cycle that contains every vertex (except the starting and ending point) exactly once.
- A connected graph has an Eulerian path if and only if it has at most 2 vertices with odd degree. A connected graph has an Eulerian cycle if and only if it has no vertices with odd degree.

We also saw the following general problem-solving concepts:

> Concept: In order to prove that $n$ is the minimum possible integer number of something in a problem, we need to show two things: that $n$ is possible, and that $n-1$ (or less) is impossible.

> Concept: Often when solving a problem, it pays to focus on the object with the most of something (or the least of something). This is sometimes referred to as the extremal principle.

## Review Problems

**Problem 15.20:**
(a) Can a country in which 3 roads lead out of every city have exactly 50 cities? Why or why not?
(b) Can a country in which 3 roads lead out of every city have exactly 35 cities? Why or why not?

**Problem 15.21:** 17 people are at a party. For any pair of people present, they are friends, enemies, or don't know each other. Prove that there must be a group of 3 people all of whom are mutual friends, enemies, or strangers.

**Problem 15.22:** In the school ping-pong tournament only 6 students entered. The organizers decide to have exactly 7 games, and also mandate that out of any 3 players, at least two must play each other. Prove that:
(a) There exists a student who plays against at least 3 other students.
(b) There exist three people who each play against the other two.
(Source: Romania)

**Problem 15.23:** A graph $G$ has $n$ vertices, with degrees $d_{1}, d_{2}, \ldots, d_{n}$. How many paths of length 2 are there?

**Problem 15.24:** Show that distance on a graph satisfies the Triangle Inequality: if $A, B$, and $C$ are vertices and are all connected to each other, then
$$d(A, C) \leq d(A, B)+d(B, C) .$$

**Problem 15.25:** A connected planar graph $G$ has 10 faces, and every vertex of $G$ has degree 4. Find the number of vertices of $G$.

**Problem 15.26:** In a connected planar graph, every vertex has degree 3, and every face is bordered by 5 or 6 edges. How many faces are bordered by 5 edges?

**Problem 15.27:** At a conference, everybody has at least 1 friend among the people attending. It is known that among any group of at least 3 people, there are never exactly two pairs of friends. Prove that there is a person that is friends with everyone at the conference.

**Problem 15.28:** Is it possible for a knight to travel around a standard $8 \times 8$ checkerboard such that it makes every possible move exactly once? (We consider a move to be completed if it is made in either direction.)

## Challenge Problems

**Problem 15.29:** In the ham radio club, there are 78 members, and each member is friends with at least 52 other members. Prove that there are 4 members with the same number of friends. Hints: 318, 247

**Problem 15.30:** Suppose there is a group of people in which each person has at most 3 enemies, and enemies are mutual (i.e. if person A hates person B, then person B also hates person A). Prove that it is possible to split the people into two groups so that each person has at most one enemy in his or her group. Hints: 28

**Problem 15.31:** A city has the following property: if any set of citizens were to meet, the number of introductions necessary to acquaint everyone would be less than the number of citizens present. Prove that the city may be partitioned into two groups of people, such that each person knows everyone else in their group.
Hints: 221

**Problem 15.32:** At a homecoming dance, no boy dances with every girl, but each girl dances with at least one boy. Prove that there are two couples $g$ and $g^{\prime} b^{\prime}$ who dance such that $g$ doesn't dance with $b^{\prime}$ and $g^{\prime}$ doesn't dance with b. (Source: Putnam) Hints: 152

**Problem 15.33:** \* Prove that if $G$ is a connected graph with $n$ vertices, and each vertex of $G$ has degree at least $n / 2$, then $G$ has a Hamiltonian cycle. (This is known as Dirac's Theorem.) Hints: 22

**Problem 15.34:** \* A domino consists of two squares, each of which is marked with between 0 and 6 dots (inclusive). The complete set of 28 dominos is shown at right. Is it possible to arrange all 28 dominos in a circle, such that adjacent halves of neighboring dominos have the same number of dots? Hints: 88, 349

**Problem 15.35:** \* In the country of Eulandia, any two cities are connected either by rail or by bus (but not both). Prove that for any city, we can choose a type of transportation (rail or bus) such that every other city in Eulandia can be reached via the chosen type of transportation with at most 1 transfer. Hints: 135
