Também conhecido como MER, o Modelo Entidade-Relacionamento foi criado por Peter Chen em 1976. E está voltado para a representação de aspectos estáticos, ou informações do domínio da aplicação.

Esse modelo é popular por características como:

- **Simplicidade**:  esse modelo tem como objetivo tornar aspectos complexos da aplicação em relacionamentos simples, o que gera o próximo tópico.

- **Expressividade**: o modelo traz uma visão clara e eficiente do problema. Isso é importantíssimo, levando em consideração que em cenários de bancos de dados deve-se encontrar erros o mais rápido possível, pois quanto mais tarde for, mais complicado será para resolver.

- **Intuitivo**: Por último, esse modelo é intuitivo, por trazer uma abstração e uma representação gráfica de conjuntos de informações que antes poderiam ser difíceis de visualizar.

#### Componentes de um Modelo Entidade-Relacionamento

- **CE**: Conjunto de Entidades

	Coleções de entidades que têm a mesma estrutura e o mesmo significado na modelagem. (estrutural e semanticamente iguais)

	- **Entidades**: são unidades usadas para representar "coisas", objetos, pessoas, organizações e muitas outros exemplos do mundo real. Entidade é uma unidade abstração de aspectos da realidade. O MER não trata entidades de maneira individual, mas sim em conjuntos, e relacionamentos.
	
	- Notação de Entidades: Retângulos

- **CR**: Conjunto de Relacionamentos

	São os relacionamentos entre entidades dos mesmos CEs.

	-  **Relacionamentos**: São associações entre as entidades do mundo real. Ligações que geram uma representação abstrata de operações que acontecem em algum contexto da realidade. Exemplo:

![[Pasted image 20250331085840.png]]

	- Notação de Relacionamentos: Losango
	
- [[Atributos no MER]]

#### Papéis

Cada Conjunto de Entidade que participa de um Conjunto de Relacionamento, possui um papel nesse contexto. É um elemento opcional no MER, mas pode facilitar o entendimento da modelagem.

![[Pasted image 20250331095427.png]]

![[Pasted image 20250331095450.png]]

#### Auto-Relacionamento

É quando um relacionamento desempenha mais de um papel em um meso CR, em um caso, que ele necessita se relacionar consigo mesmo.

![[Pasted image 20250331095630.png]]

