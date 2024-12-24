# Leetcode 1431 Kids With the Greatest Number of Candies

There are n kids with candies. You are given an integer array candies, where each candies[i] represents the number of candies the `i`th kid has, and an integer extraCandies, denoting the number of extra candies that you have.

Return a boolean array result of length n, where result[i] is true if, after giving the ith kid all the extraCandies, they will have the greatest number of candies among all the kids, or false otherwise.

Note that multiple kids can have the greatest number of candies.

## Example
```
Input: candies = [2,3,5,1,3], extraCandies = 3
Output: [true,true,true,false,true] 
Explanation: If you give all extraCandies to:
- Kid 1, they will have 2 + 3 = 5 candies, which is the greatest among the kids.
- Kid 2, they will have 3 + 3 = 6 candies, which is the greatest among the kids.
- Kid 3, they will have 5 + 3 = 8 candies, which is the greatest among the kids.
- Kid 4, they will have 1 + 3 = 4 candies, which is not the greatest among the kids.
- Kid 5, they will have 3 + 3 = 6 candies, which is the greatest among the kids.
```

## Solution
```python
 def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List:
        result = []
        for i in range(len(candies)):
            newCandyAmount = candies[i] + extraCandies

            if newCandyAmount >= max(candies):
                result.append(True)
            else:
                result.append(False)

        return result
```

## Explanation
Initialized an empty boolean array which we will store whether the `i`th kid has a greater amount of candy amongst the others. Iterate through the given `candies` and add the extra candies to the `i`th kid, if that amount is greater than all the other candies, return True, otherwise False.

Since theres 1 iteration of the candies list, the time complextity is O(n).

A result array is initialized which takes up O(n) space.

## Time: O(n)
## Space: O(n)