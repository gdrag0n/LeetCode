# Solution
# Approach 01

I do not plan to use three for loops.
The only way that can be implemented in my opinion would be to find the third value in nums instead, since we already know what sets we are looking for and what condition must be satisfied for the same.

*Problem outline:<br>
a=nums[i]<br>
b=nums[j]<br>
c=nums[k]<br>
c=-(a+b) for a+b+c=0 to satisfy<br>
if c is in nums, and its index is not same as a and b, its value is acceptable*<br>

```
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:

        l=[]
        n=len(nums)
        for i in range(n):
            for j in range(i+1,n):
                a=nums[i]
                b=nums[j]
                c=-(a+b)
                if c in nums:
                    p=nums.index(c)
                    if p!=i and p!=j:
                        l.append(sorted([a,b,c]))
                        #l=[[-1,0,1],[-1,0,1],[-1,-1,2],[-1,0,1],[-1,0,1],[-1,0,1],[-1,-1,2]]
```
### Duplicate Removal

<strong>dictionary</strong>

```
l=list(dict.fromkeys(l)) 

```
Since List is not hashable, does not remove duplicates.<br>
<br>
<br>

<strong>if + remove()</strong>
```
        for i in l:
            if l.count(i)>1:
                l.remove(i)
        
        return l
```
nums: [-1,0,1,2,-1,-4]<br>
Expected Output: [[-1,-1,2],[-1,0,1]]<br>
Output: [[-1,0,1],[-1,0,1],[-1,0,1],[-1,-1,2]]<br>
<br>
<br>

<strong>for + remove()</strong>
```
        
        for i in l:
            for j in range(l.count(i)-1):
                l.remove(i)
        
        return sorted(l)
```
nums = [-1,0,1,2,-1,-4,-2,-3,3,0,4]<br>
146 / 312 testcases passed<br>
Output:<br>
[[-1,-1,2],[-1,-1,2],[-3,1,2],[-1,0,1],[-4,1,3],[-2,-1,3],[-2,0,2],[-3,-1,4],[-3,0,3],[-4,0,4]]<br>
Expected:<br>
[[-4,0,4],[-4,1,3],[-3,-1,4],[-3,0,3],[-3,1,2],[-2,-1,3],[-2,0,2],[-1,-1,2],[-1,0,1]]<br>




To understand the issue more, I decided to implement the problem till before duplicates are removed.<br>
```
l=
[[-4,0,4],[-4,0,4],[-4,0,4],[-4,0,4],[-4,0,4],[-4,1,3],[-4,1,3],[-4,1,3],
[-3,-1,4],[-3,-1,4],[-3,-1,4],[-3,-1,4],[-3,-1,4],[-3,0,3],[-3,0,3],[-3,0,3],[-3,0,3],[-3,0,3],[-3,1,2],[-3,1,2],[-3,1,2],
[-2,-1,3],[-2,-1,3],[-2,-1,3],[-2,-1,3],[-2,-1,3],[-2,0,2],[-2,0,2],[-2,0,2],[-2,0,2],[-2,0,2],
[-1,-1,2],[-1,-1,2],[-1,0,1],[-1,0,1],[-1,0,1],[-1,0,1],[-1,0,1],[-1,0,1],[-1,0,1],[-1,0,1]]
```
[-1,-1,2] gets repeated<br>
Understanding the code:<br>
```
i=[-1,-1,2]
l.count(i)=2
j in range(1):
    l.remove(i)
```
i is expected to be removed once for j=0, but it is not
Therefore, using another approach to get rid of duplicates to give the solution above
<br>

<br>

<strong>temporary list h</strong>
```


        h=[]            #list of unique triads
        for i in l:
            t= i in h
            if not t:
                h.append(i)
        
        return sorted(h)

```
Time Limit Exceeded<br>
<br>

<br>

<strong>set</strong>
```
        l=set(map(tuple, l))
```
Time Limit Exceeded<br>
I believe the issue lies in the approach towards solving the question.
<br>

<br>


# Approach 02
*Problem outline:<br>
a=nums[i]<br>
b=nums[j]<br>
c=nums[k]<br>
<br>
*<br>
```

```
