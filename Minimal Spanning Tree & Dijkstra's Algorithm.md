Minimal Spanning Tree - a weighted graph where all the nodes are connected and has the least total cost. Only works on undirected graphs. Can handle negative weights with prim's algorithm
	-Use min heap for priority queue



Prim's algorithm 
- Choose a vertice. choose the vertice with the minimal edge among all adjacent nodes.  Keep track of previous edges in case they are the minimal edge after each round.
- ![[Pasted image 20230424010904.png]]
	Example: AB (3),  BE (3),  ED (1), DC (2), EF (2), CG(4), GH (3), EI (4), IJ (3), IL (5), GK(6)



Dijkstra's Algorithm - find the shortest path between a source node and a target node
- Only works when all the edge-weight are nonnegative