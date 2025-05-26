**Análise léxica** é a **primeira fase da tradução realizada por um compilador**. Nessa etapa, o **analisador léxico (ou scanner)** recebe o **código-fonte como um fluxo de caracteres** e o segmenta em **unidades léxicas chamadas tokens**.

Cada **token** representa uma **entidade significativa da linguagem**, como palavras-chave, identificadores, operadores, números, símbolos, etc.

Além de identificar essas unidades, o analisador léxico também **classifica cada token de acordo com sua categoria léxica**, por exemplo:

`int x = 10;`

Tokens gerados:

- `int → palavra-chave
    
- `x → identificador
    
- `= → operador de atribuição
    
- `10 → literal inteiro
    
- `; → delimitador

Esse processo elimina espaços em branco, comentários e outros elementos irrelevantes para a estrutura sintática, preparando a entrada para a próxima fase do compilador: a análise sintática.

Um analisador léxico normalmente retorna uma sequência de tokens no seguinte formato:

`<classificação, valor>`

- **Classificação**: o tipo do token (por exemplo: `id`, `op`, `num`, `kw`, `sep`).
    
- **Valor**: o conteúdo do token, útil especialmente para identificadores, números e strings.

---
### Ferramentas de Parsing

Existem ferramentas clássicas utilizadas para implementar a análise léxica, como o disponibilizados pela biblioteca Lark.

O **Lark** é um toolkit de parsing para Python que fornece **lexer**, **parser** e **transformadores de árvore** numa API unificada [GitHub](https://github.com/lark-parser/lark/blob/master/lark/lexer.py?utm_source=chatgpt.com). Ao instanciar um parser, você obtém internamente um lexer configurado pela gramática.

#### Sintaxe de `lex()`

```python
def lex(src: str) -> Iterator[Token]:     
	return ast_parser.lex(src)
```

- `src: str` indica que o parâmetro é uma **string** de código-fonte (type hint)..
    
- `-> Iterator[Token]` é uma **anotação de tipo** do módulo `typing`, significando que a função retorna um **iterador** de objetos da classe `Token` (definida pelo Lark).
	
- Internamente, `ast_parser.lex(src)` chama o método `lex()` do objeto `Lark`, que tokeniza o texto, aplicando a análise léxica de acordo com a gramática estabelecida.

```python
from lark import Token, Lark
from typing import Iterator

grammar = ""
ast_parser = Lark(grammar, parser = "lalr", lexer = "standard")

def lex(src:str) -> Iterator[Token]:
	return ast_parser.lex(src)

if __name__ == "__main__":
	entrada = "3 + 4 * (2 - 1)"
	print(f"Analisando: {entrada}")
	for token in lex(entrada):
		print(f"{token.type}:{token.value}")
```

Esse processo organiza o código bruto em tokens para facilitar a [[Compiladores - Análise Sintática]] do código.