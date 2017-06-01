---
layout: post
title:  "Heuristics #5 - Editorial"
date:   2017-03-29
author: ferbncode
---

This edition of Heuristics was [Radiohead](https://en.wikipedia.org/wiki/Radiohead) themed. Hopefully you liked it. We recommend you check out In Rainbows if you want to listen to some great music.

## [Fake Plastic Trees](https://www.hackerearth.com/problem/algorithm/fake-plastic-trees/)

### Author: [Suyash Garg](https://github.com/ferbncode)

Given the array of integers, it was required to find the minimum number of swaps to bring max element to the first index and the minimum element to the last index. The approach to solve this problem is as follows:

1. Find the max and min element. Also find their indexes. Since all numbers in the array are not distinct, the index of the max element nearest to the index 0 is to be considered. For the min element, the index closest to the end(n-1) is to be considered.

2. The answer is simply the sum of the absolute difference between the index of max element and zero and the absolute difference between the index of the min element and the last index (n-1). In cases where the indexmin < indexmax, there is a swap counted in the both cases. Thus, subtracting 1 swap in all those cases gives the correct answer.

[Author's solution](https://gist.github.com/ferbncode/2dc5b4391c14c7f9e1a064656129d722)


## [Subterranean Homesick Aliens](https://www.hackerearth.com/problem/algorithm/subterrenean-homesick-alien/)

### Author: [Suyash Garg](https://github.com/ferbncode)

Given a matrix of $$n$$x$$3$$ containing the cost to paint n stones, it was required to find the minimum cost to paint all stones such that no adjacent stones have the same color. This is a question of [Dynamic Programming](https://www.topcoder.com/community/data-science/data-science-tutorials/dynamic-programming-from-novice-to-advanced). Consider this problem for 1 stone. The answer is simply the minimum of all the three colors. For 2 stones, the answer is min((cost of painting 2 stone by red + min(cost of painting stone 1 by majenta, cost of painting stone 1 by violet)), (cost of painting stone 2 by violet + min(cost of painting stone 1 by majenta or red)) and a similar case when stone 2 is painted by majenta). Thus, this problem can be then extended to n stones. Thus:

```
   min_cost = min(dp[n-1][0], dp[n-1][1], dp[n-1][2])
```

where:

+  ```dp[n-1][0] = cost[n-1][0] + min(dp[n-2][1], dp[n-2][2])```

+  ```dp[n-1][1] = cost[n-1][1] + min(dp[n-2][2], dp[n-2][0])```

+  ```dp[n-1][2] = cost[n-1][2] + min(dp[n-2][1], dp[n-2][0])```


[Author's solution](https://gist.github.com/ferbncode/4bc06ef5d2d2c4a8f33e8106c7aaa7ca).

## [No Surprises](https://www.hackerearth.com/problem/algorithm/no-surprises/)

### Author: [Param Singh](https://github.com/paramsingh)

This was a simple ad-hoc problem with the constraints so small that the brute force approach would
work easily. All you had to do in this one was iterate through all numbers less than $$X$$, check if they satisfy the condition given in the question and keep a count.

[Author's solution](https://www.hackerearth.com/submission/7856306/)

## [Bodysnatchers](https://www.hackerearth.com/problem/algorithm/bodysnatchers/)

### Author: [Param Singh](https://github.com/paramsingh)

This was a tree problem that asked you to calculate sum of the values of nodes in the subtree of certain
nodes. Because the number of queries is too large, a simple dfs for each query will exceed time limit here.
What we need to do is precompute the answer for each node and store it in an array. This can be done with a single dfs. Then, all the queries can be answered in $$O(1)$$ time.

[Author's solution](https://www.hackerearth.com/submission/7856359/)

## [Jigsaw Falling Into Place](https://www.hackerearth.com/problem/algorithm/cheer-the-kids/)

This problem was sourced from [SPOJ](http://spoj.com/problems/ASSIGN). It is a standard problem  that involves Dynamic Programming with bitmasks. The state of the DP is a bitmask that keeps track of which puzzles have been given to children already. Then we start assigning puzzles according to this bitmask and get a count of all possible assignments.

The complexity of this solution is $$O(2^n)$$.

[Editorialist's solution](https://www.hackerearth.com/submission/7856504/)
