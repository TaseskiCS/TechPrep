# Leetcode 347 Top K Frequent Elements

Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

## Example
```
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
```

## Solution
```python
map = {}
        for i in nums:
            if i not in map:
                map[i]= 1
            map[i]+=1

        freq = []
        for key, val in map.items():
            freq.append([val, key])
        freq.sort()

        elements = []
        i = 0
        while i < k:
            elements.append(freq.pop()[1])
            i+=1
        return elements
```

## Explanation
Initialize map to store our frequencies of each integer.

Loop through our items in the map and append each pair to our ``freq`` list where we sort it in order.

Pop the elements up to `k` amount and append them to return list.

Time complexity is O(nlogn) due to the sorting of elements.

Space complexity is O(n)

## Time: O(n*logn)
## Space: O(n)