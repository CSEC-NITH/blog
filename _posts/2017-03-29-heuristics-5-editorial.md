## Fake Plastic Trees:

Given the array of integers, it was required to find the minimum number of swaps to bring max element to the first index and the minimum element to the last index. The approach to solve this problem is as follows:

1. Find the max and min element. Also find their indexes. Since all numbers in the array are not distinct, the index of the max element nearest to the index 0 is to be considered. For the min element, the index closest to the end(n-1) is to be considered.

2. The answer is simply the sum of the absolute difference between the index of max element and zero and the absolute difference between the index of the min element and the last index (n-1). In cases where the indexmin < indexmax, there is a swap counted in the both cases. Thus, subtracting 1 swap in all those cases gives the correct answer.

Find code in C++ [here](https://gist.github.com/ferbncode/2dc5b4391c14c7f9e1a064656129d722)


## Subterranean Homesick Aliens

Given a matrix of nx3 containing the cost to paint n stones, it was required to find the minimum cost to paint all stones such that no adjacent stones have the same color. This is a question of [Dynamic Programming](). Consider this problem for 1 stone. The answer is simply the minimum of all the three colors. For 2 stones, the answer is min((cost of painting 2 stone by red + min(cost of painting stone 1 by majenta, cost of painting stone 1 by violet)), (cost of painting stone 2 by violet + min(cost of painting stone 1 by majenta or red)) and a similar case when stone 2 is painted by majenta). Thus, this problem can be then extended to n stones. Thus:

min_cost = min(dp[n-1][0], dp[n-1][1], dp[n-1][2])
where:
dp[n-1][0] = cost[n-1][0] + min(dp[n-2][1], dp[n-2][2])
dp[n-1][1] = cost[n-1][1] + min(dp[n-2][2], dp[n-2][0])
dp[n-1][2] = cost[n-1][2] + min(dp[n-2][1], dp[n-2][0])

Find c++ implementation [here](https://gist.github.com/ferbncode/4bc06ef5d2d2c4a8f33e8106c7aaa7ca).

