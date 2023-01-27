**Heap Data Structure**
- ![[Pasted image 20230125122611.png]]
- Operations:
	- Heapify: Process to rearrange elements to main property of a heap data structure 
			- Done when a certain node creates an imbalance in the heap due to operations on that node.
	- Insertion: Inserting an element in existing heap time O(Log N)
	- Deletion: Deleting the top element of the heap (highest priority element), then organizating the heap then it returns the element that was deleted with time complexity O(Log N)
	- Peek: find the most prior element in the heap (max or min element for max and min heap)
- Two types of heap data structures:
	- Max-Heap
		- The root node must be the greatest among all nodes. Every value of a parent node is also greater than its child nodes 
	- Min-Heap
		- The root node must be the smallest among all nodes. Every value of a parent node is also smaller than its child smalls 

- Build MaxHeap Algorithm
	- Max Heap is where the root of a heap is the maximum value among all nodes. Also, every parent node's value is greater than its child(s).
	- Array representation of a complete binary tree contains the level order traversal of the tree.
	- How does the algorithm work? 
		- Ignore leaf nodes (nodes that do not have any children)
		- Last parent node index (or last non-leaf node index= (n/2) - 1