#### Conjuntos conexo

S é um conjunto conexo se e somente se para quaisquer nós A e B:

- A for alcançável por B.
- B for alcançável por A.

#### Componentes conexo

S é um componente conexo se e somente se:

- Com base em um conjunto conexo, tem-se que todos os outros nós que não fazem parte da estrutura desse conjunto não podem ser conexo com o mesmo.

	`para todo µ ∈ G-C, a união entre {u} e C não deve ser conexo.`
	
	- G - Grafo como um todo
	- C - Conjunto conexo
	- u - nó qualquer que não pertence ao conjunto conexo.

![[Pasted image 20250413214512.png]]

Nesse caso acima, pode-se formar 3 conjuntos conexo máximos. São eles:

- Conjunto formado por {1,2,3,4,5,6,7,8}.
- Conjunto formado por {9,10}
- Conjunto formado por {11,12,13}

Esses três conjuntos conexo máximos são componentes conexo. 

Porém caso fosse formado um conjunto conexo formado por {1,2,3}, o mesmo não poderia ser considerado um componente conexo, pois existiria valores de {u} que ainda eram conexo a esse conjunto, ferindo assim a lei de formação de componentes conexo.

---
### Conexidade em Grafos Direcionados (Conexidade Forte e Fraca)

Em grafos com essa propriedade, as classificações em relação a conexidade de uma grafo mudam:

- **Grafos Não-Conectados**: Remetem aqueles grafos que não possuem nós conectados entre si

- **Grafos Fracamente-Conectados**: Caso o grafo respeite essas duas propriedades o chamamos de grafo fracamente-conectado

	Porém a segunda propriedade é apenas uma obstrução para que esse grafo seja considerado fortemente-conectado. 
	Em outras palavras, todo grafo fortemente-conectado também é um grafo fracamente-conectado, enquanto isso, não é possível afirmar o contrário

	- Caso sejam ignoradas as direções das arestas, o grafo não-direcionado resultante é conexo.
	 - Exista pelo menos um nó onde partem conexões, mas não há conexões de volta, gerando um nó que não é alcançável dependendo do ponto de partida

- **Grafos Fortemente-Conectados**: Ocorre quando todos os nós do grafo são alcançáveis independente do ponto de partida. Assim se for estudar os nós de um grafo fortemente conectado, sempre haverá um caminho para qualquer vértice escolhido.

	`Caso se encontre um nó {s}, é alcançável por todos os outros nós, e todos os outros nós são alcançáveis por ele. Então tem-se um grafo fortemente conectado.`

	- Caso se inverta todas as arestas de um grafo fortemente-conectado, outro grafo fortemente-conectado será gerado.

### Grafos Fortemente-Conectados - Algorítimo

Considerando um grafo G, o algorítimo a seguir testa a conexidade seguindo a seguinte lógica:

- Escolhe-se um nó {s} qualquer de G.
- Aplica-se o algorítimo BFS(G,{s}), gerando uma busca em largura no grafo a partir do nó {s}.
- Gerar o grafo reverso de G.
- Aplicar o algorítimo BFS(G®,{s}), gerando uma busca em largura no grafo reverso a partir do nó {s}
- Verifica se todos os nós do grafo foram alcançados nas duas aplicações da BFS.

Complexidade: O(n+m)
