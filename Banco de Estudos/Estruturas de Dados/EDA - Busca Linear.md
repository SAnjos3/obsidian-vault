A **busca linear** é o algoritmo mais simples para localizar um elemento em uma estrutura de dados linear, como vetores ou listas. Ela consiste em percorrer sequencialmente cada elemento da estrutura até encontrar o valor desejado ou até que todos os elementos tenham sido verificados.​

### Características

- **Aplicabilidade**: Funciona em qualquer estrutura linear, ordenada ou não.
    
- **Simplicidade**: Fácil de implementar e entender.
    
- **Desempenho**: Pode ser ineficiente para grandes conjuntos de dados.​
    

---

### Algoritmo

1. Comece no primeiro elemento da estrutura.
    
2. Compare o elemento atual com o valor buscado.
    
3. Se forem iguais, o elemento foi encontrado.
    
4. Se não, avance para o próximo elemento.
    
5. Repita os passos 2 a 4 até encontrar o elemento ou até o final da estrutura.​
    

---
### Análise de Complexidade

- **Melhor caso**: O elemento está na primeira posição → `O(1)`.
    
- **Pior caso**: O elemento está na última posição ou não está presente → `O(n)`.
    
- **Caso médio**: Em média, `O(n)`.​
    

A busca linear é menos eficiente que a busca binária (`O(log n)`), especialmente para grandes conjuntos de dados.

---
#### Exemplo Prático

Considere o vetor: `[4, 2, 7, 1, 9]`​

Vamos buscar o número `7`:​

1. Compare `4` com `7` → diferente.
    
2. Compare `2` com `7` → diferente.
    
3. Compare `7` com `7` → igual! Elemento encontrado na posição 2.