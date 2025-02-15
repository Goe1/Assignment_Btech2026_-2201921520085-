"Explanation here..." 
Approach
If no seats are occupied sit at 0
Else find all compute the mid point between every consecutive occupied seat and check if distance is max or not.
If there is an elemnt already at position 0, the next round of seating should be at position N-1.
Complexity
Time complexity:
Iteration for each position takes : O(m) where m is size of occupied seats
And then we add the element to seats set. 0(log m).
So total: O(m+log(m))

Space complexity:
O(m) where m is total occupied seats