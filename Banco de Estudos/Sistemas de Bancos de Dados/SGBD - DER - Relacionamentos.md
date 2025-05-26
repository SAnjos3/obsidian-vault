
- **CR**: Conjunto de Relacionamentos

	São os relacionamentos entre entidades dos mesmos CEs.

	-  **Relacionamentos**: São associações entre as entidades do mundo real. Ligações que geram uma representação abstrata de operações que acontecem em algum contexto da realidade. Exemplo:

![[Pasted image 20250331085840.png]]

	- Notação de Relacionamentos: Losango

#### Papéis

Cada Conjunto de Entidade que participa de um Conjunto de Relacionamento, possui um papel nesse contexto. É um elemento opcional no MER, mas pode facilitar o entendimento da modelagem.

![[Pasted image 20250331095427.png]]

![[Pasted image 20250331095450.png]]

#### Auto-Relacionamento

É quando um relacionamento desempenha mais de um papel em um meso CR, em um caso, que ele necessita se relacionar consigo mesmo.

![[Pasted image 20250331095630.png]]

![[Pasted image 20250428002451.png]]

![[Pasted image 20250428002504.png]]
#### Grau do Conjunto de relacionamentos

Grau é o número de Conjunto de Entidades envolvidos em um relacionamento:

- 2 CEs - Relacionamento Binário 
- 3 CEs - Relacionamento Ternário 
- N CEs - Relacionamento n-ário

![[Pasted image 20250428002131.png]]

Cardinalidades possíveis para Ternários: 

-  1:1:1 
-  1:1:N 
-  1:N:M 
-  N:M:P