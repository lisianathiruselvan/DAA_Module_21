# EX 3D Pattern Matching
## DATE: 29.3.25
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. Get lengths of text s1 and pattern s2.

2. Loop through each index i in s1 from 0 to len(s1) - len(s2).

3. For each i, compare characters of s1 and s2 one by one.

4. If all characters match, return starting index i.

5. If no match found, return -1.


## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: LISIANA T
Register Number: 212222240053
*/
def BF(s1,s2):
    len_s1 = len(s1)
    len_s2 = len(s2)

    for i in range(len_s1 - len_s2 + 1):
        j = 0
        while j < len_s2 and s1[i + j] == s2[j]:
            j += 1
        if j == len_s2:
            return i

    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)


```

## Output:
![image](https://github.com/user-attachments/assets/8e1e21c7-a17c-4d9d-ab78-8ebce8339c31)



## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
