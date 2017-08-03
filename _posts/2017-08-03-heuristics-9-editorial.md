---
layout: post
title:  "Heuristics #9 - Editorial"
date:   2017-08-03
author: udit
---

This edition of Heuristics was [Doctor Who](https://en.wikipedia.org/wiki/Doctor_Who)(TV Show) themed. Do check it out, if you are a sci-fi fan ;). 

## [Doctor and Coins](https://www.hackerearth.com/problem/algorithm/doctor-and-coins/)

Given a number $$N$$, you need to divide it into parts of size 2 and 3 only such that the number of 3 sized parts is maximum and print the maximum number of 3 sized parts.

There can be only 3 possible cases--

1.	3 evenly divides $$N$$. In this case, answer will be simply $$N/3$$.

2.	Remainder is 1 when $$N$$ is divided by 3. In this case, we can't take $$N/3$$ coins having value 3 because we will be left with value 1, which can't be exchanged. What we can do is take $$(N/3) - 1$$ coins having value 3 and take 2 coins having value 2.

3.	Remainder is 2 when $$N$$ is divided by 3. In this case, we can just take $$N/3$$ coins having value 3 and 1 coin having value 2.

[Author's solution](https://www.hackerearth.com/submission/10139208/)

---

## [Master and Challenge](https://www.hackerearth.com/problem/algorithm/master-and-challenge/)

Given two n-digit numbers A and B, you have to rearrange the digits of number B such that if we compare each corresponding digit then--

1.	Number of times corresponding digit of B is lesser is minimum. Print that minimum number.

2.	Number of times corresponding digit of A is lesser is maximum. Print that maximum number.

First sort the digits of each number individually.

For first case, start from the largest digit of B and find the largest digit of A that is smaller than or equal to that digit of B and move on to next smaller digit of B. If for a digit of B, there is no digit of A that is smaller than or equal to it, then break and store the count. The number of remaining digits of B (for which there is no digit of A smaller or equal to it) will be the answer for first case.

For second case, start from the largest digit of B and find the largest digit of A that is smaller than that digit of B and move on to next smaller digit of B. If for a digit of B, there is no digit of A that is smaller to it, then break and store the count. The number of counted digits of B (for which there is a digit of A smaller to it) will be the answer for second case.

[Author's solution](https://www.hackerearth.com/submission/10147623/)

---

## [Attack on Daleks](https://www.hackerearth.com/problem/algorithm/attack-on-daleks/)

Given $$N$$ initial points on a straight line and $$N$$ final points on the same straight line, you need to calculate the minimum sum of distances required for $$N$$ Daleks to move from given $$N$$ initial points to $$N$$ final points such that each one occupies only one position.

One can easily see that the sum of distances is minimum if we move from $$i$$th smallest initial point to the $$i$$th smallest final point. To calculate this minimum distance, just sort both initial and final points individually and take the absolute differences of corresponding points and add it to the answer.

[Author's solution](https://www.hackerearth.com/submission/10148768/)

---

## [Doctor and Portals](https://www.hackerearth.com/problem/algorithm/doctor-and-portals/)

Given a tree rooted at 1, you need to find the minimum number of edges one requires to travel to a node having a portal.

One can simply apply a DFS or BFS to calculate the distance of each node from root. After that, just print the minimum distance out of all those having a portal.

[Author's solution](https://www.hackerearth.com/submission/10153990/)

---

## [Doctor and Planets](https://www.hackerearth.com/problem/algorithm/doctor-and-planets/)

Given a series in which 1 is 1 times, 2 is 2 times, 3 is 3 times and so on, you need to calculate sum upto N terms.

Since, the value of N can only go upto $$10^5$$, one can just precompute the sum upto 0 to $$10^5$$ terms and store it in an array and answer each sum for corresponding value of $$N$$ from that array.

Here's a bonus question for you. What if value of $$N$$ is upto $$10^{18}$$?

**Hint:** sum of k times k can be written as k * k.

[Author's solution](https://www.hackerearth.com/submission/10155135/)

---

## [Defending Earth](https://www.hackerearth.com/problem/algorithm/defending-earth/)

Given $$N$$ buildings (with corresponding heights) in a straight line, there are cybermen on each of the building. For each query, you are given the index of a building (denoted by $$CURR$$), you need to calculate the sum of cybermen from that building upto the building which is just before the one that is first one on right having height greater than that of building at $$CURR$$.

First pre-compute the index of first greater building on it's right for each building and store it in an array. This can be done in $$O(N)$$ using stacks. For detailed explanation for this pre-computation, click this [link](http://www.geeksforgeeks.org/next-greater-element/).

Also, calculate the prefix sum for $$O(1)$$ retrieval of range sum.

Then, for each query print the range sum from index $$CURR$$ upto just before it's next greater building.

Overall complexity for this approach is $$O(N + Q)$$. But sadly due to weak test cases, brute force approach with complexity $$O(N^2 + Q)$$ was also working :(.

[Author's solution](https://www.hackerearth.com/submission/10226742/)