# Approach 01
```
# The isBadVersion API is already defined for you.
# def isBadVersion(version: int) -> bool:

class Solution:
    def firstBadVersion(self, n: int) -> int:

        while isBadVersion(n)==True:
            n=n-1

        while isBadVersion(n)==False:
            n=n+1

        return n    
```

# Approach 02
```
# The isBadVersion API is already defined for you.
# def isBadVersion(version: int) -> bool:

class Solution:
    def firstBadVersion(self, n: int) -> int:

        if isBadVersion(n)==True:
            while isBadVersion(n)==True:
                n=n-1
            return n+1

        else:
            while isBadVersion(n)==False:
                n=n+1
            return n
```

# Approach 03
```
```
