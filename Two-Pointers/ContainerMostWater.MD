# Leetcode 11 Container With Most Water

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

## Example
```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

## Solution
```python
 def maxArea(self, heights: List[int]) -> int:
        result = 0
        l = 0
        r = len(heights) - 1
        while l < r:
            area = (r-l) * min(heights[l], heights[r])
            result = max(result, area)
            if heights[l] < heights[r]:
                l += 1
            else:
                r-= 1
        return result
```

## Explanation
Set a left pointer `l` to the start of the `heights` list and right pointer `r` to the end of it, and while they haven't met yet, take the area from the rectangle that is made with the pointers as sides, and set our new max area. Based off the heights from each pointer, we take our minimum pointer and move it towards the greater pointer, hoping to find another height that will make a greater area.

## Time: O(n)
## Space: O(1)