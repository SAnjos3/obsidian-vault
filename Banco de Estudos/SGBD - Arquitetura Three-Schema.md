Um SGBD geralmente tende a ser dividido em duas partes:
- Esquema:
	- Definição (Metadados) 
	- Tende a ser estático na maioria de seu ciclo de vida

- Instância:
	- Manipulação
	- Dinâmica
#### Esquema

O esquema de um banco de dados é dividido em 3 níveis, daí o nome arquitetura three-schema. Possui as seguintes características que definem importantes tópicos na filosofia desse sistema:

- Múltiplas visões para os usuários: em um mesmo banco de dados usuários possuem visões diferentes de acordo com o nível de suas permissões.

- O armazenamento do esquema da base de dados em diferentes níveis de abstração.

- Possui um esforço dedicado em prover a independência entre os dados. 

Independência se define na capacidade de modificar o esquema em um determinado nível sem afetar o esquema do nível superior. Essa independência é garantida a partir da separação de níveis. 

![[Pasted image 20250408213813.png]]

- O 3° nível é um nível interno ou físico, ele se refere de fato ao banco de dados, onde estão armazenados os dados. Registra **como** os dados estão sendo armazenados. Baixo nível.

- O 2° nível descreve o esquema conceitual e lógico do banco dados. É nesse nível onde são estabelecidas as regras de negócio. Ele descreve como são as estruturas dos dados, não como eles serão armazenados.

- O 1° nível é semelhante ao 2° nível, porém com a implementação de hierarquias entre os usuários. Esse nível descreve a parte de dados em que cada grupo de usuários tem interesse. Assim se diz que ele é composto por Sub-Esquemas, que são as views.

A conexão entre esses níveis são feitos por meio de mapeamentos. Mapeamento externo/conceitual, mapeamento conceitual/interno.