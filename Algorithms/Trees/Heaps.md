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
	- Log(N) time
	- Left child = 2(i)+1
	- Right child = 2(i) + 2
	- Max Heap is where the root of a heap is the maximum value among all nodes. Also, every parent node's value is greater than its child(s).
	- **Array representation of a complete binary tree contains the level order traversal of the tree**.
	- How does the algorithm work? 
		- Ignore leaf nodes (nodes that do not have any children)
		- Last parent node index (or last non-leaf node index= (n/2) - 1
		- have a for loop that starts from the last parent node index ((n/2) - 1) and decrement by 1 for every iteration until it reaches 0. This is to heapify every non-leaf node. 
		- Starting from the last parent node index ( the root), check to see if the left child is greater than the parent node. set a variable, largest, to left node. 
		- Check to see if the right child is greater than the largest node. if it is, set largest to the right child. 
		- Check a condition if the largest isn't the "root", Swap the parent nodes value with the largest value using a temp variable. Recursively check to see if there are any subtrees by heapifying after. 
		```Java
		public class BuildHeap {
    // To heapify a subtree rooted with node i which is
    // an index in arr[].Nn is size of heap
    static void heapify(int arr[], int N, int i)
    {
        int largest = i; // Initialize largest as root
        int l = 2 * i + 1; // left = 2*i + 1
        int r = 2 * i + 2; // right = 2*i + 2
  
        // If left child is larger than root
        if (l < N && arr[l] > arr[largest])
            largest = l;
  
        // If right child is larger than largest so far
        if (r < N && arr[r] > arr[largest])
            largest = r;
  
        // If largest is not root
        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;
  
            // Recursively heapify the affected sub-tree
            heapify(arr, N, largest);
        }
    }
  
    // Function to build a Max-Heap from the Array
    static void buildHeap(int arr[], int N)
    {
        // Index of last non-leaf node
        int startIdx = (N / 2) - 1;
  
        // Perform reverse level order traversal
        // from last non-leaf node and heapify
        // each node
        for (int i = startIdx; i >= 0; i--) {
            heapify(arr, N, i);
        }
    }
  
    // A utility function to print the array
    // representation of Heap
    static void printHeap(int arr[], int N)
    {
        System.out.println(
            "Array representation of Heap is:");
  
        for (int i = 0; i < N; ++i)
            System.out.print(arr[i] + " ");
  
        System.out.println();
    }
  
    // Driver Code
    public static void main(String args[])
    {
        // Binary Tree Representation
        // of input array
        //            1
        //         /      \
        //       3        5
        //     /   \       / \
        //  4       6  13 10
        // / \    /  \
        // 9  8  15   17
        int arr[] = {1, 3, 5, 4, 6, 13, 10, 9, 8, 15, 17};
        int N = arr.length;
        
        buildHeap(arr, N);
        printHeap(arr, N);
    }
    ```
- HeapSort
	- Takes O(NLog(N)) time
	- Steps:
		- Build a max heap
		- Swap the first and last elements of a heap
		- Reduce the array size by 1
		- heapify afterwards to maintain a heap structure
		- repeat using a for-loop
	```Java
	        // One by one extract an element from heap
	        // build a max heap then add this code 
        for (int i = N - 1; i > 0; i--) {
            // Move current root to end1
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp; 
            // call max heapify on the reduced heap
            heapify(arr, i, 0);
            // Transforms a max heap to a min heap+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        }
    }
	```

