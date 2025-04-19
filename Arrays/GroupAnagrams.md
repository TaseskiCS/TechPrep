# Leetcode 49 Group Anagrams

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
 def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """
        map = {} # initialize map for holding, sorted string : strs[i]
        groups = [] # return list

        for i in strs:
            key = "".join(sorted(i)) # sort current string
            if key not in map:       
                map[key] = []        
            map[key].append(i)        

        for i in map:
            groups.append(map[i])
        return groups
```

## Explanation
Initialize empty hashmap for storing our key which is the sorted word, and the current word that is an anagram to it.
Loop through list and sort each word going through, check if already in map, if not set a key to that sorted word, then append the unsorted version to it.
To return the groups just loop through the map pulling all the values and appending them into a return list.

Time complexity stems from sorting which will take O(nlogn) time and then having to go over the other characters in it's unsorted version.


## Time: O(m*n logn)
## Space: O(m*n)