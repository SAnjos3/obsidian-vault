BF também chamada de Brainfuck é uma linguagem de programação conhecida como exotérica, isso remete ao fato dela não ter sido projetada para ser útil ou eficiente, é mais como um desafio de programação. Programar nela tende a ser bastante complexo, porem q quantidade de comandos é bastante reduzida, assim, o intuito é construir um interpretador para essa linguagem a fim de fixar os fundamentos de compiladores.

Características:

- É uma linguagem Turing completa
- Foi criada para confundir e desafiar os programadores
- Não é útil para uso prático
- É muito mais fácil desenvolver compiladores e interpretadores para esta linguagem do que para outras linguagens
- O nome da linguagem é geralmente não-capitalizado

Como funciona 

- No brainfuck, o mundo é uma array unidimensional
- É possível navegar no array, incrementar/decrementar células dessa array
- É possível pedir input (apenas na forma de caracteres)
- É possível escrever output
- É possível executar loops (com uma condição imutável)

- Começa na primeira casa 
- " > " Mover para a posição da direita
- " < " Mover para a posição da esquerda
- " + " Incrementar o valor atual
- " - " Decrementar o valor atual
- " . " Imprime
- " , " Input
- " [ ] " Loop

Primeiro desafio: considerando a lista.
	5 - 2 - 0 - 0
A ideia é passar todas as unidades da primeira posição para a segunda opção.
` [ - > + < ] ` - O loop será executado ate q o valor da posição seja inicial do loop seja igual a 0. 

#### Lógica geral do brainfuck

S -> Caracter, exceto "[ ]".

Bf -> S, repetido 0 ou inúmeras vezes.

Fórmula ->

	Bf [ Bf ] Bf

Essa é uma tentativa de formular uma regra geral para representar essa linguagem de programação. Assim pode-se utilizar essa fórmula como base para elaborar compiladores e interpretadores. É possível visualizar mais exemplos em [[Introdução Compiladores]].