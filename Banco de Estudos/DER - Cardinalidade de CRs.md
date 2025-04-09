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
