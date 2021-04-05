+++
author = "Hugo Authors"
title = "백준 1260번 DFS와 BFS"
date = "2021-04-05"
description = "백준 1260_DFS와 BFS 파이썬 문제풀이"
categories = [
    "Algorithm"
]
tags = [
    "백준", "boj", "python", "1260", "graph traversal"

]

image = "boj.png"

+++

# 1260번_DFS와 BFS

[문제 보러가기](https://www.acmicpc.net/problem/1260)

## 🅰 코드

```python
N,M,V=map(int,input().split())
matrix=[[0]*(N+1) for i in range(N+1)]
for i in range(M):
    a,b = map(int,input().split())
    matrix[a][b]=matrix[b][a]=1
visit_list=[0]*(N+1)

def dfs(V):
    visit_list[V]=1
    print(V, end=' ')
    for i in range(1,N+1):
        if(visit_list[i]==0 and matrix[V][i]==1):
            dfs(i)

def bfs(V):
    queue=[V]
    visit_list[V]=0
    while queue:
        V=queue.pop(0)
        print(V, end=' ')
        for i in range(1, N+1):
            if(visit_list[i]==1 and matrix[V][i]==1):
                queue.append(i)
                visit_list[i]=0

dfs(V)
print()
bfs(V)

```


## ✅ 후기

* 문제 자체는 `SSAFY`교육에도 진행되었던 `DFS`, `BFS`의 가장 기본인 코드를 구현하는 것이었다. 그렇기에 어렵지는 않았지만, 궁극적인 목표는 어떤 문제에는 어떤 알고리즘으로 구현하는 것이 더 어울리는지 문제를 보고 바로 아는 것인것 같다. 그러므로 더욱 노력해야 할것 같다;;