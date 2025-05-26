A restrição de participação pode ser dividida em duas categorias:

### Participação Total

Toda Entidade de um Conjunto de Entidades deve obrigatoriamente participar de pelo menos um relacionamento do Conjunto de Relacionamento.

- Pode ser chamado de Dependência Existencial: uma entidade só deve existir se estiver associada pelo menos uma vez a outra.
- Notação no DER: linha dupla conectando CE ao CR.
	![[Pasted image 20250428000440.png]]

### Participação Parcial

Nesse caso, nem todas as Entidades do Conjunto de Entidades necessitam participar de um CR. A Entidade pode existir sem estar associada a outra entidade.

- Notação no DER: linha simples conectando CE ao CR.
	![[Pasted image 20250428000708.png]]


### Entidade Fraca 

Não possui atributos que a identifiquem de forma única na semântica do domínio. Esse tipo de entidade necessita de outra para que possa ser identificada de maneira única. 

- Não possui chave primária própria.
- A entidade que fornece a identificação única é chamada de Owner.
- Possui uma chave parcial que junto ao relacionamento com o Owner, identifica a entidade fraca.
- Notação no DER: 
	- Entidade Fraca: retângulo duplo
	- Relacionamento Identificador: Losango duplo
	- Chave Parcial: sublinhado tracejado
	![[Pasted image 20250428001815.png]]
	