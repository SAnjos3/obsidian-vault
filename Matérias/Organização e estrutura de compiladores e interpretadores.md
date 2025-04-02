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


Com o objetivo de iniciar a produção de um interpretador, será utilizada a linguagem python.

```python
#!/usr/bin/python3

import sys
import click #pip3 install click

class BF:
	def __init__(self):
		self.memory = [0] * 10_000
		self.index = 0

	def run(self,src: str):
		chars = iter(str)
		for c in src:
			match c:
				case ">":
					self.index += 1
				case "<":
					if self.index == 0:
						raise  IndexError 
					self.index -= 1
				case "+":
					self.memory[self.index] += (self.memory[self.index] + 1)%256
				case "-":
					self.memory[self.index] -= (self.memory[self.index] - 1)%256
				case ".":
					print(ord(self.memory[self.index]),end="")
				case ",";
					self.memory[self.index] = ord(click.getchar()) % 256
				case "[":
					cmd = []
					open_pares = 1
					# serve para ler o loop em brainfuck( [loop] )
					for c in chars
						if c == "]":
							open_pares -= 1
						if c == "[":
							open_pares += 1
							
						if open_pares == 0:
							break
						cmd.append(c)
					else:
						raise SyntaxError 
					body = "".join(cmd)
					# executa o codigo lido entre os colchetes
					while self.memory[self.index] != 0:
						self.run(body)
						
				case "]":
					raise SyntaxError
				
		
def main():
	vm = BF()
	filename = sys.argv[-1]
	with open (file, "r") as fd:
		source = fd.read()
	

if __name__ == "__main__":
	main()
```

Agora a ideia é produzir um compilador. Para isso, usaremos python para ler o código em Brainfuck e converte-lo para c.

```python
import click
template = """
#include<stdio.h>

int main(){
	char memory[10000];
	int index = 0;

	for(int i=0; i < 10000; i++){
		memory[i] = 0;	
	}
	
"""
class BF:
	def __init__(self):
		self.line = []

	def run(self,src: str):
		chars = iter(str)
		for c in src:
			match c:
				case ">":
					print("index += 1;")
				case "<": 
					print("index -= 1;")
				case "+":
					print("memory[index]++;)
				case "-":
					print("memory[index]--;")
				case ".":
					print('printf("%c",memory[index]); flush(stdin);')
				case ",";
					print("memory[index]=getchar();")
				case "[":
					print("while(memory[index] != 0){")
				case "]":
					print("}")
def main():
	vm = BF()
	filename = sys.argv[-1]
	with open (file, "r") as fd:
		source = fd.read()
	
	print(c_template)
	vm.run(source)
	print("return 0;")
	print("}")
if __name__ == "__main__":
	main()
				
```

