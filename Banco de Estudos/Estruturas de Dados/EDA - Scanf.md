Material de estudos relacionado com a função Scanf da linguagem de programação C. A estrutura do Scanf é definida por:

```C
int scanf(const char *format, ...)
```

Primeiro, é interessante notar que o scanf é uma função de tipo inteiro, isso porque ela retorna um número referente a quantos caracteres foram lidos corretamente.

Sobre a estrutura da função, o componente format refere-se a um conjunto de diretivas que indicam para o scanf qual tipo de entrada vai ser lida. Dentre esses formatos, temos:

- Whitespace: No geral, indica caracteres que geram algum espaço em branco na formatação.
	- Espaço
	- Tab
	- \v - Espaço Vertical
	- \n - Quebra de linha
	- \r

- Normais: Refere-se a todos os caracteres que não são especiais.

- "%" : Indica início de comando para formatação da entrada do scanf.

O "..." representa um conjunto de parâmetros para configuração da função Scanf. Porém é importante se atentar às funcionalidade de relacionadas ao consumir da função. Ela não opera apenas como um conversor de dados, mas tem essa propriedade de consumir.

“Consumir” significa **ler um caractere da entrada (teclado) e descartá-lo do buffer**, ou seja, ele **sai da fila** e **não será lido de novo**.

Exemplos:

```C
// Caso 1
scanf("abc")

// Caso 2
scanf("a b c")
```

Embora sejam parecidos, os dois casos são diferentes. No primeiro, o scanf esta programado para ler exatamente "abc", isso significa que caso a entrada seja algo como    "a bc" então a leitura falharia.

Enquanto isso, no segundo caso, o scanf esta programado para ler "abc" independente da quantidade de whitespace tiver entre os caracteres. Assim, em uma situação onde a entrada fosse "a    bc", esse scanf ainda seria capaz de fazer a leitura.

Essa funcionalidade permite que a entrada seja formatada da maneira como desejar. Por exemplo, imagine que você precisa ler dados que vêm num formato fixo de um arquivo ou de um usuário, tipo:

[User]
name=Joao
age=21

```C
char name[50];
int age;

scanf("[User]\nname=%s\nage=%d", name, &age);
```

- `[User]` → literal fixo
    
- `\n` → ignora qualquer whitespace, inclusive quebras de linha
    
- `name=` → literal fixo
    
- `%s` → converte a string pro `name`
    
- `\n` → ignora whitespace de novo
    
- `age=` → literal fixo
    
- `%d` → converte para inteiro


#### Scanf - Conversão

Dentro da estrutura so scanf, utilizamos o caracter especial "%" para indicar um formato o qual desejamos ter como destino da conversão. 

```C
<tipo> variavel;
scanf("%<indicador>", &variavel)
```
O indicador é o qual vai informar o formato de destino, e ele pode assumir os seguintes valores:

Decimais:
- `%d` - Ler números decimais com sinal
- `%u`- Ler números decimais sem sinal
-  `%i` 
- `%f %F` - Ler números flutuantes decimais

Hexadecimais:
- `%a %A`- Ler números flutuantes na notação hexadecimal
- `%x %X`- Ler números na base hexadecimal sem sinal

Octal:
- `%o` - Ler números na base octal sem sinal

Strings:
- `%c`- Ler um caracter
- `%s`- Ler uma string

Especiais:
- `%n`- Não consome nada, mas armazena em int o n° de chars já lidos
- `%p`- Ler ponteiros
- `[ ]` - **scanset**: lê um conjunto de caracteres definido entre `[` e `]`
	- `%[abc]` → lê um ou mais caracteres **contidos** em `a`, `b` ou `c`.
	- `%[^abc]` → lê um ou mais caracteres **não contidos** em `a`, `b` ou `c`.
	- Pode usar intervalos: `%[a-zA-Z0-9]`.