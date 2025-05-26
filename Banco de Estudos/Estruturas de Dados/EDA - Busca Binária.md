A **busca binária** é um algoritmo eficiente para localizar um elemento em um vetor ordenado. A ideia central é dividir o espaço de busca pela metade a cada iteração, comparando o elemento alvo com o elemento central do intervalo atual.​

###  Pré-requisitos

- O vetor deve estar **ordenado**.
    
- Acesso aleatório aos elementos do vetor (como em arrays).​
	
- Em listas encadeadas a busca binária é feita no formato de [[EDA - Arvore Binária]]  - > [[EDA - Arvore Binária de Busca]]

---

## Algoritmo

1. Inicialize dois ponteiros: `início` e `fim`, representando os limites do vetor.
    
2. Enquanto `início` ≤ `fim`:
    
    - Calcule o índice do meio: `meio = (início + fim) / 2`.
        
    - Compare o elemento no índice `meio` com o valor buscado:
        
        - Se forem iguais, o elemento foi encontrado.
            
        - Se o valor buscado for menor, ajuste `fim = meio - 1`.
            
        - Se for maior, ajuste `início = meio + 1`.
            

---
## Análise de Complexidade

- **Melhor caso**: O elemento está no meio do vetor na primeira tentativa → `O(1)`.
    
- **Pior caso**: O elemento não está presente ou está nas extremidades → `O(log n)`.
    
- **Caso médio**: Em média, também `O(log n)`.​[

A busca binária é significativamente mais eficiente que a busca linear (`O(n)`), especialmente para grandes conjuntos de dados.

---
#### Exemplo Prático

Considere o vetor ordenado: `[1, 3, 5, 7, 9, 11, 13]`​

Vamos buscar o número `9`:​

1. `início = 0`, `fim = 6`, `meio = 3` → elemento no índice 3 é `7`.
    
2. Como `9 > 7`, atualize `início = 4`.
    
3. Agora, `meio = 5` → elemento no índice 5 é `11`.
    
4. Como `9 < 11`, atualize `fim = 4`.
    
5. Agora, `meio = 4` → elemento no índice 4 é `9`.
    
6. Elemento encontrado!

