# Leetcode 242 Valid Anagram

Given two strings s and t, return true if t is an 
anagram
 of s, and false otherwise.

## Example
```
Input: s = "anagram", t = "nagaram"

Output: true
```

## Solution
```python
 def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        sMap = {}
        tMap = {}
        # build hash maps for each str
        for i in range(len(s)):
            sMap[s[i]] = 1 + sMap.get(s[i], 0) # get: built in map method, default return is 0 if s[i] DNE 

            tMap[t[i]] = 1 + tMap.get(t[i], 0) # ^^^^
        for j in sMap:
            if sMap.get(j, 0) != tMap.get(j, 0): 
                return False
            
        return True
```

## Explanation
Initialize 2 empty hash maps, one designated for the `s` characters, and the other for the `t` characters. Insert each value into the maps and add the occurences. Loop through the map and compare if the value at each index is the same, if not return False, else, it's an anagram.

Looping through S and then through t, we only go through each one time, so time complexity is O(n).

We initialize 2 hashmaps which each take up n space, so O(n) + O(n) = 2*O(n), therefore space/memory complexity is O(n).
## Time: O(n)
## Space: O(n)