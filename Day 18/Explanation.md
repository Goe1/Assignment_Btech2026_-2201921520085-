"Explanation here..." 
Note 1
Using a priority queue (heap) would have had better complexity (O(n) initialization, O(log n) upload and O(1) longuest) but in Java implementation, removing from a priority queue is O(n) instead of O(log n).

Note 2
This not the optimal solution, the optimal one is the HashSet/array one. However one advantage of the tree solution, is that the worst case of any upload() call is O(log n) while for the HashSet/array the worst case of one call is O(n) (but O(1) amortized).