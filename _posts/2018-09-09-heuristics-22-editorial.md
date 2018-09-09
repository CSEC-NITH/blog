---
layout: post
title:  "Heuristics 22 Editorial"
date:   2018-09-09
---

## Easy Problem

The problem requires to find the LCM of two positive integers. Since, number are upto $$10^9$$, we need a solution which can calculate it in $$O(logN)$$. So, calculate GCD(A, B) in $$O(log(min(A, B)))$$ using Euclid's algorithm or the C++ implicit function and using that, calculate LCM(A, B).

[Solution](https://gist.github.com/Uditgulati/3fbc2374655fe4b8df5c0493a87ade77#file-easy-problem-cpp)

**Overall Complexity:** $$O(T * log(min(A, B)))$$

---

## Brackets Regularity

In this problem, it was required to break the given regular bracket sequence into maximum number of smaller non-empty regular bracket sequences. One can observe that any continuous sub-sequence of the regular sequence which is having equal opening and closing brackets is also a regular sequence. So, just greedily take the smallest valid continuous sub-sequence from left to right.

[Solution](https://gist.github.com/Uditgulati/3fbc2374655fe4b8df5c0493a87ade77#file-brackets-regularity-cpp)

**Overall Complexity:** $$O(T * length(S))$$

---

## Math Love

The problems requires to find the maximum no. of operations it'll take to reduce B to less than A with just division by some number which divides B. If at each step, out of all possible divisors, if one takes the one which is smallest, then it'll result in maximum number of operations. So, now the problem rediuces to finding the smallest divisor which divides the given number and smallest divisors of all numbers in $$[2, 10^6]$$ can be pre-calculated using sieve of eratosthenes in $$O(N * logN).

[Solution](https://gist.github.com/Uditgulati/3fbc2374655fe4b8df5c0493a87ade77#file-math-love-cpp)

**Overall Complexity:** $$O((N * logN) + (T * logB))$$ with N = $$10^6$$

---

## Assigning Heroes

The problem states that given a graph and X marked nodes, allocate K heroes such that the sum of the minimum distance of each hero to it's nearest marked node is the minimum possible. Just calculate the distance of each node to it's nearest marked node and sort all min distances for each node and pick the smallest K values. Now, to calculate all min distances using one BFS, just mark all marked nodes as sources and push them to queue and run the BFS.

[Solution](https://gist.github.com/Uditgulati/3fbc2374655fe4b8df5c0493a87ade77#file-assigning-heroes-cpp)

**Overall Complexity:** $$O(T * max(N, M))$$

---

## Make 'em One

The problem states that given an array and some value K and a range $$[L, R]$$, find the sum of absolute difference of each element of the range with K. This can be done in $$O(logN)$$ per query using merge sort tree. Construct the merge sort tree of the array and also, store prefix sum of list in the merge sort tree. Use the merge sort tree to get the sum of all values below K and same goes for values above K. Let X be the count of values below K and Y be the count of values above K. Then, answer would be $$(X * K - sum of values below K) + (sum of values above K - Y * K)$$.

[Solution](https://gist.github.com/Uditgulati/3fbc2374655fe4b8df5c0493a87ade77#file-make-em-one-cpp)

**Overall Complexity:** $$O(Q * logN)$$

---

## Forming Teams

The probem is basically to find the number of triangles in a graph. The brute force solution is to take the intersection of each pair of adjacency list and take the count with complexity of $$O(N * N + M)$$. A better solution would be the one I read on Quora and is given below-

Lets consider graph consisting from N vertices and M edges. Lets define vertex as heavy if it has more than $$\sqrt{M}$$ neighbours and light otherwise. According to definition it can be proven that there is no more than $$\sqrt{M}$$ heavy vertices. Consider four cases of triangles in undirected graph:

1. Heavy-heavy-heavy
2. Heavy-heavy-light
3. Heavy-light-light
4. Light-light-light

We also need a hash set to efficiently check if some edge is presented in our graph.
To count number of triangles of type (1) we can just iterate though triples of heavy vertices and checking if they are pairwise connected. Since there is $$O(\sqrt{M})$$ of them, total time would be: $$O(M * \sqrt{M})$$.
In cases (2)-(3) you have at least one heavy vertex so you can iterate over it. Let it be q for notation. You need also to have an inner cycle iterating over all the edges (u, v) and checking if it fits type (2) or (3) (e.g. pair of vertices are either heavy and light or light and light) and that (u, v, q) is a triangle. This is also would require $$O(M * \sqrt{M})$$ time.
Finally, in case (4) you need to iterate through all edges (u, v) such that u and v are light vertices and just intersect their adjacency lists in linear time. Since they are light vertices total time here would be $$O(M * \sqrt{M})$$.

**Overall Complexity:** $$O(T * M * \sqrt{M})$$