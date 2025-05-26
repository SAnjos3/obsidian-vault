Em relação a busca em grafos, o primeiro problema a se tratar é:

	`Existe um caminho entre dois nós de um grafo?`

Essa primeira pergunta leva a uma próxima:

	`Qual o menor caminho entre dois nós?`

A busca tem que ser feita com base na garantia de que ela não será feitas em ciclos e tem como objetivo partir de um nó específico e chegar em outro nó específico.
#### Aplicações

- **Encontrar saída de Labirinto**
- **Número de Kevin Bacon** 
- **Menor número de passos em uma rede de comunicação**

### [[EDA - BFS - Busca em Largura]]

### [[EDA - DFS - Busca em Profundidade]]

#### Tipos de Busca por Grafos

Existem tipos de busca por grafos que pode-se aplicar tanto na busca em largura quando na busca por profundidades.

![[Pasted image 20250413184713.png]]

- `funct(G)`: 
	
	Nesse caso apenas o grafo é passado como parâmetro, assim a função buscara qualquer nó inicial nesse grafo, e não terminará suas operações até que não haja mais nenhum outro vértice a ser explorado.
	
	O retorno de uma função desse tipo seriam 3 árvores no caso do grado acima.
	
- `funct(G,i):
	
	Nesse tipo de busca, não só o grafo é passado como parâmetro, mas também um valor inicial por onde a função deve começar a estruturar a árvore. 
	
	A função procurará por todos os nós diretamente e indiretamente conectados ao nó inicial. Isso significa que aquelas outras árvores não ligadas ao nó inicial não seriam inclusas no retorno.
	
- `funct(G,i,f):
	
	O Grafo, nó inicial e nó final são passados com parâmetros. Essas informações serão utilizadas na operação de busca a partir do nó inicial e com término no nó final. 
	
	Isso significa que o valor retornado será uma subárvore incluindo apenas o nó inicial, nó final, e nós encontrados entre o início e término da operação