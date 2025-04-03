### **Interpretador e Compilador: Conceitos Fundamentais**

Ambos são tipos de tradutores que convertem código-fonte escrito em linguagens de programação para um formato que o computador possa executar, mas fazem isso de maneiras diferentes.

1. **Interpretador:**
    
    - Traduz e executa o código linha por linha, sem gerar um arquivo separado de código de máquina.
        
    - Programas interpretados tendem a ser mais fáceis de depurar e modificar, mas podem ser mais lentos, pois a tradução ocorre em tempo de execução.
        
    - Exemplos de linguagens interpretadas: Python, JavaScript, PHP.
        
2. **Compilador:**
    
    - Traduz todo o código-fonte para código de máquina antes da execução, gerando um arquivo binário executável.
        
    - Isso resulta em maior velocidade na execução, mas o processo de compilação pode ser mais demorado.
        
    - Exemplos de linguagens compiladas: C, C++, Rust.

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

