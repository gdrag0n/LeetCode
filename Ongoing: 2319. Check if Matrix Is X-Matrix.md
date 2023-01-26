# Approach 01
```
class Solution:
    def checkXMatrix(self, grid: List[List[int]]) -> bool:
        
        n=len(grid)
        d=[]        #list of diagonal elements
        for i in range(n):
            d.append(grid[i][i])
            d.append(grid[i][n-i-1])

        if n%2!=0:
            d.append(grid[n//2][n//2])
        
        for i in d:
            if i==0:
                return False
        
        for j in range(n):
            for k in grid[j]:
                if k not in d and k!=0:
                    return False
    
        return True

```
Most of the test cases were passed but I can see a better way to approach this question so I'm abandoning this approach

# Approach 2
```
class Solution:
    def checkXMatrix(self, grid: List[List[int]]) -> bool:
        
        n=len(grid)

        for i in range(n):
            if grid[i][i]==0 or grid[i][n-i-1]==0:
                return False

        if n%2!=0:
            if grid[n//2][n//2]==0:
                return False

        for j in range(n):
            grid[j].pop(j)
            grid[j].pop(n-j-2)      #ideally should be n-j-1. but since j is removed in prev command, n-2-j
            for k in grid[j]:
                if k!=0:
                    return False
    
        return True
```
Error arises when grid[j][j] occurs on left to grid[j][n-i-1]

# Approach 3
```
class Solution:
    def checkXMatrix(self, grid: List[List[int]]) -> bool:
        
        n=len(grid)

        for i in range(n):
            if grid[i][i]==0 or grid[i][n-i-1]==0:
                return False

        if n%2!=0:
            if grid[n//2][n//2]==0:
                return False

        for j in range(n):
            for k in grid[j]:
                if index(k)==j or index(k)==(n-j-1):
                    continue
                else:
                    if k!=0:
                        return False
        return True
```
The error still arises.
