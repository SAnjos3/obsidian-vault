Essa anotação é referente a história e contexto cronológico de bancos de dados, porém é interessante acompanhar a [[Evolução de Sistemas de Bases de Dados]].
## Década 50 - Surgimento dos Computadores Comerciais

Nesse período começou a se tornar necessárias formas de armazenamento de dados de forma eficiente.

- O armazenamento era feito de maneira rudimentar, os programas eram escritos direto em linguagem de máquina.

- A manipulação de informação exigia uma lógica especifica para acessar e modificar os arquivos, tornando o armazenamento de dados complexo e específico para cada aplicação.

- Nesse período começou a surgir conceitos base para a computação, como sistemas operacionais, estruturas de dados (listas, filas, árvores), linguagens que permitiram um maior nível de abstração (Fortran e Assembly).

- 1959: Primeiro computador comercial a utilizar um disco rígido magnético como meio de armazenamento. Sistema RAMAC:
	- O termo **RAMAC (Random Access Method of Accounting and Control)** refere-se à tecnologia de **acesso aleatório** utilizada no disco rígido do sistema. Esse sistema tornou possível acessar uma informação diretamente no disco, melhorando em muito o processo que antes era sequencial de acordo com as fitas magnéticas.
	- O RAMAC foi um percursor para os sistemas modernos de armazenamento.

## Década 60 - Modelo Hierárquico

Nesta época, empresas começaram a lidar com grandes volumes de informações e perceberam que os sistemas baseados em **arquivos tradicionais** (como no RAMAC) eram limitados. Isso levou ao desenvolvimento de **sistemas de bancos de dados estruturados**, que ajudaram a organizar e recuperar dados de maneira mais eficiente.

- Conceituação SGBD (Sistema Gerenciador de Banco de Dados):
	- Software que facilita a **criação, organização, gerenciamento e manipulação de dados** dentro de um banco de dados. Ele atua como intermediário entre o usuário (ou aplicação) e os dados armazenados, permitindo acesso estruturado e seguro.
	- Começa-se então criar um planejamento antes de codar e estruturar o banco de dados

- Surgimento de Sistemas Hierárquicos: desenvolvido para ordenar os dados em formato de árvore.
	- Foi formalizado no **sistema IMS (Information Management System), criado pela IBM em 1966** para gerenciar informações da missão Apollo da NASA.
	- Integração com a linguagem COBOL (em alta na época).

## Década 70 - Modelo Relacional

O **modelo relacional** foi proposto pelo cientista da computação **Edgar F. Codd**, da IBM, em um artigo publicado em **1970** chamado _"A Relational Model of Data for Large Shared Data Banks"_.

**Principais ideias do modelo relacional:**

- Os dados devem ser organizados em **tabelas (relações)**.
    
- Cada tabela tem **colunas (atributos)** e **linhas (tuplas/instâncias)**.
    
- Para acessar os dados, basta realizar **consultas declarativas**, sem precisar conhecer a estrutura interna do armazenamento (diferente dos modelos hierárquico e em rede).
    
- Introdução do conceito de **chave primária** (identificador único de cada linha).
    
- Relações entre tabelas são estabelecidas através de **chaves estrangeiras**.
    
- Possibilidade de manipulação dos dados com **álgebra relacional** e, mais tarde, com **SQL**.

Após a proposta do modelo relacional, começaram a surgir **os primeiros protótipos de SGBDs** para testar essa abordagem. Os dois mais importantes foram:

####  INGRES (UC Berkeley, início dos anos 1970)

- Desenvolvido na **Universidade da Califórnia, Berkeley**, liderado por **Michael Stonebraker**.
    
- Utilizava o modelo relacional e introduziu conceitos de **otimização de consultas**.
    
- Foi um dos primeiros bancos de dados a influenciar o desenvolvimento do **PostgreSQL** no futuro.
    
- Tinha uma linguagem própria para consultas, que ajudou na criação do SQL.
    

####  Sistema R (IBM, 1974–1977)

- Criado pela **IBM** para testar as ideias do modelo relacional.
    
- Primeiro SGBD a implementar uma linguagem de consulta baseada em **álgebra relacional**, que mais tarde evoluiu para o **SQL (Structured Query Language)**.
    
- Influenciou fortemente o **Oracle**, que foi um dos primeiros bancos de dados comerciais relacionais.

Na mesma década ocorreu mais um avanço no que diz respeito à modelagem de banco de dados. O **Modelo Entidade-Relacionamento (MER)** foi introduzido por **Peter Chen** em **1976**. Ele foi criado para facilitar a modelagem de bancos de dados antes da implementação.

