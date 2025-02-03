"Explanation here..." 
Maintain a list of cumulative products (products) where each element represents the product of all numbers added so far.
For each number added:
Multiply it with the last cumulative product and store the result.
If the number is 0, reset the list because any product involving 0 will always be 0.
When querying the product of the last k numbers, divide the current cumulative product by the product that represents the position just before the last k numbers.
Complexity
Time complexity:
add(num): O(1) per insertion.
getProduct(k): O(1) for retrieval by accessing the cumulative product list.

Space complexity:
O(n), where n is the number of elements added (for storing cumulative products).