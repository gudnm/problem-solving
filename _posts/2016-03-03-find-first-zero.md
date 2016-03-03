---
layout: post
---
Given an array that starts with 0..n number of 1's and ends with 1..m number of 0's, find the index of the first 0. (Based off [First Bad Version on LeetCode](https://leetcode.com/problems/first-bad-version/))

Example

    [1, 1, 1, 1, 1, 0, 0] => 5

Solution (in Python):

	def firstZero(a):
	    if a[0] == 0:
	        return 0
	    return fz(a, 0, len(a) - 1)
	    
	def fz(a, start, end):
	    if start == end - 1:
	        return end
	    m = start + (end - start) / 2
	    if a[m] == 0:
	        return fz(a, start, m)
	    else:
	        return fz(a, m, end)