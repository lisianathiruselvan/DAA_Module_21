# EX 3A Knight Tour & Count Path
## DATE: 18.3.25
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1. Initialize movement options for the knight (8 possible moves) and a queue for BFS traversal.

2. Start BFS from the knight’s initial position and mark it as visited.

3. Iterate using BFS, exploring all valid and unvisited knight moves from the current cell.

4. Check if the target is reached at each step; if so, return the number of moves (distance).

5. Continue BFS until the target is found or the queue is empty, returning infinity if unreachable.

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: LISIANA T
Register Number:  212222240053
*/
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
     
    dx = [-2, -1, 1, 2, -2, -1, 1, 2]
    dy = [-1, -2, -2, -1, 1, 2, 2, 1]

    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))

    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True

    while len(queue) > 0:
        curr = queue.pop(0)

        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist

        for i in range(8):
            x = curr.x + dx[i]
            y = curr.y + dy[i]

            if isInside(x, y, N) and not visited[x][y]:
                visited[x][y] = True
                queue.append(cell(x, y, curr.dist + 1))

    return float('inf')
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```

## Output:
![image](https://github.com/user-attachments/assets/9d6cafb6-5b7a-4917-b389-43d0f186bafd)



## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
