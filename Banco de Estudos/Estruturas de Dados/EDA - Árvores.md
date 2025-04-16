Uma **árvore** é uma **estrutura de dados hierárquica** que organiza elementos de forma semelhante a uma árvore da natureza.

Ela é composta por **nós** conectados por **arestas**, formando uma estrutura em que **um nó principal** (chamado de **raiz**) se ramifica em outros nós, criando uma relação de **pai e filho**.

#### **Características de uma Árvore**

1. **Hierárquica**: Diferente de listas ou arrays, onde os elementos são organizados sequencialmente, as árvores têm uma estrutura em níveis.
    
2. **Raiz**: O nó principal da árvore, que serve como ponto de partida.
    
3. **Nós**: Elementos da árvore que armazenam valores e podem ter filhos.
    
4. **Filhos**: Nós que derivam de um nó pai.
    
5. **Folhas**: Nós que **não têm filhos**.
    
6. **Altura da árvore**: O número de níveis da raiz até a folha mais profunda.

#### **Tipos de Árvores**

1. **Árvore Geral**: Cada nó pode ter qualquer número de filhos.
    
2. [[EDA - Árvore Binária]]: Cada nó pode ter **no máximo dois filhos**.
    
3. [[Árvore de Busca Binária]] (BST)**: Uma árvore binária com regras para manter os elementos ordenados.
    
4. **Árvore Balanceada**: Mantém a altura reduzida para otimizar operações.
    
5. **Árvores Trie, AVL, Red-Black, B-Trees**: Usadas em diferentes aplicações como bancos de dados, buscas eficientes e compressão de dados.

#### **Propriedades Importantes**

- Cada nó pode ter **zero, um ou mais filhos**.
    
- Não pode haver **ciclos** (ou seja, um nó não pode apontar de volta para um ancestral).
    
- Um nó pode ter **apenas um pai**, exceto a raiz, que não tem pai.