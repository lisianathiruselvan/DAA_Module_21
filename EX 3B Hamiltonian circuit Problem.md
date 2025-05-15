# EX 3B Hamiltonian Circuit Problem
## DATE: 22.3.25
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Initialize a DP table where dp[i][mask] is True if a path ends at node i covering nodes in mask.

2. Set base cases: each node alone forms a valid path (dp[i][1 << i] = True).

3. Iterate over all subsets of nodes and try extending paths to each node j.

4. Update dp[j][mask] if there is a neighbor k such that k → j is an edge and dp[k][mask without j] is True.

5. Return True if there's any path covering all nodes ending at any node.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: LISIANA T
Register Number: 212222240053  
*/
#def Hamiltonian_path(adj, N):
    
def Hamiltonian_path(adj, N):
    dp = [[False for _ in range(1 << N)] for _ in range(N)]

    for i in range(N):
        dp[i][1 << i] = True

    for i in range(1 << N):
        for j in range(N):
            if (i & (1 << j)) and any((i & (1 << k)) and adj[k][j] and j != k and dp[k][i ^ (1 << j)] for k in range(N)):
                dp[j][i] = True

    return any(dp[i][(1 << N) - 1] for i in range(N))
    
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:

![image](https://github.com/user-attachments/assets/439ed4ba-c528-4bd4-b4f2-637e505000e4)



## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
