## Fake Plastic Trees:

Given the array of integers, it was required to find the minimum number of swaps to bring max element to the first index and the minimum element to the last index. The approach to solve this problem is as follows:

1. Find the max and min element. Also find their indexes. Since all numbers in the array are not distinct, the index of the max element nearest to the index 0 is to be considered. For the min element, the index closest to the end(n-1) is to be considered.

2. The answer is simply the sum of the absolute difference between the index of max element and zero and the absolute difference between the index of the min element and the last index (n-1). In cases where the indexmin < indexmax, there is a swap counted in the both cases. Thus, subtracting 1 swap in all those cases gives the correct answer.

