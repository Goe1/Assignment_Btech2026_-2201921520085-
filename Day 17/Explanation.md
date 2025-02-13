"Explanation here..." 
Approach
There are two parts to the question

Initialising the heap
Adding and finding the kth element in the heap
First, we want to maintain the k largest elements in our heap, as we need to have the kth largest number in our heap. Also note, if we kept a max-heap we would get the largest number, while a min-heap would give the smallest of the k numbers stored in our heap. Hence, that clears up that we need a min-heap here.

Please note the "maintain the k largest elements in our heap" part, as this invariant is the heart of this and other stream related problems and will also help you avoid mistakes if you follow this religiously in your code.

Initialising
We have two scenarios here either the size of initial array is larger than k, or it is not. Based on this our approach will be as below
If it is larger initialise our min-heap with the first k elements(avoid adding one by one in a loop and use heapify function in your language)
If not, initialise with whatever number of elements are available
For the rest of the elements if there are any left (this logic is similar to handling the stream below)
	Add element to heap
	If size is disturbed(ie. more than k elements) pop an element
Complexity : Time - O(max(k, n)) for initialising k elements, O((n-k)logk) for adding the rest ~ O( max(k, n) + nlogk - klogk), Space - O(k)
Note: if you donot use heapify and add one by one - complexity will be O(max(k, n)logk) which is less optimised than the above in all possible cases. A lot of answers in discuss are using this approach still.
Handling the stream
Add the new number to heap
If the size of the heap is disturbed pop a number out
Return the minimum of the k largest numbers in our heap(ie. the kth largest one)
Complexity : Time: O(logk), Space: O(1), however we are using the heap created above