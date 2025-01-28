"# Explanation for Day 1" 
The grid array is initialized to hold the input grid.
The neighborSum constructor takes a 2D array as input and initializes the class variable grid with this array.

//help(int value)
This method finds the indices (i, j) of the specified value in the grid.
It iterates over each element of the grid. When it finds the value, it stores the indices in the instance variables i and j.
The method stops searching once the value is found.

//adjacentSum(int value)
This method calculates the sum of adjacent neighbors of the specified value.
After finding the position of value using the help method, it checks and sums the values of the top, bottom, left, and right neighbors if they exist.
if (i != 0) checks if the top neighbor exists.
if (j != 0) checks if the left neighbor exists.
if (i != grid.length - 1) checks if the bottom neighbor exists.
if (j != grid[i].length - 1) checks if the right neighbor exists.

//diagonalSum(int value)
This method calculates the sum of diagonal neighbors of the specified value.
After finding the position of value using the help method, it checks and sums the values of the top-left, top-right, bottom-left, and bottom-right neighbors if they exist.
if (i != 0 && j != 0) checks if the top-left neighbor exists.
if (i != 0 && j != grid[i].length - 1) checks if the top-right neighbor exists.
if (i != grid.length - 1 && j != 0) checks if the bottom-left neighbor exists.
if (i != grid.length - 1 && j != grid[i].length - 1) checks if the bottom-right neighbor exists.

Time Complexity
Initialization: (O(1))
Finding the Position (help method): (O(n^2))
Sum Calculations: (O(1))