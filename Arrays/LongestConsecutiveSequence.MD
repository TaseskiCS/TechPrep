# Leetcode 128 Longest Consecutive Sequence

Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

You must write an algorithm that runs in O(n) time.

## Example
```
Input: nums = [100,4,200,1,3,2]
Output: 4
Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.
```

## Solution
```python
 def longestConsecutive(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        streak = set(nums)
        longest_sequence = 0
        for i in streak:
            # check if start of sequence
            check = i - 1 #check if has no left neighbour
            if check not in streak:
                length = 0 # start of sequence
                while (i + length) in streak: # checks if our current + length is in the set eg. 2 + length(1) = 3, in the set
                    length += 1
                longest_sequence = max(length, longest_sequence) #take the longest sequence from set and current longest
                
        return longest_sequence
```

## Explanation
Convert streak to set, allowing O(1) lookup on values.

Go through the streak and check if each element has a left neighbour, because conceptually the start of a sequence should not have a left neighbour thats 1 less than its value in the set, if we do find that its in the set then we will just move forward and save it for a future iteration when we find the start.

After find the start of the sequence, we initialize our length to 0 and check our value from `i` + `length` to see if it's in our set, which for example, if we have 2, we want to check if 3 is in the set, and for 3 check if 4 is in, and length keeps incrementing each iteration so it keeps up.

Last we take the max from our current `length` and our existing `longest_sequence` and return it.

Time complexity is O(n) since we just check over the values in a `SET` with constant lookup, and space complexity is O(n) because of the conversion.

## Time: O(n)
## Space: O(n)