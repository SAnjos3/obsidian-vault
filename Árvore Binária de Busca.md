Uma **árvore binária de busca (BST - Binary Search Tree)** é uma estrutura de dados hierárquica usada para armazenar elementos de forma ordenada, facilitando operações como busca, inserção e remoção. Ela segue regras específicas que garantem essa organização eficiente.

#### **Estrutura de uma Árvore Binária de Busca**

Uma BST é composta por **nós**, e cada nó tem no máximo dois filhos:

- **Filho esquerdo**: contém valores **menores** que o nó pai.
    
- **Filho direito**: contém valores **maiores** que o nó pai.
    

Essa propriedade se aplica recursivamente a todos os nós da árvore, o que significa que, para qualquer nó, sua subárvore esquerda conterá apenas valores menores, e sua subárvore direita conterá apenas valores maiores.

#### **Inserção**

Para inserir um novo valor na BST:

1. Comece na raiz.
    
2. Compare o valor com o nó atual:
    
    - Se for menor, vá para a esquerda.
        
    - Se for maior, vá para a direita.
        
3. Repita esse processo até encontrar um nó nulo e insira o novo valor nesse local.

#### **Remoção**

A remoção de um nó na BST pode ter três casos:

1. **Nó sem filhos (nó folha)**: Basta removê-lo diretamente.
    
2. **Nó com um único filho**: O nó é substituído pelo seu único filho.
    
3. **Nó com dois filhos**: Substituímos o nó pelo seu **sucessor in-order** (o menor nó da sua subárvore direita) ou pelo **antecessor in-order** (o maior nó da sua subárvore esquerda). Isso mantém a propriedade da BST.