# EX 6B KNAPSACK PROBLEM
## DATE:23.05.25
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Create a 2D dp table of size (n+1) x (W+1), initialized to 0.
2. Loop i from 1 to n (number of items).
3. Loop w from 1 to W (total weight capacity).
4. If weight[i-1] <= w, set dp[i][w] = max(dp[i-1][w], dp[i-1][w-weight[i-1]] + value[i-1]).
5. Else, set dp[i][w] = dp[i-1][w]. Final result is dp[n][W].
  

## Program:
```

To implement the program for 0/1 knapsack problem.


Developed by: sreeja.v
Register Number: 212222230169

def knapSack(W, wt, val, n):
    if n == 0 or W == 0 :
        return 0
    if (wt[n-1] > W):
        return knapSack(W, wt, val, n-1)
    else:
        return max(val[n-1] + knapSack(W-wt[n-1], wt, val, n-1), knapSack(W, wt, val, n-1))

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:

![Screenshot 2025-05-23 110307](https://github.com/user-attachments/assets/56184d92-3f72-4fd3-b830-b8c51b762d4d)


## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
