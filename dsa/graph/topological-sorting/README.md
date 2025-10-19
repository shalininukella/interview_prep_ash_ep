# Topological Sorting

Use kahn's algorithm

Keep in-degrees (if incoming edge represents a dependency of fro&#x6D;_&#x6E;ode on t&#x6F;_&#x6E;ode ) array whichever node doesn't have any in-degree means that node does not depend on any other node and can be processed so add that to result and decrement its dependent's in degrees by 1 adding them to processing queue.

```python
degrees = [0] * n
adj_list = defaultdict(list)

for frm, to in dependencies:
    degrees[to] += 1
    graph[frm].append(to)
    
q = deque([i for i in range(n) if degrees[i] == 0])

result = []

while q:
    node = q.popleft()
    result.append(node)
    for nbr in adj_list[node]
        degrees[nbr] -= 1
        if degrees[nbr] == 0:
            q.append(nbr)

return result
```
