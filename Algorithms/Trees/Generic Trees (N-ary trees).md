- Generic trees are a collection of nodes where each node contains multiple references to its children
	- Properties:
		- Many children at every node
		- Number of nodes for each node is not known in advance
- First child, next sibling representation of a n-ary tree
	- First child, next sibling is treated as a binary representation 
	- Rather than having pointers pointing to every child, Only one pointer is pointed to the first child in a tree then pointers pointed to the next siblings. 
		- How is this different than a typical N-ary tree?
			- Memory allocation is reduced. With a typical N-ary tree, new unique node pointers have to be created in order for the parent to point to the children nodes. 
			- First child, next sibling representation utilizing a sibling node so that whenever the parent has a new child, the parent can use the sibling pointer to point to a new memory address.
	- ![[Pasted image 20230216193611.png]]
	```Java
	// Java program to create a tree with left child
// right sibling representation.
class GFG {
	
	static class NodeTemp
	{
		int data;
		NodeTemp next, child;
		public NodeTemp(int data)
		{
			this.data = data;
			next = child = null;
		}
	}
	
	// Adds a sibling to a list with starting with n
	static public NodeTemp addSibling(NodeTemp node, int data)
	{
		if(node == null)
			return null;
		while(node.next != null)
			node = node.next;
		return(node.next = new NodeTemp(data));
	}
		
	// Add child Node to a Node
	static public NodeTemp addChild(NodeTemp node,int data)
	{
		if(node == null)
			return null;
	
		// Check if child is not empty.
		if(node.child != null)
			return(addSibling(node.child,data));
		else
			return(node.child = new NodeTemp(data));
	}

	// Traverses tree in depth first order
	static public void traverseTree(NodeTemp root)
	{
		if(root == null)
			return;
		while(root != null)
		{
			System.out.print(root.data + " ");
			if(root.child != null)
				traverseTree(root.child);
			root = root.next;
		}
	}

	// Driver code
	public static void main(String args[])
	{
		
		/* Let us create below tree
		*		 10
		*	 / / \ \
		* 2 3	 4 5
		*			 | / | \
		*			 6 7 8 9 */
	
		// Left child right sibling
		/* 10
		* |
		* 2 -> 3 -> 4 -> 5
		*			 | |
		*			 6 7 -> 8 -> 9 */

		NodeTemp root = new NodeTemp(10);
		NodeTemp n1 = addChild(root,2);
		NodeTemp n2 = addChild(root,3);
		NodeTemp n3 = addChild(root,4);
		NodeTemp n4 = addChild(n3,6);
		NodeTemp n5 = addChild(root,5);
		NodeTemp n6 = addChild(n5,7);
		NodeTemp n7 = addChild(n5,8);
		NodeTemp n8 = addChild(n5,9);
		
		traverseTree(root);
	}
}

// This code is contributed by M.V.S.Surya Teja.

	```
