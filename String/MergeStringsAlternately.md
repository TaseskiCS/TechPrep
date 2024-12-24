# Leetcode 1768 Merge Strings Alternately
You are given two strings word1 and word2. Merge the strings by adding letters in alternating order, starting with word1. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return the merged string.

## Example
```
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
```

## Solution
```python
 def mergeAlternately(self, word1: str, word2: str) -> str:
        merged = ""
        i = 0
        while i < len(word1) or i < len(word2):
            if i < len(word1):
                merged += word1[i]
            if i < len(word2):
                merged += word2[i]
            i+=1
        return merged
```

## Explanation
Initialize an empty string to store merged elements from each string, iterate through `word1`'s and `word2` and simutaniously add each element `i` goes over to merged while checking if `i` has not reached the end of the string, and if it does, it continues going through the other.

Since there is one iteration per string, the time complexity is O(n).

Since theres an empty string which we opened to store our merged elements, it takes up O(n) space/memory.
## Time: O(n)
## Space: O(n)