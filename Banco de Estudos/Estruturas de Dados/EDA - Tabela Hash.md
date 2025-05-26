### Introdução

Uma **Tabela Hash** é uma estrutura de dados que associa **chaves** a **valores**, permitindo operações de busca, inserção e remoção eficientes, geralmente com complexidade média de tempo constante, O(1).

---
### Conceito Fundamental

- **Chave (Key):** Identificador único utilizado para acessar o valor associado.
    
- **Valor (Value):** Informação armazenada e acessada por meio da chave.
    
- **Função Hash:** Algoritmo que transforma a chave em um índice dentro de um array.
    
- **Tabela Hash:** Estrutura de array onde os valores são armazenados nos índices calculados pela função hash.

---
### Algorítimo

1. **Cálculo do Índice:**
    
    - **Função Hash**
    
	    É aplicada à chave para determinar o índice no array. Mapeia-se para inteiros entre **0** e **N-1**, onde **N** é o tamanho da tabela. 
	    
	    Uma boa função hash deve:
		- Ser rápida de calcular.
	    - Distribuir uniformemente as chaves.
		- Minimizar colisões.
        
	    Exemplos:
		- **Para números inteiros:**
	    
		    - `hash(k) = k mod m`, onde `m` é o tamanho da tabela, preferencialmente um número primo.
        
		- **Para strings:**
	    
		    - Converter a string em um número inteiro utilizando métodos como a multiplicação por potências de uma base e aplicar o módulo.
        
2. **Armazenamento:**
    
    - O valor é armazenado na posição do array correspondente ao índice calculado.
        
3. **Busca:**
    
    - Para encontrar um valor, aplica-se a função hash à chave e acessa-se o índice resultante.
        

---
### Tratamento de Colisões

Colisões ocorrem quando diferentes chaves produzem o mesmo índice. Métodos para tratar colisões incluem:

- **Encadeamento Separado (Chaining):**
    
    - Cada posição do array contém uma lista encadeada de pares chave-valor.
        
    - Novos elementos são adicionados à lista correspondente ao índice.
        
- **Endereçamento Aberto (Open Addressing):**
    
    - Em caso de colisão, busca-se outra posição no array de acordo com uma sequência de sondagem (linear, quadrática, dupla hash).
        

---
### Complexidade de Tempo

| Operação | Complexidade Média | Complexidade no Pior Caso |
| -------- | ------------------ | ------------------------- |
| Busca    | O(1)               | O(n)                      |
| Inserção | O(1)               | O(n)                      |
| Remoção  | O(1)               | O(n)                      |

_Nota:_ O pior caso ocorre quando há muitas colisões, resultando em listas longas ou sondagens extensas.

---
### Vantagens e Desvantagens

**Vantagens:**

- Acesso rápido aos dados.
    
- Eficiência em operações de busca, inserção e remoção.
    

**Desvantagens:**

- Não é eficiente para a função ordenar (`sort`) nem de selecionar (`select`)
    
- Desempenho depende da qualidade da função hash.
    
- Pode haver desperdício de espaço se a tabela for muito grande.
	
- Tempo de execução pode crescer se as chaves forem muito longas.


Hashing é um bom exemplo de **time-space-trade-off**:

- **Sem limites de memória**: busca direta com a chave como endereço.
    
- **Sem limites de tempo**: uso de menos memória e buscas sequenciais.
    
- **Hashing** busca um **equilíbrio**: ajustando apenas o **tamanho da tabela**, sem mudar o algoritmo.

---
### Aplicações Comuns

- Implementação de dicionários e mapas.
    
- Indexação de bancos de dados.
    
- Armazenamento de caches.
    
- Verificação de duplicatas.

