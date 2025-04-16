#### Generalização / Especialização

Esses conceitos estão relacionados à relação entre entidades genéricas e entidades específicas. O MER-X incluiu uma espécie de relacionamento  baseada em "Is-a", que remete a ideia de uma entidade ser parte da outra.

- Uma entidade genérica abstrai.
- Uma entidade específica especializa em subtipos.

#### Herança 

- Relação semelhante à uma herança em OO.
	-  Nessa relação, as entidades específicas herdam atributos e relacionamentos da entidade genérica.


![[Pasted image 20250407083709.png]]

Assim tanto os atributos da Entidade Pessoa, quanto seu relacionamento com a entidade Plano Saúde são herdados pelas entidades específicas Aluno, Professor, Funcionário.

#### Herança em Múltiplos Níveis

Ocorre quando uma mesma entidade é simultaneamente genérica e específica de outros CEs.

![[Pasted image 20250407090746.png]]

#### Casos de Especialização

##### 1. **Atributos Exclusivos para Certos Tipos**

Quando alguns atributos só fazem sentido para um subconjunto da entidade.
**Exemplo (no RPG):**

- Entidade: `Carta`
- Subtipos: `Monstro`, `Tesouro`, `Maldição`
- Atributo "nível_de_combate" só existe para Monstro, enquanto "valor_ouro" só existe para Tesouro.

![[Pasted image 20250408234009.png]]

##### 2. **Regras d\e Negócio Diferentes**

Quando os subgrupos têm comportamentos distintos no sistema.
**Exemplo:**

- Entidade: `Jogador`
- Subtipos: `JogadorHumano` e `JogadorBot`
- Um bot pode ter lógica automatizada de decisão, enquanto o humano não.

![[Pasted image 20250408234028.png]]

#### Múltiplas Especializações

Um mesmo CE participa como CE Genérico em mais de uma ocorrência de Abstração de Especialização:

![[Pasted image 20250408234204.png]]


#### Restrições da Abstração de Generalização

Em modelagem conceitual, a abstração de generalização pode ser complementada por restrições que definem como os subtipos (entidades especializadas) se relacionam com o supertipo (entidade genérica). As principais restrições são: disjunção, sobreposição, totalidade e parcialidade.

###### Restrição de Disjunção (Exclusão Mútua)

![[Pasted image 20250408234935.png]]

Essa restrição indica que uma instância do supertipo pode pertencer a **no máximo um** dos subtipos. Em outras palavras, os conjuntos de entidades especializadas são mutuamente exclusivos. Por exemplo, uma disciplina deve ser **somente** de graduação **ou** de pós-graduação, nunca as duas ao mesmo tempo.

###### Restrição de Sobreposição

![[Pasted image 20250408234958.png]]

Permite que uma instância do supertipo pertença a **mais de um** subtipo simultaneamente. Ou seja, os conjuntos especializados podem se sobrepor. Por exemplo, uma pessoa pode exercer simultaneamente as funções de secretário e bibliotecário. Essa restrição é útil quando subtipos representam papéis ou funções acumuláveis.

###### Restrição de Totalidade

![[Pasted image 20250408235020.png]]

Indica que **todas** as instâncias do supertipo devem estar presentes em **pelo menos um** dos subtipos. Ou seja, o supertipo é completamente particionado pelos seus subtipos. Por exemplo, toda disciplina deve obrigatoriamente ser de graduação, pós-graduação ou especialização.

###### Restrição de Parcialidade

![[Pasted image 20250408235040.png]]

Indica que **nem todas** as instâncias do supertipo precisam pertencer a um subtipo. Ou seja, pode haver entidades que não se enquadram em nenhuma das especializações. Por exemplo, uma pessoa pode exercer uma função que não está definida como subtipo no modelo, como gerente de RH.

