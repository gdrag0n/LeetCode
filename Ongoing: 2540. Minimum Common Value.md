```
class Solution:
    def getCommon(self, nums1: List[int], nums2: List[int]) -> int:

        #min(nums1 and nums2)

        nums1.sort()
        nums2.sort()

        for i in nums1:
            if i in nums2:
                return i
        
        else:
            return -1
```

time limit exceeded

```

```
