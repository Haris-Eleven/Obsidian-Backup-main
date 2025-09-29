# DFS
- Cycle Detection 
- Cycle Detection in Directed Graph
- **Bipartite** Graph
- Topological Sort
# BFS
- 0/1 BFS 
- Cycle Detection 
- Cycle Detection in Directed Graph
- **Bipartite** Graph
- Topological Sort
- Kahn's Algorithm 
# Dijkstra
- Cannot detect negative cycles 
# Prim's
- Minimum spannig tree
- Greedy 
- Kinda like [Dijstra](#dijkstra)
# Kruskal's
- Minimum spannig tree
- Uses [DSU](#dsu) 
- Sort weights and start with minimum
# Floyd-Warshall
- Basic Idea: `d[0][1] = d[0][j] + d[j][0]`
- Shortest path between all pair nodes 
- negative cycles
- DP 
- Brute force ( tries out all combinations )
# Bellman-Ford
- N-1 relaxation of ***edges*** 
- Intuition: At least for one node the child will be the closest
- Negative Cycles 
- Shortest distance between src and all the remaining 
- Directed Graphs only 
- O ( V * E )
# Kahn's
- Implemented from [BFS](#bfs)
# Tarjan's
- Bridges
- Articulation Point
# Kosaraju's 
- Strongly Connected Component (SCC) 
	A component in which every node is reachable from each other 
# DSU
- A Data Structure
- 3 functions ( Make, Find, Union )
- Find length of connected component in linear time 
- Amortized time complexity 
- Rank / Size 
- Path Compression 
- Unoptimised = O(log n)
- Optimised = O (4 )
# BST 
# Heaps
1. A complete binary tree
	- Each level is completely filled except for the last one (maybe)
	- Filled from left to right 
``` cpp
val[child] <= val[par]; // max heap
val[child] >= val[par]; // min heap
```
2. Represented in the form of an array 
3. arr[(i-1)/2] Returns the parent node
4. arr[(2*i)+1] Returns the left child node
5. arr[(2*i)+2] Returns the right child node
## Binary Heap
- Implemented in a tree based structure
## Min/Max Heap
-  Implemented in an array 


