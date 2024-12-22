# Leetcode 1 Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

## Example
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

## Solution
```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
        temp = {} 
        for k, v in enumerate(nums): 
            complement = target - v  
            if complement in temp:
                return [temp[complement], i]
            temp[num] = k
```

## Explanation
Assigns each key to a value and checks if the difference between the target and the current value is in the hashmap, which if it is, then that would mean the current value + value in the map would equal the target, since each difference is unique in the map. We iterate over the "nums" list one time, which means the time complexity is O(n). Theoretically we could add each value from "nums" to "temp" so the space complexity is also O(n).

## Time: O(n)
## Space: O(n)