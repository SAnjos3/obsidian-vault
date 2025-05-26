Arvores já foram desenvolvidas, porém havia um problema ainda:

O problema: Como implementar uma tabela de símbolos em uma BST de modo que a árvore permaneça balanceada qualquer que seja as sequencias de busca e inserções?

O que é uma árvore balanceada?
- Refere-se  a que? A altura da árvore

Destaques das árvores 2-3

- nós simples e duplos
- nós triplos temporários
- operação de busca
- operação de inserção 
- toda árvore 2-3 é perfeitamente balanceada
- altura nunca passa de - c * log(N)

	- Isso resolve um problema de árvores. A altura de uma árvore cresce com a inserção de novas chaves na árvore.

A solução para o problema da altura e balanceamento das arvores: Armazenar mais de uma chave em cada nó.

![[Pasted image 20250403142456.png]]

Árvores 2-3 foi projetada para um bom desempenho no pior caso.
- Se temos apenas nos simples, a altura será: log(N)
- Se temos apenas nós duplos, a altura será: log(n) base - 3 = log(n)/log(3)

---
### Inserção em Árvores 2-3

A inserção sempre é feita nas folhas para ser distribuída da maneira correta para os níveis mais próximos da raiz.

- Inserção em Nó Simples - inserção simples:
	1. torne-o nó duplo:
	
	Exemplo:
	    D                       D
	   /   \        ->        /    \
	  A   G               A-B   G

- Inserção em Nó Duplo: 
	1. torne-o triplo temporariamente.
	2. Promova a chave do meio para o nível superior.
	3. Faça isso recursivamente em casos de formação de nós triplos.
	
	Exemplo:
	    M                        M                    G-M 
       /    \       ->       /          \      ->    /    |    \                  
     E-R   T        E-G-R        T          E     R     T

---

### Remoção em Árvore 2-3

A remoção de um item deve levar em consideração manter a estrutura da árvore 2-3. Em remoção de items, há casos em que se torna necessário fazer uma redistribuição dos items para manter as propriedades da arvore 2-3.

- Remoção de Nó Duplo na Folha - Caso mais simples e que resume-se apenas em:

	1. Tornar o nó duplo em nó simples.

Algumas das  remoções ferem com as propriedades da árvore 2-3:

- Nós Duplos devem possuir sempre 3 nós filhos. A remoção pode gerar casos erro como:

	- Nós duplos com 2 nós filhos.

- Nos Simples devem possuir sempre 2 nós filhos. A remoção pode gerar casos erro como:

	- Nó simples com 1 nó filho.

	- Nó simples com 3 filhos.

- Balanceamento perfeito da Arvore. A remoção pode gerar casos erro como:

	- O rebalanceamento dos nós apos um remoção ainda pode ferir a distribuição. Quando se faz a distribuição dos nós, deve-se levar em consideração que os nós folhas devem sempre estar na mesma profundidade.

##### Algorítimo de Remoção

Para

