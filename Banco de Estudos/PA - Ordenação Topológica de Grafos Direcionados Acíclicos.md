Esse grafo contém arestas direcionadas e que caso seja respeitado o sentido das arestas, não há ciclos.

![[Pasted image 20250414021123.png]]

Esses tipos de grafos estabelecem uma relação de precedência entre os componentes da estrutura. Isso significa que considerando:

`Aresta(Vi,Vj), o componente Vi deve ocorrer antes do componente Vj.`

#### Ordenação Topológica 

Significa ordenar um grafo direcionado de forma que os componentes fiquem no formato: `V¹,V²,V³,Vŋ` e para toda conexão (Vi, Vj) tem-se que i < j. Isso significa que o resultado contém arestas em apenas um sentido, sem nenhuma em contramão.

![[Pasted image 20250414021642.png]]

Quando aplica-se uma ordenação topológica, é possível obter diferentes resultados corretos, porém não se encontra nenhum resultado caso o grafo de origem possuísse um ciclo em sua estrutura.

![[Pasted image 20250414021941.png]]

- Para que um grafo seja considerado direcionado e acíclico, e possua uma ordenação topológica, então ele deve conter pelo menos nó o que não possua nenhuma aresta lhe apontando.

