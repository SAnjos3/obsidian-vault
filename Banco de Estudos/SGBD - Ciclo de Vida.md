![[Pasted image 20250408220915.png]]

O ciclo de vida de um projeto se inicia no mundo real, nas necessidades encontradas em algum contexto da realidade. Essas necessidades vão ser coletadas e analisadas para serem elaborados os requisitos.

[[Requisitos de Software]] são a unidade atômica o qual o projeto se baseará. E eles vão ser divididos em dois lados. Na imagem, os requisitos funcionais promoverão a base para a aplicação. 

Do lado esquerdo, os requisitos de dados servirão como base para a produção do sistema gerenciador de banco de dados. 

Nessa anotação, o foco é no ciclo de vida de um SGBD. E nesse contexto temos essas etapas:

![[Pasted image 20250408221622.png]]

#### Projeto Conceitual - [[SGBD - Modelo Conceitual]]

- Esquema conceitual para a base de dados

- Níveis conceitual/lógico e externo de visão

- Baseado nos requisitos de dados 

- Objetivos:
	- Estrutura de base de dados
	- Semântica 
	- Relacionamentos
	- Restrições

#### Projeto Lógico - [[SGBD - Modelo Lógico]]

- Esquema lógico
	- Níveis conceitual lógico e externo / de visão

-  Mapeamento do modelo conceitual para o modelo do SGBD
	- Passo 1: mapeamento independente do SGBD específico, porém dependente do paradigma. ( Relacional, OO,  Relacional-Objeto )

	- Passo 2: ajustes de acordo com as características e restrições do modelo implementado por um SGBD específico.

Projeto Físico
- Esquema Físico
	- Nível Interno

- Estruturas físicas de armazenamento
	-  Organização de registros físicos 
	-  Índices 
	- Número de discos, processadores, memória...

- Critério
	- Tempo de resposta 
	- Espaço utilizado 
	- Número de transações

