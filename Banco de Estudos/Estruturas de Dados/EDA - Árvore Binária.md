Uma **árvore binária** é uma estrutura de dados hierárquica na qual cada **nó** pode ter, no máximo, **dois filhos**. Esses filhos são chamados de **filho esquerdo** e **filho direito**.

Ela recebe esse nome porque cada nó pode ter **zero, um ou dois filhos**, nunca mais do que isso.

#### **Estrutura de uma Árvore Binária**

Cada **nó** de uma árvore binária contém três elementos principais:

1. **Um valor** (ou dado).
    
2. **Uma referência para o filho esquerdo** (pode ser nula se não houver filho).
    
3. **Uma referência para o filho direito** (também pode ser nula se não houver filho).

#### **Tipos de Árvores Binárias**

Existem diferentes variações de árvores binárias, dependendo das regras usadas para organizar os nós. Algumas delas incluem:

1. **Árvore Binária Completa**: Todos os níveis são preenchidos completamente, exceto possivelmente o último nível, que está preenchido da esquerda para a direita.

	![[Pasted image 20250401144921.png]]

2. **Árvore Binária Cheia**: Cada nó tem **zero ou dois filhos** (nunca apenas um filho).

	![[Pasted image 20250401144647.png]]

3. **Árvore Binária Perfeita**: Todos os nós internos têm exatamente dois filhos e todas as folhas estão no mesmo nível.

	![[Pasted image 20250401145052.png]]

4. **Árvore Binária Balanceada**: O número de níveis da árvore é mantido o mais baixo possível para otimizar a eficiência das operações.
    
5. **[[EDA - Árvore Binária de Busca]] (BST - Binary Search Tree)**: Segue regras que mantêm os elementos ordenados (como explicado antes).

####  **Operações em Árvores Binárias**

Algumas operações comuns em árvores binárias são:

- **Inserção**: Adicionar um novo nó na árvore.
    
- **Busca**: Encontrar um nó específico.
    
- **Remoção**: Excluir um nó e reorganizar a árvore.
    
- **Percursos (Traversal)**: Percorrer a árvore de diferentes formas (pré-ordem, em-ordem, pós-ordem).