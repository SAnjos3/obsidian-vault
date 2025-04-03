### **Introdução ao Estudo de Compiladores e Interpretadores**

As linguagens de programação são ferramentas essenciais para a construção de softwares, mas para que um código escrito por um programador possa ser executado pelo computador, ele precisa ser traduzido para um formato compreensível pela máquina. Essa tradução é realizada por **compiladores** e **interpretadores**, que desempenham um papel fundamental no desenvolvimento de software.

#### **1. O que são Compiladores e Interpretadores?**

- **Compilador**: Traduz todo o código-fonte para código de máquina antes da execução, gerando um arquivo binário executável. Exemplo: GCC para C/C++.
    
- **Interpretador**: Executa o código linha por linha, sem gerar um arquivo binário final. Exemplo: Python e JavaScript.
    
- Algumas linguagens utilizam um **modelo híbrido**, como Java e C#, que são compiladas para um bytecode intermediário e depois interpretadas por uma máquina virtual.
    

#### **2. A Importância dos Compiladores na Computação**

Compiladores não apenas traduzem código, mas também realizam otimizações para torná-lo mais eficiente. Além disso, são responsáveis por detectar erros antes da execução, garantindo um melhor desenvolvimento de software.

#### **3. Estrutura de um Compilador**

Um compilador é dividido em várias fases:

1. **Análise Léxica** – Identifica os componentes básicos do código (tokens).
    
2. **Análise Sintática** – Verifica se a estrutura do código segue as regras da linguagem.
    
3. **Análise Semântica** – Garante que as instruções fazem sentido.
    
4. **Geração de Código** – Converte o código para um formato executável.

Com o objetivo de fixar os conceitos de interpretador, será analisado e elaborado um interpretador de [[Brainfuck]]. Por se tratar de uma linguagem simples no quesito de quantidade de sentenças. 

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

