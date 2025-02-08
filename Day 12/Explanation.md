"Explanation here..." 
Use two queues: main (to hold the elements in stack order) and helper (to assist in reordering elements during the push operation).
For push(x):
Transfer all elements from main to helper.
Add the new element x to main.
Transfer all elements back from helper to main.
This ensures the most recently added element is always at the front of the main queue, simulating a stack's top.
For pop():
Simply remove and return the front element of main.
For top():
Peek at the front element of main without removing it.
For empty():
Check if main is empty.
Complexity
Time complexity:

Push operation: O(n)
The push operation involves transferring all elements between main and helper, which takes linear time relative to the number of elements in the stack.
Pop operation: O(1)
Removing the front element from a queue takes constant time.
Top operation: O(1)
Peeking at the front element of a queue takes constant time.
Empty operation: O(1)
Checking if a queue is empty takes constant time.
Space complexity:

O(n)
Two queues are used, each potentially holding up to all elements in the stack.