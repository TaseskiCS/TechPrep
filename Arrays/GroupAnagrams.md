# Leetcode 217 Contains Duplicate

Given an array of strings strs, group the anagrams together. You can return the answer in any order.

## Example
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]

Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

Explanation:

There is no string in strs that can be rearranged to form "bat".
The strings "nat" and "tan" are anagrams as they can be rearranged to form each other.
The strings "ate", "eat", and "tea" are anagrams as they can be rearranged to form each other.
```

## Solution
```python
 def containsDuplicate(self, nums: List[int]) -> bool:
        i = 0
        temp = set()
        while i < len(nums):
            if nums[i] in temp:
                return True
            else:
                temp.add(nums[i])
            i+=1

        return False
```

## Explanation
Initialize empty set, iterate through nums and compare each value to see if it's already in the set, if not add it.

Go through nums once, and check if any value is in `temp`, so O(n) + O(n) = 2*O(n), therefore time complexity is O(n).

Initialized a set which takes up O(n) space.

## Time: O(n)
## Space: O(n)