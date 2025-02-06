"Explanation here..." 
Here are some points to notice

To get Rid of TLE we do % of num with w * 2 + h * 2 - 4 because we have to travel through perimeter of the given grid and after travel w * 2 + h * 2 - 4 we will reach at the same position.
if you wondered why we subtract 4 from w * 2 + h * 2 if we simply do n*m we will travel all the corner edges 2 times so to manage this we have to subtract 4 from w * 2 + h * 2 - 4.
In case your solution passes 140 test case and you didn't find the reason why your code fails .
Dry Run This test case
["Robot","getPos","getDir","move","getDir","getPos"]
[[2,3],[],[],[24],[],[]]
in the beginning robot faces "East" at (0, 0),
but next time, when it comes to (0, 0) it should face "South"