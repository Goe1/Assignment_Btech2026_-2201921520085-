"Explanation here..." 
Approach
1>Prefix Sum Array:
Precompute the cumulative sum for the input array nums and store it in a prefix sum array (prefixA).
Each element in prefixA at index i stores the sum of elements from index 0 to i in the original array.

2>Range Sum Calculation:

For any subarray defined by [left, right]:
If left == 0, the sum is simply prefixA[right].
Otherwise, the sum is calculated as:

prefixA[right]−prefixA[left−1]
This subtracts the cumulative sum of elements before left from the cumulative sum up to right.

Complexity
Time complexity:
Constructing the prefix sum array takes O(n) time, where n is the length of the input array.
Each query to calculate the range sum takes O(1) time.
Space complexity:
O(n)