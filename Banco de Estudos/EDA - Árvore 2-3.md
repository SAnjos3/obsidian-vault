Arvores já foram desenvolvidas, porém havia um problema ainda:

O problema: Como implementar uma tabela de símbolos em uma BST de modo que a árvore permaneça balanceada qualquer que seja as sequencias de busca e inserções?

O que é uma árvore balanceada?
- Refere-se  a que? A altura da árvore

Destaques das árvores 2-3

- nós simples, duplas
- nós triplos temporários
- operação de busca
- operação de inserção 
- toda árvore 2-3 é perfeitamente balanceada
- altura nunca passa de - c * log(N)

	- Isso resolve um problema de árvores. A altura de uma árvore cresce com a inserção de novas chaves na árvore.
	- Solução: Armazenar mais de uma chave em cada nó.

![[Pasted image 20250403142456.png]]

Árvores 2-3 foi projetada para um bom desempenho no pior caso.
- Se temos apenas nos simples, a altura será: log(N)
- Se temos apenas nós duplos, a altura será: log(n) base - 3 = log(n)/log(3)