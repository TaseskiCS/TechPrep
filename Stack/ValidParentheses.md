# Leetcode 20 Valid Parentheses

You are given a string s consisting of the following characters: '(', ')', '{', '}', '[' and ']'.

The input string s is valid if and only if:

Every open bracket is closed by the same type of close bracket.
Open brackets are closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.
Return true if s is a valid string, and false otherwise.



## Example
```
Input: s = "[]"

Output: true
```

## Solution
```python
 def isValid(self, s: str) -> bool:
        open_brackets = ["[", "{", "("]
        stack = []
        for i in s:
            if i in open_brackets:
                stack.append(i)
            else:
                if len(stack) == 0:
                    return False
                if i == '}':
                    if stack.pop() != '{':
                        return False
                elif i == ']':
                    if stack.pop() != '[':
                        return False
                elif i == ')':
                    if stack.pop() != '(':
                        return False
        if len(stack) != 0:
            return False

        return True
```

## Explanation
Initialize an open_brackets list to define our brackets, define a stack.
Loop through the string `s` and check if `i` is in `open_brackets`, if it is push onto the stack. Otherwise it must be the closing bracket so conditionally check each possibility and if the value popped off the stack doesn't match then return False.
## Time: O(n)
## Space: O(n)