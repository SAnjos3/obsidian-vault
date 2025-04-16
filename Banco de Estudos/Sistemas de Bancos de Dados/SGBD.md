## Sistema de Gerenciamento de Banco de Dados

Um SGBD é composto por:

- Conjunto de dados:
	-Base de Dados, Tabelas e Índices, tuplas
	
- Conjunto de programas
	-Acesso e manipulação dos dados

É considerado um sistema de propósito geral, isso significa que independente de que tipo de informação esse sistema irá armazenar, ele fará seu papel.

- Manter um conjunto lógico e organizado de dados
- Armazenar grandes volumes de dados
- Permitir busca e atualização de dados
- Ser eficiente 
- Ser autônomo em relação às aplicações, existe independente dos outros programas que o usam.

![[Pasted image 20250330183246.png]]

A imagem demonstra como o SGBD funciona, por ser independente, diversas aplicações podem o utilizar de maneira simultânea. E ele é organizado em esquema e instância:

- Esquema como a imagem diz é o molde dos dados. É nesse esquema que é definido a maneira como os dados serão armazenados.
- Instância por sua vez são os dados propriamente ditos.

### Requisitos Fundamentais:

- Segurança
	- Física (mais comum no passado)
	- Lógica
		- Usernames e Passwords
		- Perfis de Usuário

- Integridade
	- Consistência
	- Validade
		- Restrições de Integridade: Definem o que é valido e o que não é. Exemplos:
			– Um funcionário não pode pertencer a mais do que um departamento. 
			– O preço de venda de um produto deverá ser superior ao seu custo. 
			– O código de cada produto deve ser único.

- Recuperação / Tolerância a Falhas
	- Transições Atômicas
		- Operações no banco de dados é atômica por considerar tanto as entidade quanto os relacionamentos como uma unidade. Assim em uma falha ou na entidade, ou nos relacionamentos, gera uma recuperação do todo.
	- Registros de Log
		- Descreve todas as operações realizadas.
	- Backup
		- Permite recuperação de dados afetados.

- Controle da Concorrência
	- Faz administração sobre operações simultâneas. Isso significa que caso esteja sendo realizado uma operação sobre um dado,  SGBD bloqueia essa linha de qualquer outra consulta até que a operação esteja concluída.
#### [[SGBD - Componentes]]
