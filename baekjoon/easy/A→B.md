# A→B

URL: https://www.acmicpc.net/problem/16953
문제 번호: 16953
작성일시: 2022년 1월 5일 오후 11:32

# 솔루션

```python
from collections import defaultdict, deque

A:int;B:int;
dist = defaultdict(int)

def bfs():
    q = deque([A])
    dist[A] = 1
    while q:
        node = q.popleft()
        if node == B:
            return dist[node]
        
        next_node = node * 2
        if next_node <= B and next_node not in dist:
            q.append(next_node)
            dist[next_node] = dist[node] + 1
        next_node = node*10 + 1
        if next_node <= B and next_node not in dist:
            q.append(next_node)
            dist[next_node] = dist[node] + 1
    return -1

A, B = map(int ,input().split())
print(bfs())
```