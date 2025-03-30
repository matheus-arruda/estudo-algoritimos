# 🎯 Problemas Clássicos com Grafos em Java

## 1. Busca em Largura (BFS)

**Enunciado**:

Implemente BFS para encontrar o caminho mais curto em um grafo não-direcionado.

```java
Input: grafo = [[1,2],[0,3],[0,3],[1,2]], nó inicial =  0

Output: [0, 1, 1, 2] (distâncias do nó 0)
```
  

🔍 Solução

```java

public  int[] bfs(List<List<Integer>> graph, int start) {

	int[] distances  =  new  int[graph.size()];

	Arrays.fill(distances, -1);

	Queue<Integer> queue  =  new  LinkedList<>();

	queue.add(start);

	distances[start] =  0;

	while (!queue.isEmpty()) {

		int  node  =  queue.poll();

		for (int  neighbor  :  graph.get(node)) {

			if (distances[neighbor] ==  -1) {

					distances[neighbor] = distances[node] +  1;

					queue.add(neighbor);

				}

		}

	}

	return distances;

}
```
Complexidade:  O(V + E).
