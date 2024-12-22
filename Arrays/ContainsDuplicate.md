# Leetcode 217 Contains Duplicate

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

## Example
```
Input: nums = [1,2,3,1]

Output: true

Explanation:

The element 1 occurs at the indices 0 and 3.
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