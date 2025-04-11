Existem duas estruturas de dados bem populares quando o assunto é representação de grafos:
###### **Matriz de Adjacências**:
 
Se trata de uma matriz  N x M onde cada coordenada ( x , y ) representa uma aresta de conexão entre nós.

![[Pasted image 20250411170940.png]]

Como o grafo estudado é não direcionado, cada aresta aparece duas vezes. No caso mostrado, temos a representação em matriz do caminho {2 - 4} e {4 - 2}.

![[Pasted image 20250411170806.png]]

Caso a aresta ( x , y ) exista, então sua coordenada na matriz de adjacências será marcada com o valor binário 1.

Propriedades:

- Espaço proporcional à n², o que torna essa estrutura de dados inviável em casos de muitos dados.
- Verificar adjacências possui complexidade O(1).
- Identificar todas as arestas possui complexidade equivalente a O(n²).
- Um dos grandes problemas dessas representação de grafos em matriz, é que ela demonstra todos as possíveis conexões entre vértices, inclusive aquelas que não existem.


 - ###### **Lista de Adjacências**:

	É a segunda representação popular de grafos, e possui algumas vantagens em relação a anterior. 

	Nessa representação cada nó possui uma lista de suas conexões 

	![[Pasted image 20250411173547.png]]

	Propriedades:
	
	- Considere: 
		- `n` =  quantidade de nós 
		- `m`  = somatório dos graus.
	
	- Em grafos não direcionados, arestas são representadas duas vezes.
	- Espaço proporcional a m + n.
	- Verificar uma conexão entre vértices é equivalente ao grau do vértice.
	- Identificar todas as arestas é equivalente a O( n + m)