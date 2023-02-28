- Picking the minimum element in the unsorted list and then putting it into the sorted list and repeating it until there are no more elements in the unsorted list
	- ![[chrome_343Urm3iEZ.png]]
	- Starting at index 0: Store the index in a Minimum variable. Compare minimum to the rest of the elements in the list indexing from `0,n-1`. If the minimum is greater than the element being compared, assign the index of the compared element to the minimum. After iterating through the array, swap the first index of the array with the minimum. Increase the index by 1 and repeat the process
	- Unsorted Array: Starting at index 1 and increasing the index by 1
	- Sorted Array: Starting at index 0 and increasing the index by 1 
- Time complexity:
	- Worst case: O(N^2)
	- Best case: O(N^2)
	- Average case: O(N^2)
```Kotlin
// Java program for implementation of Selection Sort
import java.io.*;
public class SelectionSort
{
	void sort(int arr[])
	{
		int n = arr.length;
		// One by one move boundary of unsorted subarray
		for (int i = 0; i < n-1; i++)
		{
			// Find the minimum element in unsorted array
			int min_idx = i;
			for (int j = i+1; j < n; j++)
				if (arr[j] < arr[min_idx])
					min_idx = j;
			// Swap the found minimum element with the first
			// element
			int temp = arr[min_idx];
			arr[min_idx] = arr[i];
			arr[i] = temp;
		}
	}
	// Prints the array
	void printArray(int arr[])
	{
		int n = arr.length;
		for (int i=0; i<n; ++i)
			System.out.print(arr[i]+" ");
		System.out.println();
	}
	// Driver code to test above
	public static void main(String args[])
	{
		SelectionSort ob = new SelectionSort();
		int arr[] = {64,25,12,22,11};
		ob.sort(arr);
		System.out.println("Sorted array");
		ob.printArray(arr);
	}
}
/* This code is contributed by Rajat Mishra*/


```
Advantages:
- Easy to understand
Disadvantages: