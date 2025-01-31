"Explanation here..." 

Data Representation:
Use a fixed-size array (byte[]) to represent numbers from 1 to 1000.
Each index in the array corresponds to a number, with 0 indicating the number is available and 1 indicating it is removed.
popSmallest:
Start from the current minIndex, which tracks the smallest available number.
Find the first available number (0) and mark it as removed (1).
Update minIndex to skip over removed numbers in future calls.
addBack:
Mark the given number as available (0) in the array.
Update minIndex if the added number is smaller than the current smallest.

Complexity

Time complexity:
1. popSmallest: On average, this operation is O(1) since minIndex avoids unnecessary iterations.
2. addBack: Always O(1).
Space complexity:
1. O(1) as we use a fixed-size array.
