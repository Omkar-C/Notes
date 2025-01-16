#graph
### Single Source Shortest Path Problem

Given a graph with n vertices and m edges, find the shortest path from vertex s to every other vertex.

### Algorithm
1. Initialize a distance array for n nodes where d[i] is the distance from source to i vertex and a visited array to keep track of visited nodes. d[i] = infinity initially.
2. Initialize a predecessor Array to store the previous node from which we calculated the shortest distance to current node.
3. Initialize the d[s] = 0 as the distance of the source from the source is 0.
4. Run the following steps for n iterations
	1. Find the most promising node which is still unvisited. (The node which has the lowest current distance d[i])
	2. For every edge from the selected node, if the distance to other node can be improved than update the distance to this distance and the parent node to the current node.
		If  d[currNode] + weight < d[nextNode] :
			d[nextNode] = d[currNode] + weight
			p[nextNode] = currNode

After the algorithm ends, you will have the distance array having the shortest distance from source node to every node.
If some node is unreachable, the distance array will have infinity.
To reconstruct the shortest path to node v, follow the predeccessor array from node v
**shortest path = (s, ..., p[p[v]], p[v], v)


Depending of the implementation, the time complexity can be calculated by finding the complexity of two operations.
1. The time complexity for getting the most promising node.
	1. If we use a array, then it's O(n).
	2. If we use a priority queue, then it's O(m), since at max you will end up inserting every node for each edge visited.
	3. If we use a priority queue with decrease key operation, then it's O(log(n)).
2. Updating the distance for every edge of the selected node. O(1).

Since we run the algorithm for n iterations, the final complexity will be 
O(n * (log(n) + m))

