# Leetcode 125 Valid Palindrome

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

## Example
```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

## Solution
```python
 def isPalindrome(self, s: str) -> bool:
        temp = ''
        valid = True
        i=0
        if len(s) == 0:
            valid = True

        for char in s:
            if char.isalnum():
                temp+=char.lower()

        left = 0
        right = len(temp)-1

        while left < right:
            if temp[left] != temp[right]:
                valid = False
            left +=1
            right -=1
        return valid
```

## Explanation
Initialize an empty String, check corner case for if `s` is empty, loop through the s and filter out everything except alpha numericals, then set a left pointer, and a right pointer, and increment the left, decrement the right, check values until they cross over and compare.

We iterate through `s` once, and then iterate through `temp` once, so that would be O(n) + O(n) = 2*O(n) which is O(n) time complexity.

When we initialize an empty string thats opening potential usage of it, so it's space/memory complexity is O(n).

## Time: O(n)
## Space: O(n)