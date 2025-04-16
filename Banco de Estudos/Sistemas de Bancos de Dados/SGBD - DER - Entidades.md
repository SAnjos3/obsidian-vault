#### Entidade - Definição

- **CE**: Conjunto de Entidades

	Coleções de entidades que têm a mesma estrutura e o mesmo significado na modelagem. (estrutural e semanticamente iguais)

	- **Entidades**: são unidades usadas para representar "coisas", objetos, pessoas, organizações e muitas outros exemplos do mundo real. Entidade é uma unidade abstração de aspectos da realidade. O MER não trata entidades de maneira individual, mas sim em conjuntos, e relacionamentos.
	
	- Notação de Entidades: Retângulos
#### Entidade Fraca

Uma entidade é considerada fraca quando não tem atributos que possam identificá-la univocamente na SEMÂNTICA do domínio de aplicação. Em uma representação mais simples, uma entidade fraca poderia ser representada como um atributo composto e multivalorado de outra entidade.

-  não tem chave (semântica) própria

 Sua identificação depende de um relacionamento com uma entidade de outro conjunto (chamada de owner).

Chave Parcial: um ou mais atributos de CEs Fracas que podem identificar univocamente as entidades fracas relacionadas a um mesmo owner
#### Restrição de Participação

Pode ser de dois tipos:

- **Participação Total**: Refere-se a relacionamentos entre entidades onde caso uma desapareça, a existência da outra também deixa de fazer sentido no determinado contexto. Pode ser chamado de **Dependência Existencial**.

- Notação DER: linha dupla conectando o CE ao CR

![[Pasted image 20250408232313.png]]

	Exemplo: Uma disciplina pode existir sem estar associada a um Curso? Toda entidade **Disciplina** deve obrigatoriamente participar de um relacionamento "PPossui" com a entidade **Curso**

- **Participação Parcial**: Ocorre em relacionamentos onde uma entidade pode existir sem estar associada a outra.
- Notação DER: linha simples conectando o CE ao CR.

![[Pasted image 20250408232441.png]]
