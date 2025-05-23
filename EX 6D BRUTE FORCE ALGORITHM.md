# EX 6D BRUTE FORCE ALGORITHM
## DATE:23.05.25
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.
## Algorithm
1. Let n = length of main string, m = length of substring.
2. Loop i from 0 to n - m.
3. For each i, check if main[i : i+m] == pattern.
4. If match found, return i (starting index).
5. If no match after loop, return -1.
  

## Program:
```

To implement the program using brute force method of searching for the given substring in the main string.


Developed by: sreeja.v
Register Number:212222230169  
import re
def match(string,sub):
    pattern=re.compile(str2)
    r=pattern.search(str1)
    while r:
        print("Found at index {}".format(r.start()))
        r=pattern.search(str1,r.start()+1)
str1=input()
str2=input()


```

## Output:

![Screenshot 2025-05-23 110648](https://github.com/user-attachments/assets/23eaf889-a1ce-490e-9bae-48238266afac)


## Result:
Thus the above program was executed successfully for searching the substring at respective index.
