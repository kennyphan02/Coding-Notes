Graph data structure - a collection of vertices and edges (V,E)
	- Collection of edges, E, represented as ordered pair of vertices (U,V)
	- ![[Pasted image 20230217201000.png]]
	- V = {0,1,2,3}
	- E = {(0,1), (0,2), (1,2), (0,3)}
	- G = {V,E} 
- Graph Terminology
	- Sparse Graph
	- Dense Graph
	- Adjacency - A vertex is adjacent to another vertex if there is an edge connecting them (ie: (0,2) is adjacent)
	- Path - A sequence of edges that allow you to go from one vertice to another
	- Directed Graph - A graph with directed arrows. (i.e if the graph above was directed, the edge (0,2) wouldn't mean there is an edge (2,0) as well )
	- Undirected Graph - A graph with edges that do not point in any direction (edges are bidirectional)
	- Connected graph - There exists at least one path from a vertex to another vertex for all vertex
	- Spanning Tree- vertices connected with the minimum possible number of edges. 
	- Connected graph - Every pair of vertices connected by a unique edge 
	- Complete graph - every vertex has an edge to every other vertex 
	- Directed Acyclic Graph (a directed graph with no directed cycles)
	- Topological Sort - takes
	- Sparse graph - A graph with as few edges as possible 
	- Dense graph - A graph with the maximal number of edges possible
- How are graphs represented? 
	- Adjacency Matrix: 2D array of V x V vertices. Each row and column represent a vertice
		- If the value at `a[i][j]` is 1, it indicate there is an edge (i,j) 
		- ![[Pasted image 20230217203749.png]]
	-  Adjacency List: an array of linked lists. The index of an array represents the vertex and each elements in its linked list represents the edges that the vertex form with the other vertices 


Warshall's Algorithm
