
Agregação se define como a associação de objetos componentes para compor um objeto composto. 

Na modelagem conceitual, essa ideia se aplica ao associar componentes como Conjuntos de Entidades e Conjuntos de Relacionamentos ou atributos. 

##### **Agregação de Atributos**:

Ao agregar atributos, se cria um atributo composto. [[DER - Atributos#Tipos de Atributos]]

![[Pasted image 20250408094449.png]]

##### **Agregação de Entidades e Relacionamentos** (Entidade-Associativa):

Processo de combinar entidades relacionadas por meio de um relacionamento e compor entidades agregadas (de nível abstrato mais alto)

![[Pasted image 20250408103248.png]]

Assim a entidade Paciente em relacionamento com entidade Médico se tornam um so componente associado. Esses componente passa a ter capacidade de ter seus próprios atributos e relacionamentos. Outra representação dessa associação é tornar elemento que os relaciona uma entidade, assim como no exemplo abaixo:

![[Pasted image 20250408102253.png]]

O relacionamento consulta passa a ser uma entidade o que permite o relacionamento Prescrição com a outra entidade Medicamento.

##### Indícios de uso da Agregação

- Mesmas instancias de um relacionamento ocorrem múltiplas vezes
		Exemplo: Um mesmo médico pode atender o mesmo paciente em **vários momentos diferentes**.
	- Nesse caso a instância médico e paciente, permanecem a mesma, então o que diferencia cada uma das interações?

- Caso um relacionamento possua um identificador próprio. Como título
		Exemplo: Um desenvolvedor se relaciona com um Cliente para desenvolverem um projeto, assim o projeto é o relacionamento. Mas o projeto tem um título.

- Necessidade de associar dois relacionamentos.
		Exemplo: Entrevistas e Resultados.