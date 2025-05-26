Nessa abordagem, começa-se em um nó específico para explorar primeiramente todos seus nós adjacentes.

O algorítimo BFS baseia-se em camadas:

- L0 = {S} , sendo S o nó inicial.
- L1 = Camada onde estão todos os adjacentes à camada L0. Distancia = 1 em relação ao nó S.
- L2 = Camada onde se encontram os vizinhos dos vizinhos. Distancia = 2 em relação ao nó S.
- L i+1 = Camada onde se encontram todos os vizinhos da camada anterior. Distancia = i em relação ao nó S.

A busca só prossegue para a próxima camada ao explorar completamente a camada atual. 

Considerando que a distancia dos nós são equivalentes ao nível das camada onde se encontram. O algorítimo de busca em largura sempre garante o menor caminho.

O retorno gerado por uma busca em largura é uma árvore, sendo o nó inicial a raiz dessa árvore. Pode existir mais de uma árvore 

Um nó é filho do outro se ele estiver conectado ao mesmo e se encontrar em uma camada a mais.

Não se garante a ordem de busca entre os vizinhos de um nó. Assim cada vez que se roda um algorítimo BFS, pode ser retornada uma árvore diferente. Porém tem-se que a árvore retornada depende do nó inicial.
#### Algoritmo BFS (Busca em Largura)

![[Pasted image 20250411205631.png]]

1. Para cada nó `s` ainda não explorado:
2. (Enqueue(S, s)) → Adicione o nó `s` na fila `S` 
3. Marque o nó `s` como visitado
4. Enquanto a fila `S` não estiver vazia:
5. Dequeue(S) → Remova o primeiro nó da fila 
6. (Adj[u]) → Para cada nó `v` na lista de adjacência do nó `u`:
7. Se `v` não foi explorado:
8. Marque a aresta `(v, u)` como aresta da árvore
9. Marque o nó `v` como visitado
10. Adicione `v` na fila `S` (Enqueue(S, v))

| Termo          | Significado                                           |
| -------------- | ----------------------------------------------------- |
| `Adj[u]`       | Lista de vértices vizinhos de `u` (em qualquer ordem) |
| `Dequeue(S)`   | Remove e retorna o elemento mais antigo da fila `S`   |
| `Enqueue(S,v)` | Adiciona o vértice `v` no final da fila `S`           |
| `G`            | Grafo explorado                                       |
| `s`            | Nó do Grafo G                                         |
| `S`            | Fila de nós                                           |
| `(v,u)`        | Aresta entre o nó u e v.                              |

## Características Principais

- **Estrutura de dados**: Utiliza uma fila (FIFO - primeiro a entrar, primeiro a sair)
	- Por utilizar filas, o algorítimo garante arvores acíclicas.

- **Propriedade**: Explora os vértices em ordem de distância da raiz

- **Complexidade**: O(m + n) para grafos representados por lista de adjacência

- **Aplicações**:
  - Encontrar caminhos mais curtos em grafos não-ponderados
  - Testar conectividade
  - Identificar componentes conexos