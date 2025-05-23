# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1. Let dp[mask][u] = min cost to reach city u with visited cities as mask.
2. Initialize dp[1<<0][0] = 0 (start at city 0 with only city 0 visited).
3. For all masks, and for each current city u in mask:
4. For all next cities v not in mask:
5. Update dp[mask | (1<<v)][v] = min(dp[mask | (1<<v)][v], dp[mask][u] + cost[u][v])
   

## Program:
```

To implement the program for TSP.


Developed by: sreeja.v
Register Number: 212222231069 

from sys import maxsize
from itertools import permutations
V = 4
def travellingSalesmanProblem(graph, s):
    vertex =[]
    for i in range(V):
        if i !=s:
            vertex.append(i)
    min_path = maxsize
    next_permutation = permutations(vertex)
    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)
        
    return min_path
if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:
![Screenshot 2025-05-23 110505](https://github.com/user-attachments/assets/709f0ad3-ddfb-4b41-895b-3ae85578eedb)



## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
