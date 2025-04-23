O termo inteligência artificial pode ser compreendido em partes:

- Inteligência: 

	Nesse contexto, o termo inteligência se refere à capacidade do ser humano de resolver tarefas cognitivas.
	- Tarefa Cognitiva: é qualquer atividade mental como pensar, lembrar, aprender, compreender.
	
	Com essa capacidades cognitivas, o ser humano é capaz de resolver problemas e tomar decisões. Porém há limitações na quantidade de dados que somos capazes de processar. 

Assim o termo inteligencia artificial se refere a programas computacionais que podem realizar tarefas cognitivas normalmente associadas a inteligência humana.

#### Técnicas de Desenvolvimento de IA

Existem duas técnicas principais usadas para projetar programas de IA:

- **Técnicas baseadas em regras**: 
	Se refere a programas de IA que seguem estritamente regras predefinidas para tomar decisões.

- **Técnicas de aprendizado de máquina**:
	Envolvem criação de programas de IA que são capazes de analisar dados para encontrar padrões e tomar decisões de forma independente.
	
	- O aprendizado de máquina é um subconjunto de IA voltado para o desenvolvimento de programas de computadores que podem analisar dados para tomar decisões ou fazer previsões. Os projetistas de IA geralmente usam ML em seus programas de IA porque ele não tem as limitações das técnicas baseadas em regras.
	
		![[Pasted image 20250419161641.png]]
	
	Há três abordagens comuns para o treinamento de programas de AM:

	- **Aprendizagem supervisionada**: nessa abordagem, é entregue a IA um conjunto de treinamento **rotulado de dados**, e o programa aprende com esses dados.
	
		- Conjunto Rotulado: Inclui dados rotulados ou etiquetados, que fornecem contexto e significado aos dados.


	- **Aprendizagem não supervisionada**: nessa abordagem, é entregue a IA um conjunto de treinamento **não rotulado de dados**, e o programa aprende com esses dados.
	
		- Conjunto Não Rotulado: possui dados que não possuem rótulos nem etiquetas.


	- **Aprendizagem por reforço**: nessa abordagem, é entregue a IA um conjunto de dados que permite que a mesma aprenda por tentativa e erro. O programa aprende a fazer isso ao ser recompensado por fazer boas escolhas que levam aos resultados desejados.
	
		- O programa aprende a fazer isso ao ser recompensado por fazer boas escolhas que levam ao s resultados desejados. No aprendizado por reforço, a "recompensa" é um **sinal numérico**:
		
			- **Recompensa Positiva:** Um número positivo indica que a ação levou o agente mais perto do objetivo desejado ou resultou em um resultado favorável.
		
			- **Recompensa Negativa (ou Penalidade):** Embora o foco principal seja na recompensa, um número negativo (uma penalidade) pode ser usado para indicar que a ação levou o agente para longe do objetivo ou resultou em um resultado indesejado.
			
			- **Recompensa Zero:** Uma recompensa zero (ou muito próxima de zero) indica que a ação não teve um impacto significativo no progresso em direção ao objetivo.


	Cada técnica de ML tem seus próprios pontos fortes e fracos. Dependendo do tipo de dados disponíveis e do que é necessário para resolver o problema específico, os designers de IA podem usar uma, duas ou todas as três técnicas para produzir uma solução alimentada por IA.
	
	Por exemplo, todas as três abordagens desempenham funções distintas nas ferramentas de IA para conversação. A Aprendizagem supervisionada equipa as ferramentas de IA para conversação com dados fundamentais de diálogo, permitindo que elas respondam adequadamente às dicas comuns de conversação. A Aprendizagem não supervisionada permite que elas interpretem nuances na linguagem, como coloquialismos, que ocorrem naturalmente em uma conversa. A Aprendizagem por reforço fortalece ainda mais essas ferramentas, permitindo que elas melhorem suas respostas em tempo real com base no feedback do usuário. Isso permite que elas se adaptem ao contexto da conversa e se envolvam em conversas naturais.


#### Ferramentas de IA

Ferramenta de IA é um software avançado por IA que pode automatizar ou auxiliar os usuários em várias tarefas. Uma ferramenta de IA pode ser classificada em:

- Ferramenta de IA Automatizada.
- Ferramenta de IA Integrada.
- Ferramenta de IA personalizada.

#### Modelos de IA

Toda IA é produzida tendo com base um conjunto de dados que sustenta os padrões e tomadas de decisões. O programa de computador treinado em conjuntos de dados para reconhecer padrões e executar tarefas específicas é chamado de modelo de IA.

- Algumas ferramentas de IA utilizam vários modelos de IA, trabalhando juntos para obter mais flexibilidade e realizar uma gama maior de tarefas.

**Processo de Treinamento de Modelos de IA**:

1. **Defina o problema** **a ser resolvido.** 
	Os designers e engenheiros de IA querem prever a chuva para ajudar as pessoas a se manterem secas durante o trajeto de ida e volta para o trabalho. Eles começam considerando os recursos e as limitações da IA antes de identificar uma solução de IA.
    
2. **Colete dados relevantes** **para treinar o modelo.**
	Os designers e engenheiros de IA coletam dados históricos dos dias em que choveu e dos dias em que não choveu nos últimos 50 anos.
    
3. **Prepare os dados** **para o treinamento.** 
	Os designers e engenheiros de dados de IA preparam os dados rotulando recursos importantes, como temperatura externa, umidade e pressão do ar e, em seguida, observando se choveu. Também é comum separar os dados em dois conjuntos distintos: um** _conjunto de treinamento_ e um _conjunto de validação_ para teste posterior.
    
4. **Treine o modelo.**
	Os designers e engenheiros de IA aplicam programas de aprendizado de máquina (ML) aos dados de treinamento preparados. AS os programas de ML analisam os dados e começam a aprender a reconhecer padrões que indicam a probabilidade de chuva, como a combinação de altas temperaturas, baixa pressão do ar e alta umidade.
    
5. **Avaliação do modelo.***
	Os designers e engenheiros de IA usam o Conjunto de validação que prepararam anteriormente para avaliar a capacidade do modelo de prever chuvas de forma precisa e confiável. A análise do desempenho de um modelo pode revelar possíveis problemas que afetam o modelo, como dados de treinamento insuficientes ou tendenciosos. Se houver algum problema, os projetistas e engenheiros de IA poderão revisitar uma etapa anterior desse processo para tentar uma abordagem diferente. Quando o modelo tiver um bom desempenho com seu Conjunto de validação, o processo continua na próxima etapa.
    
6. **Implantar o modelo.** 
	Quando os designers e engenheiros de IA estão satisfeitos com o desempenho do modelo, eles o implantam em uma ferramenta de IA - ajudando as pessoas da cidade a se manterem secas no caminho para o trabalho!