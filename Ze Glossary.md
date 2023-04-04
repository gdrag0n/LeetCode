### 520
s is a string here
1. s.upper() or s.lower() : transforms s into an entirely uppercase or lowercase version of itself
2. s.isupper() or s.islower() : Bool that checks if all elements of s are uppercase or lwoercase
3. s.istitle() : bool that cheks if s[0] is in uppercase and the rest are in lowercase or not


### 2164
used in #922
sorting all even indices and all odd indices separately
nums[::2}=sorted(nums[::2])
nums[1::2]=sorted(nums[1::2], reverse=True)
