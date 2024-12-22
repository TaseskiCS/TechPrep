# Leetcode 121 Best Time to Buy and Sell Stock

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

## Example
```
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```

## Solution
```python
 def maxProfit(self, prices: List[int]) -> int:
        left = 0
        right = 1
        maxProfit = 0
        while right < len(prices):
            if prices[left] < prices[right]:
                profit = prices[right] - prices[left]
                if profit > maxProfit:
                    maxProfit = profit
            else:
                left = right
            right +=1
        return maxProfit
```

## Explanation
Sets up left and right pointer, checks if the price at index of left, is less than the price of index of right, we want to see our profit so far, so we subtract the price at left from the price of right and do a check to see if that profit is greater than our starting maxProfit value (0), which it is so we set the new profit to that. Lastly increment right pointer.

If the price at the index of left is NOT less than the price of index of right, then we simply dont want to "buy" that stock yet so we shift our left pointer to the rights location, then we increment the right pointer.

We traverse through the full size list of "prices" once so that makes our time complexity O(n), and we don't use any extra space/memory so that complextity is O(1).

## Time: O(n)
## Space: O(1)