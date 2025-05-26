Esse grafo contém arestas direcionadas e que caso seja respeitado o sentido das arestas, não há ciclos.

![[Pasted image 20250414021123.png]]

Esses tipos de grafos estabelecem uma relação de precedência entre os componentes da estrutura. Isso significa que considerando:

`Aresta(Vi,Vj), o componente Vi deve ocorrer antes do componente Vj.`

#### Ordenação Topológica 

Significa ordenar um grafo direcionado de forma que os componentes fiquem no formato: `V¹,V²,V³,Vŋ` e para toda conexão (Vi, Vj) tem-se que i < j. Isso significa que o resultado contém arestas em apenas um sentido, sem nenhuma em contramão.

![[Pasted image 20250414021642.png]]

Quando aplica-se uma ordenação topológica, é possível obter diferentes resultados corretos, porém não se encontra nenhum resultado caso o grafo de origem possuísse um ciclo em sua estrutura.

![[Pasted image 20250414021941.png]]
#### Lógica de Ordenação 

Levando em consideração que em um grafo é direcionado acíclico, pode-se concluir que existe ordenação topológica para esse grafo.

Grafos com essas características possuem pelo menos um nó o qual não possui nenhuma aresta lhe apontando, chamaremos esse nó de "nó-base"

Utilizando essa propriedade, gera-se a ordenação topológica de um grafo:

- Encontrando e retirando o nó-base do grafo.

- Isso fará com que um novo nó receba a característica de não possuir arestas lhe apontando. Assim retira-se esses nós-base recursivamente, até que não sobre nenhum.

- A ordem com que foi retirados os nós gerará a ordenação topológica do grafo estudado.