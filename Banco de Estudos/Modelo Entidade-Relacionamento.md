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
#### Cardinalidade - Conjunto de Relacionamentos

Cardinalidade se define como restrição estrutural que rege os relacionamentos entre entidades. Dentro de um relacionamento, a cardinalidade estabelece a quantidade de vezes que uma entidade pode se repetir dentro do contexto.

![[Pasted image 20250403102733.png]]

Nesse contexto:

**Um para Um**: é uma relação onde a primeira entidade é instanciada apenas uma vez em relação à segunda entidade, assim como, a segunda entidade é instanciada apenas uma vez quando relacionada com a primeira entidade. Leitura:

	Uma ementa descreve apenas uma disciplina.
	Uma disciplina é descrita por apenas uma ementa.

**Um para Muitos**: é uma relação onde a primeira entidade só pode ser instanciada uma vez quando em relação com a segunda entidade. Enquanto isso, a segunda entidade pode ser instanciada N vezes quando em relação com a primeira entidade.

	Um professor pode tutorar várias turmas.
	Uma turma pode ser tutorada por apenas um professor.

**Muitos para Muitos**: é uma relação onde a primeira entidade pode ser instanciada N vezes quando em relação com a segunda entidade, assim como a segunda entidade em relação com a primeira.

	Uma pessoa pode se matricular em várias disciplinas
	Uma disciplina pode ser matriculada por várias pessoas.


Perceba que em todas as leituras seja na direção  de ida (->) ou voltando (<-) começa-se a análise utilizando o artigo um/uma. Isso acontece pois quando formos fazer um estudo de relacionamento devemos imaginar a situação de como uma unidade dessa entidade se relaciona com a outra.

Essa é outra maneira, mais precisa, de se representar uma cardinalidade. Ela necessita de dois valores:
( X , Y ) - sendo o X a representação da cardinalidade mínima, e o Y a cardinalidade máxima

![[Pasted image 20250403105216.png]]

Veja que nesse exemplo, nessa relação, um cliente pode emitir zero ou muitas compras, enquanto uma compra pode ser emitida por um e somente um cliente. Note que nessa relação não existe a chance de uma compra ser emitida por zero clientes.

