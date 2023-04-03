Balance Factor for each node = height of left subtree - height of right subtree
![[Pasted image 20230403151845.png]]
- If the inserted node is in the right subtree of the right subtree of A, rotate the nodes left
![[Pasted image 20230403151920.png]]
- If the inserted node is in the left subtree of the left subtree of A, rotate the nodes right
![[Pasted image 20230403152717.png]] ![[Pasted image 20230403152725.png]] ![[Pasted image 20230403152729.png]] ![[Pasted image 20230403152736.png]] ![[Pasted image 20230403152738.png]] 
- If the inserted node is in the right subtree of the left subtree of A, rotate the subtree to the left then rotate the full tree to the right
![[Pasted image 20230403153158.png]] ![[Pasted image 20230403153201.png]] ![[Pasted image 20230403153203.png]]  ![[Pasted image 20230403153206.png]] ![[Pasted image 20230403153209.png]] 
- If the inserted node is in the left subtree of the right subtree of A, rotate the subtree to the right then rotate the full tree to the left. 