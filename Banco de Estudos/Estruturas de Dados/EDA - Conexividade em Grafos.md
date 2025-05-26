### Conexidade em Grafos Não-Direcionados
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


#### Grafos Fortemente-Conectados 

- **Grafos Fortemente-Conectados**: Ocorre quando todos os nós do grafo são alcançáveis independente do ponto de partida. Assim se for estudar os nós de um grafo fortemente conectado, sempre haverá um caminho para qualquer vértice escolhido.

	`Caso se encontre um nó {s}, é alcançável por todos os outros nós, e todos os outros nós são alcançáveis por ele. Então tem-se um grafo fortemente conectado.`

	- Caso se inverta todas as arestas de um grafo fortemente-conectado, outro grafo fortemente-conectado será gerado.


#### Grafos Fracamente-Conectados

- **Grafos Fracamente-Conectados**: Caso o grafo respeite essas duas propriedades o chamamos de grafo fracamente-conectado

	Porém a segunda propriedade é apenas uma obstrução para que esse grafo seja considerado fortemente-conectado. 
	Em outras palavras, todo grafo fortemente-conectado também é um grafo fracamente-conectado, enquanto isso, não é possível afirmar o contrário

	- Caso sejam ignoradas as direções das arestas, o grafo não-direcionado resultante é conexo.
	 - Exista pelo menos um nó onde partem conexões, mas não há conexões de volta, gerando um nó que não é alcançável dependendo do ponto de partida


#### Algorítimo - Verificação de Conexidade

Considerando um grafo G, o algorítimo a seguir testa a conexidade seguindo a seguinte lógica:

- Escolhe-se um nó {s} qualquer de G.
- Aplica-se o algorítimo BFS(G,{s}), gerando uma busca em largura no grafo a partir do nó {s}.
- Gerar o grafo reverso de G.
- Aplicar o algorítimo BFS(G®,{s}), gerando uma busca em largura no grafo reverso a partir do nó {s}
- Verifica se todos os nós do grafo foram alcançados nas duas aplicações da BFS.
- Complexidade: O(n+m)

---
#### Componentes Fortemente Conectados 

Em teoria dos grafos, os **componentes fortemente conectados** (CFCs) são uma forma de decompor grafos direcionados em subestruturas que facilitam a análise de sua conectividade. 

Em grafos fortemente conectados, essas subestruturas irão se resumir apenas uma, que é o grafo em si. Porém, um grafo fracamente-conectado terá ao mínimo dois desses componentes.

##### Algorítimo - Verificação de Componentes Fortemente Conectados 

Grafo G:

![[Pasted image 20250508201459.png]]

#### Passo 1: DFS(G) para computar post[v]  

DFS(G):

0.  time ← 1  
1.  Para todo v em G.V  
2.    Se v não visitado então  
3.       DFS-Visit(G, v)  

DFS-Visit(G, v):

1.  Marque v como visitado  
	1.  pre[v] ← time; time ← time + 1  
2.  Para todo w em Adj(v)  
3.     Se w não visitado então  
4.        Insira aresta (v, w) na árvore DFS  
5.        DFS-Visit(G, w)  
6.  post[v] ← time; time ← time + 1  

![[Pasted image 20250508201609.png]]

#### Passo 2: Construir o grafo reverso G^R  

COMPUTE-REVERSE(G):

0.  G^R.V ← G.V  
1.  G^R.E ← ∅  
2.  Para cada aresta (u, v) em G.E faça  
3.     Insira aresta (v, u) em G^R.E  
4.  Retorne G^R  

	Grafo G-Reverso:
	![[Pasted image 20250508201646.png]]

#### Passo 3: DFS em G^R na ordem decrescente de post[v]  

DFS-ON-REVERSE( G^R , post):

0.  Marcar todos os vértices de G^R como não visitados  
1.  Ordene V em ordem decrescente de post[v]  
2.  Para todo v em V (nessa ordem) faça  
3.     Se v não visitado então  
4.        DFS-Visit-R( G^R , v)  

DFS-Visit-R( G^R , v):

1.  Marque v como visitado  
2.  Adicione v ao componente corrente (SCC corrente)  
3.  Para todo w em Adj^R(v)  // arestas de G^R  
4.     Se w não visitado então  
5.         Insira aresta (v, w) na árvore DFS de G^R  
6.         DFS-Visit-R( G^R , w)  

#### Passo 4: Extrair cada componente fortemente conectado  

	// Supondo que a cada chamada de DFS-Visit-R iniciamos um novo “SCC corrente” 

Para cada SCC corrente gerada em DFS-ON-REVERSE faça  
   Imprima ou armazene a lista de vértices dessa SCC  
