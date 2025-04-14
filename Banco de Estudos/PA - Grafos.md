## Conceitos Básicos de Grafos

Para a dupla de `G = (V, E)` onde:

- V = Conjunto não vazio de vértices (nós).

- E = Conjunto de arestas conectando pares de vértices.

![[Pasted image 20250411165146.png]]

![[Pasted image 20250411165227.png]]

- n = |V|, m = |E|.

- **Adjacências**:
	- Diz-se que dos nós são adjacentes (vizinhos) se somente se haja uma aresta entre eles.

- **Grau de um Vértice** (Degree):
	Se define pela quantidade de arestas conectadas a um vértice. O número de adjacentes que um determinado nó possui.

- Propriedade - **Somatório de Graus**:
	Ao calcular-se a soma dos graus de todos os nós de um grafo, se obtém duas vezes o número de aresta desse grafo:
	∑d(v) = 2|E|  - Soma dos graus é o dobro do número de arestas 

 - **Caminhos** em Grafos:
	Um caminho em um grafo não direcional é uma sequencia de P vértices entre `V1 ~ Vĸ` com a propriedade que cada par de nós é unido diretamente por uma aresta.

	- Caminho Simples: É um caminho que contém apenas nós distintos

- **Grafos Conectados**:
	Um grafo é conectado se somente se para todo par de nós deste grafo houver um caminho entre eles.

- **Ciclo**:
	Descreve um caminho de V1 ~ Vĸ onde V1 = Vĸ.
	- K > 3
	- Todos os nós ate K-1 devem ser distintos.

- **Distancia entre Nós**:
	Menor caminho de arestas que conectam dois nós.

 - **Árvores**:
	Diz-se que um grafo não direcional é uma árvore caso ele cumpra com os seguintes pré-requisitos:
	
	- Grafo conectado.
	- Grafo acíclico.
	- Possui n-1 arestas
	
	obs: `ao verificar qualqueres duas afirmações acima, automaticamente verifica-se a terceira`

---

- ### Grafos Direcionados 
	
	Nesses tipos de grafos, as arestas entre os nós ganham uma propriedade a mais, que é a direção delas. 
	
	Em grafos como esse, a conexão não é automaticamente bidirecional, mas sim sempre em uma só direção. 
	
	Entretanto é possível que haja mais de uma aresta ligando dois nós, cada uma em uma direção
	
	Essas propriedades são importantes por introduzirem uma nova semântica que promove mais possibilidades de representação de dados. 

	- #### [[PA - Ordenação Topológica de Grafos Direcionados Acíclicos]]

### [[PA - Grafos Bipartidos]]
### [[PA - Busca em Grafos]]
### [[PA - Representação de Grafos]]
### [[PA - Conexividade em Grafos]]

