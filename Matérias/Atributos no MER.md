Atributos são valores que representam propriedades das Entidades e dos Relacionamentos no mundo real. Assim Considerando:

**Entidades**: são unidades usadas para representar "coisas", objetos, pessoas, organizações e muitas outros exemplos do mundo real. Entidade é uma unidade abstração de aspectos da realidade. O MER não trata entidades de maneira individual, mas sim em conjuntos, e relacionamentos.

 **Relacionamentos**: São associações entre as entidades do mundo real. Ligações que geram uma representação abstrata de operações que acontecem em algum contexto da realidade. 

Analisando os conceitos de entidades e relacionamentos, temos que, como unidades e operações do mundo real a serem estuadas possuem características, precisamos também representa-las na modelagem. E para isso, são usados os atributos no MER.

![[Pasted image 20250331090530.png]]

### Restrição de Unicidade 

A restrição de unicidade é um aspecto que todo conjunto de entidades deve possuir. Isso significa que conjuntos de entidades devem conter um atributo que o identifique de forma univocal.

Quando um atributo recebe essa responsabilidade, ele passa a ser considerado uma **Chave**.
A chave se torna o principal meio de acesso a essa entidade, pois a mesma é uma instância única em todo o banco de dados. 

![[Pasted image 20250331090839.png]]

Acontece quando uma única chave de uma entidade é o suficiente para representa-la.

![[Pasted image 20250331091907.png]]

Chave composta é usada quando uma entidade precisa de mais de um atributo, os quais em conjunto tornam a entidade em uma instância única no banco de dados.

### Atributos de Relacionamentos 

Existem cenários de entidades se relacionando entre si, onde um atributo não pode ser contido por apenas uma entidade, ele de forma simultânea pertence às duas entidades. Nesse casos, o atributo será contido pelo relacionamento dessas duas entidades, assim como no exemplo:

![[Pasted image 20250331092843.png]]

	Observação: os CEs sempre possuem atributos, mas os CRs podem existir mesmo que não possuam atributos próprios. A existência de CR é justificada pela associação de CEs.

### Tipos de Atributos

Simples vs Composto:

- **Simples**: é atômico, não pode ser dividido, é uma unica parte.
- **Composto**: é dividido em parte, possui sub-atributos.

![[Pasted image 20250331093641.png]]

- **Monovalorado**: assume um único valor para um/uma entidade/relacionamento em particular.
- **Multivalorado**:  assume mais de um valor para um/uma entidade/relacionamento em particular.

![[Pasted image 20250331093934.png]]

- **Armazenado**: atributo da entidade.
- **Derivado**: valor que pode ser obtido a partir dos valores de outros atributos da mesma entidade, ou de informação armazenada em seus relacionamentos.

![[Pasted image 20250331094153.png]]

Nesse caso, a idade pode ser calculada pela data de nascimento, por isso esse atributo é considerado derivado nesse contexto.