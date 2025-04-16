Quando fala-se sobre ponteiro, é importante levar em consideração o tamanho dos tipos de variáveis em C.

- **Char**: 1 byte - 8 bits de tamanho
- **Int**: 4 bytes - 32 bits de tamanho
- **Float**: 4 bytes - 32 bits de tamanho
- **Double**: 8 bytes - 64 bits de tamanho 
- **Long**: linux - 64 bits em uma máquina AMD 64
	- Depende da Arquitetura - Usar long long como solução

O aspecto onde ponteiros e os tipos de variáveis se relacionam é na maneira como os dados são armazenados na memória. 

![[EDA - Alocação de memória em C#Regiões da Memória]]

Na linguagem C, ponteiros são denominado pelo `*` . A variável do tipo ponteiro, se estiver rodando em uma arquitetura de 64 bits, terá 8 bytes de tamanho na memória,  e essa variável irá armazenar um endereço, um endereço para outro espaço de memória.

`int *a, b;
`a = &b; 

Nesse caso, o ponteiro `a` armazena o endereço da variável `b`. Isso acontece pois o comando `&` indica o endereço de algo.

#### **Referenciar e Desreferenciar**

```c
int b;
int *a;
a = &b; // Nesse caso há uma referência ao endereço de B.
*a = 15; //Nesse caso eu estou desreferenciando o endereço.
```

A segunda operação é semelhante à seguinte lógica matemática:

	Analogia Lógica de Matemática: -(-a) = a  
	Funcionamento na Linguagem C: *(*a) = b -> *(&b) -> b = 15 

Assim como negativar um valor que já é negativo o torna positivo, tem-se que referenciar uma referência de endereço é equivalente a desreferenciar.

#### Aritmética de Ponteiros

**Aritmética de ponteiros** refere-se à capacidade de **navegar pela memória** somando ou subtraindo **unidades do tipo apontado** pelo ponteiro. 

	obs: Isso não significa que o espaço alocado irá aumentar.

  Isso quer dizer que, caso o ponteiro seja do tipo inteiro:

	int *a;
	(a + 1)

Nesse momento, navega-se pela memória mais 4 bytes, que é o tamanho de uma unidade do tipo inteiro. Seguindo essa linha lógica, caso essa operação seja aplicada:

	(a + 5)

Tem-se uma navegação equivalente a:
	5 x Int -> 5 x 4 bytes -> 20  bytes

A mesma lógica se aplica a diferentes tipos de variável:

	char *c
	(c + 1)

Equivalente à uma navegação de mais 1 byte.
