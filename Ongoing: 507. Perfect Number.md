# Approach 1
```
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:

        l=[]

        for i in range(1,num):
            if num%i==0:
                l.append(i)
            
        if num==sum(l):
            return True
        else:
            return False
```
Error: Runtime


```
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:

        s=0
        for i in range(1,num):
            if num%i==0:
                s=s+i
            
        if num==s:
            return True
        else:
            return False
```
Error: Runtime

```

```
