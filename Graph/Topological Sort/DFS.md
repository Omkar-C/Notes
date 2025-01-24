#graph #dfs
### Intuition
If there are no cycles in a graph and we do dfs, then dfs(v) exits only when it has visited all nodes that can be visited from v. Thus if we just append this node to a list, then this node will be the last visited node that can be visited from v, since all other nodes would have been already visited and appended to the list.
https://cp-algorithms.com/graph/topological-sort.html

### Code
```cpp
int n; // number of vertices
vector<vector<int>> adj; // adjacency list of graph
vector<bool> visited;
vector<int> ans;

void dfs(int v) {
    visited[v] = true;
    for (int u : adj[v]) {
        if (!visited[u])
            dfs(u);
    }
    ans.push_back(v);
}

void topological_sort() {
    visited.assign(n, false);
    ans.clear();
    for (int i = 0; i < n; ++i) {
        if (!visited[i]) {
            dfs(i);
        }
    }
    reverse(ans.begin(), ans.end());
}
```
