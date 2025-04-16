É uma extensão à busca indexada por chave:

- É melhor adequada para aplicações de busca mais típicas quando não temos chaves que casam exatamente com os índices.

Algorítimos de busca baseados em Hashing são divididas de duas partes:

1.  Computar a função hash que transforma a chave de busca em um endereço da tabela
	- Idealmente chaves diferentes resolverão para endereços diferentes.
		- Mas é frequente que uma ou mais chaves resolvam para o mesmo endereço.

2. Trata colisão: processo que processa a questão das chaves que resolvem para o mesmo endereço.
	-  Um dos métodos de colisão é o uso de listas encadeadas:
		- Útil em situações que não se prevê o números de chaves de busca.
		- Os outros dois métodos de tratamento de colisões obtém melhor resultado com seus itens armazenados em um vetor fixo.

Hashing é um bom exemplo de "time-space-trade-off":

- Se não tivesse limite de memória, então faria-se a busca com apenas um acesso à memória usando a chave como um endereço de memória, como uma busca indexada pela chave.

- Se não tivesse limite de tempo, usaria-se a menor quantidade de memória e faria-se busca sequenciais.

Hashing provê um balanceamento entre os dois extremos apenas ajustando o tamanho da tabela, sem precisar reescrever código ou escolhendo outros algorítimos.

Hashing é um problema clássico de computação: Os algorítimos são bem estruturados, em profundidade e diversidade.
- Busca e inserção ficam com tempo constante

Porém há problemas:
- O tempo de execução depende do tamanho da chave, podendo ser impraticável para chaves muito compridas
- Não há implementação eficiente para "sort" e "select".

Funções Hash:
- Se existe uma tabela que armazena N itens, precisa-se de uma função que transforme chaves em inteiros.
	[ 0, N-1]

- Uma função hash ideal é fácil de computar e possui uma distribuição que se aproxima de uma função aleatório.

- A função hash é dependente do tipo de chave
	- Precisa-se de funções diferentes para tipos de chaves diferentes.

- Ideia simples para números em ponto flutuante:

	- Chaves são números maiores que 0 e menores que 1. Basta multiplicar por N e arredondar para o inteiro mais próximo para pegar um endereço entre 0 e N-1.
	
	- Generalizando: As chaves são números em ponto flutuante maiores que "s" e maiores que "r" para qualquer "s" e "t" que sejam fixos.
		- Re-escalamos a chave subtraindo por "s" e dividindo por "t-1", colocando entre 0 e 1, então multiplicamos por N.

- Se as chaves são números inteiros de "w" bits, então podemos converter para números em ponto flutuante dividindo por 2^w para obter números  em ponto flutuante entre 0 e 1, depois multiplicamos por N.

	- Problema: Só funciona para hash se as chaves forem distribuídas uniformemente no intervalo, por o valor hash é d

- O algorítimo mais comum e mais simples para chaves inteiras de "w" bits.
	- Escolhe-se um tamanho M para a tabela que seja um número primo
	- Para qualquer chave "K", computar o resto dividindo K pro N, ou:
		`h(k) = k mod N"

- Também podemos usar hashing modular para chaves em ponto-flutuante
	- Se as chaves estão e um intervalo pequeno, re-escalamos para um número entre 0 e 1, multiplicamos por 2^w e depois fazemos mod N

- Quado a chave é maior que uma palavra. 