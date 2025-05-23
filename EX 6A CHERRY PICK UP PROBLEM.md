# EX 6A CHERRY PICK UP PROBLEM
## DATE:23.05.25
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Create dp[x1][y1][x2] where y2 = x1 + y1 - x2.
2. Initialize dp[0][0][0] = grid[0][0] if grid[0][0] != -1.
3. For k in range(1, 2n-1), loop all valid x1, x2 where y1 = k-x1 and y2 = k-x2.
4. For each dp[x1][y1][x2], take max of 4 previous moves and add cherries.
5. Return max(0, dp[n-1][n-1][n-1]).
  

## Program:
```

To implement the program for Cherry pickup problem.


Developed by: sreeja.v
Register Number:  212222230169

class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        #############    Add your code here  ############### 
        dp = [[0]*n for _ in range(n)]
        for i in range(n-1,-1,-1):
            for j in range(n-1, -1, -1):
                if i==n-1 and j==n-1:
                    dp[i][j] = grid[i][j]
                elif i==n-1:
                    dp[i][j] = grid[i][j]+dp[i][j+1]
                elif j==n-1:
                    dp[i][j] = grid[i][j]+dp[i+1][j]
                else:
                    dp[i][j] = grid[i][j]+max(dp[i][j+1], dp[i+1][j])

        return max(0,dp[0][0])+1
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output:

![Screenshot 2025-05-23 110104](https://github.com/user-attachments/assets/539ebcbf-b118-407b-8293-8c8f1466288b)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
