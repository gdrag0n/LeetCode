# Approach 01

I don't want to pursue the question by making lists, but that is the only easy approach in my mind at the moment so here's a solution using that.
```
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        
        l=[]
        for i in range(c//2+2):     #c//2+1 for c=5, +2 for c=1
        
        for j in l:
            for k in l:
                t= j+k==c
                
            if t:
                    break
                
        return t            
```

error: c=1000


# Approach 02

Upon trying to gain more understanding of the question, there were two things I could understand needed a change:
1. if i * i>c:
      break
   because going any further into the loop will be futile
2. range(c//2+2) needs to change
  I wanted to change that since the very beginning, but upon some observation, I was able to incorporate it as well
  
  initially i made changes to the for loop in the following way to bring the code closer to accuracy
```
        l=[]
        for i in range(c//2+2):
            if i*i<=c:
                l.append(i*i)
```
  This in turn gave me the following idea:
  
  c=1 = 1*1 + 0*0
  sqrt(1)=1
  need to traverse up to i=1
  
  c=29 = 2*2 + 5*5
  sqrt(29)=5.38
  technically need to traverse up to i=5
  
  c=100 = 6*6 + 8*8
  sqrt(100)=10
  need to traverse up to i=8
  
  c=265 = 11*11 + 12*12
  sqrt(265) = 16.27
  need to traverse up to i=12
  
  c=1000 = 10*10 + 30*30
  sqrt(1000)= 31.6
  need to traverse up to i=30
  
  this makes sqrt(c) a better measure
  though both are the same, in essence, cause of break statement
  
```
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        
        l=[]
        for i in range(int(sqrt(c))+1):
            l.append(i*i)
        
        
        for j in l:
            for k in l:
                t= j+k==c
                
            if t:
                    break
                
        return t
```
I faced errors for c=1000
Realized that i missed out on checking for each value of k, which is necessary, hence addition of another if statement inside the inner for loop
the outer if statement still remains to exit the nested loop using break if the condition satisfies
tried making the solution more precise in for loops

```
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        
        l=[]
        s=int(sqrt(c))
        for i in range(s+1):
            l.append(i*i)
        
        for j in range(s+1):
            for k in range(j,s+1):
                t= l[j]+l[k]==c

                if t:
                    break
                
            if t:
                break
                
        return t
```

exceeds the time limite for c = 999999999
i must find a better approach


# Approach 03
```
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        

        s=int(sqrt(c))

        for j in range(s+1):
            for k in range(j,s+1):
                t= j*j+k*k==c

                if t:
                    break
        
            if t:
                break
                
        return t
```
Same issue

# Approach 04
```
l=[]
s=sqrt(c)

```

