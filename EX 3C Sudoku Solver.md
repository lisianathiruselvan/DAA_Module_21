# EX 3C Sudoku Solver
## DATE: 25.3.25
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. board: 9×9 Sudoku grid, where 0 represents an empty cell.

2. printBoard(board): Prints the board in a readable format.

3. isPossible(board, row, col, val): Checks if val can be placed at (row, col) without breaking Sudoku rules.

4. solve(): Recursive backtracking function that fills the board.


## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: LISIANA T
Register Number: 212222240053 
*/
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for row in range(9):
        for col in range(9):
            if board[row][col] == 0:
                for val in range(1, 10):
                    if isPossible(board, row, col, val):
                        board[row][col] = val
                        solve()
                        board[row][col] = 0
                return
    printBoard(board)
    
solve()
```

## Output:

![image](https://github.com/user-attachments/assets/2d8fb3a7-0a18-45a6-b3d0-e74b7ffa2430)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
