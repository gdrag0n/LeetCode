Fourth
163/172 passed
```

class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        
        nums.sort()
        n=nums[-1]

        l=set(range(1, 50))
        n=set(sorted(nums))

        s= l-n
        res=sorted(list(s))
        return res[0]
```



Third
```
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        
        if len(nums)<10:
            l={1,2,3,4,5,6,7,8,9}
            n=set(sorted(nums))

            s= l-n
            res=sorted(list(s))
            return res[0]

        else:            
            nums.sort()
            n=nums[-1]

            l=set(range(1, n+2))
            n=set(sorted(nums))

            s= l-n
            res=sorted(list(s))
            return res[0]
```


Second Approach

ERROR Memory exceeded
```
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        
        nums.sort()
        n=nums[-1]

        l=set(range(1, n+2))
        n=set(sorted(nums))

        s= l-n
        res=sorted(list(s))
        return res[0]
```


First Approach

ERROR for positive values greater than 9
```
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        
        l={1,2,3,4,5,6,7,8,9}
        n=set(sorted(nums))

        s= l-n
        res=sorted(list(s))
        return res[0]

```