#### Principais conceitos do MER:

- **Entidades:** Representam objetos reais (como "Aluno", "Produto", "Pedido").
    
- **Atributos:** Características das entidades (como "Nome", "Preço", "Data de Nascimento").
    
- **Relacionamentos:** Como as entidades se conectam entre si (exemplo: um "Aluno" faz parte de um "Curso").
    
- **Cardinalidade:** Define quantas instâncias de uma entidade podem se relacionar com outra (1:1, 1:N, N:M).

## Década de 80 - Sistema R da IBM

Essa década marcou com o surgimento do primeiro **Sistema Gerenciador de Banco de Dados Relacional** - SGBDR de grande porte disponível para comercialização.

Pontos marcantes:
####  DB2 da IBM - Sistema R da IBM

-  **DB2** foi desenvolvido pela **IBM** como parte de um esforço para trazer o **modelo relacional** para ambientes corporativos de grande escala.
    
- Ele foi **lançado oficialmente em 1983**, um dos primeiros sistemas a oferecer **suporte completo ao modelo relacional** em uma **plataforma de grande porte** (mainframes).
    
- **DB2** foi baseado no **Sistema R da IBM**, um projeto de pesquisa iniciado nos anos 1970 para testar o modelo relacional, como já discutimos.
    
- Esse SGBD implementou a linguagem **SQL** (Structured Query Language) como a **linguagem de consulta** padrão para interagir com o banco de dados, tornando-se o primeiro grande SGBD comercial a adotar SQL oficialmente.
- SQL foi consolidado como padrão
- Transição de desenvolvimento de bancos de dados para  Modelos Orientados a Objetos


## Década de 90+

- SGBDs Orientadas a Objetos
	- Trata e armazena os dados em formato de objetos. Porém armazenar dados em formato de objetos traz certos prejuízos no quesito de desempenho.
- SGBDs Objeto-Relacionais
	- Armazena os dados de forma relacional, porem retorna eles em forma de objetos. Inclui o melhor dos dois modelos, o desempenho do modelo relacional com a interface dos modelos orientados a objeto.
- NOSQL Orientados a Documentos
	- Basicamente armazenam os dados dentro do sql ou em formato de xml ou em formato de json, por exemplo. Geralmente numa forma de hierarquia seguindo tags que já existem nesse tipo de documentos.
- NOSQL em Grafos
	- Armazena os dados em formato de grafos. Não possui um desempenho muito alto, mas possui muita expressividade, isso significa que esse modelo esta projetado para modelar e consultar dados altamente conectados de maneira clara e eficiente, daí a expressividade do modelo. Eles podem facilmente modelar e consultar estruturas de dados com múltiplas interconexões e relacionamentos complexos. Seu desempenho pode ser bom em casos onde a busca seja muito profunda e complexa, assim deve-se estudar o contexto e estrutura de dados antes de aplicar esse modelo.

# Evolução dos Sistemas de Informação

## Sistemas de Informação baseados em gerenciamento de arquivos

Ao invés de base de dados, ou banco de dados, as informações eram apenas organizadas em arquivos que eram elaborados em formato de diretórios. 

Cada unidade de uma organização naquela época possuía programas para organizar seus arquivos, e cada um era desenvolvido de acordo com aquele que o havia feito. E cada arquivo possuía sua estrutura de dados.

Nesse contexto o cenário a organização de arquivos facilmente se transformava em um caos dentro da organização. Dentre os problemas desse sistema de informação:

- Redundância e inconsistência entre os dados
	- Dados repetidos em sistemas diferentes, com estruturas desiguais. Informações sobre um mesmo aspecto, incoerentes entre si.

- Dificuldade de acesso
	- Para acessar um dado, seria necessário estudar a estrutura em que ele se encontra.

- Isolamento dos dados
	- Gerado por casos onde um dado se encontra apenas em uma máquina, gerando muitas vezes até o esquecimento do mesmo.

- Anomalias no acesso concorrente
	- No cenário de programas diferentes trabalhando encima de um mesmo dado, se tornava comum situações onde esse dado era corrompido.

- Segurança 
	- Nesse cenário de caos, a segurança dos dados não podia ser assegurada de acordo com os tópicos acima.

Nesse contexto surgiu a necessidade de um sistema de gerenciamento de estrutura, esse gerenciador era um middleware entre os arquivos e o banco de dados. Esse sistema convertia os arquivos em uma só estrutura.

A evolução desses sistemas de gerenciamento de estruturas evolui para os [[SGBD]].