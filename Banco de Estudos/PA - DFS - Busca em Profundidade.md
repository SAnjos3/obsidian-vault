Nessa abordagem, diferentemente de uma busca por largura, a busca é feita em um sentido até encontrar um nó que não possua adjacentes para explorar. Assim em algorítimos DFS não se respeita a ordem de camadas, como era feito em BFS.
#### Lógica do Algorítimo

A lógica da DFS é começar por um nó e marca-lo como visitado. Após isso, escolhe-se um vizinho desse nó para começar a busca a partir dele, então esse vizinho é marcado como visitado e procura-se um vizinho do vizinho. Essa operação se repete até que se encontre um vértice que não está ligado a mais nenhum vizinho não visitado. Quando essa situação ocorrer, é aplicado o backtracking.

Para que essa busca em profundidade funcione, o conceito de backtracking é fundamental. No contexto da **DFS (Depth-First Search)**, **backtracking** acontece quando:

- O algoritmo está explorando um caminho profundo no grafo (ou árvore),
    
- Mas chega num **nó sem vizinhos não visitados** (ou seja, **um beco sem saída**),
    
- Então, ele **volta para o nó anterior** para tentar outro caminho.
    

Esse "voltar atrás" para explorar outras possibilidades é o que chamamos de **backtracking**.

![[Pasted image 20250413161717.png]]

O algorítimo acima esta implementado utilizando recursão, embora isso possa causar facilmente o estouro da stack. Porém, existe uma maneira de implementar esse algorítimo baseando-se em iterações e uma pilha, colhendo o mesmo resultado.

#### Propriedades DFS

- **Estrutura de dados**: Utiliza uma **pilha** (LIFO – último a entrar, primeiro a sair)
    
    - Pode ser implementada com **recursão** (usando a pilha de chamadas) ou com uma **pilha explícita**.
        
- **Propriedade**: Explora **profundamente** cada caminho antes de retroceder (backtracking)
    
    - Pode visitar vértices **muito distantes da raiz** antes de explorar vértices mais próximos.
        
- **Complexidade**:
    
    - **O(n + m)** para grafos representados por lista de adjacência, onde:
        
        - `n` = número de vértices
            
        - `m` = número de arestas
            
- **Aplicações**:
    
    - Detectar **ciclos** em grafos
        
    - Encontrar **componentes fortemente conexos** (em grafos direcionados)
        
    - Resolver problemas de **ordenação topológica**
        
    - Resolver labirintos e problemas que envolvem **exploração completa**
        
    - Usado como base para algoritmos mais sofisticados, como o de **Tarjan** e **Kosaraju**
	
- **Ancestralidade**: 
	
	- Caso em um grafo G, os vértices "a" e "b" são conectados por uma aresta, e no algorítimo de busca por profundidade o nó "a" for explorado antes do nó "b", assim conclui-se que "a" é ancestral de "b".
	
	![[Pasted image 20250413170649.png]]
	
	- Note que para garantir a ancestralidade, deve haver uma aresta entre os dois vértices em estudo. Um caminho entre esses dois vértices não garante a ancestralidade entre eles.