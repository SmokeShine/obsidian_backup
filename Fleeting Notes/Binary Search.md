202510171526
Status: #idea
Tags: [[Algorithms]]

# Binary Search

- Peak index 
	- mid and mid+1 to check which side of slope we are
- Perfect Square 
	- Same as binary search. if mid * mid == number, then return, else left+ 1, right - 1
	- Possibility of infinite loop
- Sqrt(x)
	- Same as perfect square, but we don't need exact match 
- Is subsequence - s,t
	- Two pointer
	- Binary search
		- Put longer t into dict
			- { char : list_indices }
				- list_indices is sorted
					- we can apply binary search here
			- check if each char in s has previous index > index of list_indices
				- same left,right
- Number of negative values in array
	- Search for first negative in the array
		- then count the len in O(1) after left < right breaks
- Search in rotated array
	- Left < target < mid means search left
	- else right
- Minimum in Rotated Sorted Array
	- left < mid, then min is left and search on mid till right
	- do the same logic for right
- Capacity To Ship Packages Within D Days
	- lower bound is max(weight)
	- upper bound is sum(weight)
	- do binary search between these ranges and see if it is feasible
	- if it is feasible, reduce right
		- else, increase left
---
# References

1. 