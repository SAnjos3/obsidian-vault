Nessa fase, o compilador verifica se a sequencia de tokens retornado pela fase de análise léxico estão estruturados de acordo com as regras sintáticas da linguagem. 

Esse processo terá como produto uma árvore sintática que determina a ordem de leitura e execução dos tokens. Quando uma árvore não pode ser formada corretamente, o compilador retorna erro sintático.

**Importância da Análise Sintática:**

- **Validação Estrutural**: Garante que a sequência de tokens forma uma sentença válida na linguagem.
    
- **Construção de Representações**: Gera estruturas intermediárias (como árvores sintáticas) que facilitam etapas posteriores, como análise semântica e geração de código.
    
- **Detecção de Erros**: Identifica erros de sintaxe que não podem ser detectados na análise léxica.

Exemplo de AST:

``` python 
3 + 4 * (2 - 1)

add
├── number: 3
└── mul
    ├── number: 4
    └── sub
        ├── number: 2
        └── number: 1

```


