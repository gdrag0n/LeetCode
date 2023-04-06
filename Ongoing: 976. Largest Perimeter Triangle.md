```
import itertools

class Solution:
    def largestPerimeter(self, nums: List[int]) -> int:
        
        ss=list(itertools.combinations(nums,3))     #list of sets of three sides
        l=[]    #list of perimeters
        max=0
        for i in ss:    #checking for each ss
            p=sum(i)
            for j in i:         #changed from a,b,c = p-2*i[0,1,2]
                if p-2*j>0:
                    z= True     #z=z and a and b and c
                else:
                    z= False
                    break
                

            if z and p>max:     #changed from list
                max=p

        return max
```
