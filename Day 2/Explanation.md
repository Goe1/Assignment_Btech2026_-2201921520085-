"Explanation for Day 2 here..." 
The given OrderedStream class is a data structure that stores ordered key-value pairs and returns a contiguous sequence of inserted values starting from the current pointer (ptr). The main goal is to ensure that values are retrieved in order when inserted.

1. Initialization (OrderedStream(int n))
The constructor initializes:
An array res of size n to store the inserted values.
A pointer ptr initialized to 0, which keeps track of the current position for ordered retrieval.
2. Insertion and Retrieval (insert(int idKey, String value))
The method inserts the given value at idKey - 1 (since idKey is 1-based but arrays are 0-based).
It then checks if the current pointer ptr is pointing to a non-null value.
If ptr is at a valid value, it continues collecting values until it encounters a null.
Finally, the contiguous list of values is returned.
3. Working of the ptr Pointer
The ptr ensures that only contiguous sequences starting from the current pointer are returned.
If an element is inserted out of order, the method does not return it until all previous elements have been inserted.

Time Complexity Analysis
The insertion operation takes O(1) time for inserting the value.
The traversal from ptr takes O(n) in the worst case (if all elements are being retrieved at once).
The overall average complexity is O(1) per insertion, making it efficient.
