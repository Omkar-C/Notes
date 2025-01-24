#graph 

https://www.geeksforgeeks.org/topological-sorting-indegree-based-solution/
#### Algorithm
Let's count the number of incoming edges to a single node. If there is no incoming to this node, then it's likely a end node. Let's process all such nodes one by one and for every edge from this node, delete the incoming node of the other node it visits. If any node's incoming reaches zero, then add this node to the processing node's list.

- Add all nodes with in-degree **0** to a queue.
- While the queue is not empty:
    - Remove a node from the queue.
    - For each outgoing edge from the removed node, decrement the in-degree of the destination node by **1**.
    - If the in-degree of a destination node becomes **0**, add it to the queue.
- If the queue is empty and there are still nodes in the graph, the graph contains a cycle and cannot be topologically sorted.
- The nodes in the queue represent the topological ordering of the graph.