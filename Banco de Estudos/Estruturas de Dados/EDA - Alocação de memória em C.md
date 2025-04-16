#### Regiões da Memória

- Stack -  Pilha

	- Liberada e alocada ao iniciar o programa.
	
	- Armazena toda variável local, dentro de uma função ou qualquer escopo sera armazenada na pilha(stack).
	
	- Uma pilha possui tamanho padrão de armazenamento de 7MB~8MB. Esse espaço é o limite de armazenamento, então caso um programa recursivo chegue em um nível de profundidade que ultrapasse esse armazenamento, um erro será retornado.
	
	- A pilha cresce de baixo para cima, então conforme são criadas variáveis, elas são sendo armazenadas na pilha de maneira sequencial.
	
	- Conforme o programa roda, as variáveis de escopos são desempilhadas da pilha e os valores de retorno empilhados.

- Heap - Amontoado de memória

	- A heap possui o tamanho de armazenamento equivalente ao limite de sua máquina.
	
	 - Não possui um sistema automático de alocação e liberação de memória. Esse processo deve ser feito manualmente pelo programa:
	 
		 - Alocação de memória:
			 - `malloc()`
			 - `calloc()`
			 - Etc
		
		- Liberação de memória:
			- `free()`

- Segmento de dados

	- Variáveis que são criadas em contexto global.

- Segmento read only

	- Variáveis que são criadas com o atributo `const`


#### Malloc()

Ao utilizar a função malloc(), se diz para o sistema operacional que o programa em execução necessita de uma quantidade N de bytes para armazenamento na heap.

`void *malloc ( size_t size )

Elementos da função:
- size_t : é um tipo de variável que cabe a maior quantidade de elementos que o sistema consegue armazenar.
- size: o tamanho de armazenamento necessário.

O valor de retorno dessa função é um ponteiro do tipo void que aponta para o início da memória alocada. Assim, caso seja necessário alocar espaço para um número inteiro:

```C
a = malloc(4);
a[0] = 2;
a[1] = 3;
```

Nesse contexto, a variável "a" receberá a referência para o início da memória alocada.
#### Free()

Ao utilizar a função free(), se diz ao sistema operacional para liberar o espaço de armazenamento referenciado pelo ponteiro.

```c
void free ( void *ptr );
free(a);
```

O ponteiro deve apontar para exatamente ao início do espaço armazenado pelo malloc().

#### Calloc()

Muito semelhante ao malloc(), porém ao inciar a a memória alocada, já se atribui o valor zero para todos os bytes disponíveis. No malloc() isso não acontece, tornando possível que seja encontrado lixos de memória nesse espaço de armazenamento. Enquanto o malloc apresenta esse problema, o calloc() a resolve atribuindo o valor 0.

Porém para que o calloc() realize isso, ele necessita de um novo parâmetro.

`void *calloc ( size_t nmemb, size_t size );

Elementos da função:
- size_t nmemb: refere-se a quantidade de elementos do tamanho `size`.
- size_t size: continua se referindo ao tamanho de bytes.

#### Realloc()

Quando se usa a função realloc(), significa pedir para o sistema operacional para atribuir um novo tamanho de memória para um espaço já alocado pelo malloc() ou calloc().

`void *realloc ( void *ptr, size_t size )

```C
int *a = malloc(300);

a = realloc( a, 600);
```
