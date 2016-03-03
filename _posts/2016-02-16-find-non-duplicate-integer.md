---
layout: post
---
In a list of integers, there is only one that doesn’t have a duplicate, find it.

Example: 

    [1, 6, 5, 1, 5] -> 6
    
Solution (in Python):

    def singleNumber(nums):
        d = {}
        for num in nums:
            if num not in d:
                d[num] = 1
            else:
                del d[num]
        return d.keys()[0]
