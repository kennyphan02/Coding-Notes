**Binary Search**

- This algorithm is used on a sorted array of n elements. 
- Divides the search interval in half. 
- Time Complexity: O(Log n)
- Steps to a binary search:
	- Sort the array in ascending order
	- set the low index to first element and high index to last element
	- set middle index to average of low and high index
	- if element at middle index is at target element, return the middle index 
	- If target element is less than the element index, set the high index to middle index-1
	- If target element is greater than the element index, set the low index to middle index+1
	- Repeat steps until element is found


```

```