 O Processo Unificado (UP) é um processo de engenharia de software que define um conjunto completo de atividades necessárias para transformar requisitos do cliente em um produto de software coeso.

Esse processo tem como característica ser iterativo e incremental, permitindo o que o desenvolvimento ocorra em fases sucessivas, cada um resultando no incremento do sistema.

![[Pasted image 20250401093427.png]]

O UP é configurado em quatro fases principais, e as ondas representadas na imagem referem-se ao esforço de implementar cada uma das disciplinas em suas respectivas fases:

1. **Iniciação (Inception):** Estabelece o escopo do projeto, elicitação inicial de requisitos, identifica os principais casos de uso e avalia a viabilidade do sistema proposto.

2. **Elaboração (Elaboration):** Detalha a maioria dos requisitos e casos de uso, estabelece e valida a arquitetura do software e detalha as estimativas de cronograma e custo. Nesta etapa são produzidos diversos artefatos como: documentação, diagramas, planilhas, etc.

3. **Construção (Construction):** Desenvolve o sistema de forma iterativa, adicionando funcionalidades a cada iteração, com foco na implementação e testes.

4. **Transição (Transition):** Entrega o sistema aos usuários finais, realiza ajustes conforme necessário e assegura que o sistema atenda às expectativas dos stakeholders.

As fases (etapas mostradas horizontalmente) servem de apoio para a execução de tarefas de cada um dos Fluxos de Trabalho (disciplinas), sendo seis da Engenharia de Software e de três para Apoio e Suporte:

- **Modelagem de Negócio** (ES): Os processos de negócio são elaborados de acordo com análise dos casos de uso. O objetivo é entender de forma muito clara o problema a ser resolvido. Caso necessário deve-se elaborar também análises de risco e viabilidade. Nessa fase a interação entre o analista e cliente é bastante acentuada. 

- **Modelagem de Requisitos** (ES): Nessa etapa devem ser extraídos os requisitos de forma que a proposta do sistema seja bem ressaltada. O alicerce é o profundo entendimento sobre o domínio do problema para uma eficiente modelagem de *Caso de Uso*. A extração dos requisitos a partir de um *Caso de Uso* gerará um artefato que evoluirá durante todo o projeto.

- **Análise e Design** (ES): Um modelo de projeto será criado e documentado em artefatos, como _Descrição da Arquitetura Básica do sistema_, _Protótipos de Funcionalidade e Interface_, _Diagrama de Classes_, _Diagrama de Estado, Diagrama de Iteração, Diagrama de Seqüência_, etc.

- **Implementação** (ES): No decorrer deste fluxo de trabalho, tenta-se gerar um sistema executável a cada iteração, além da implementação baseada nos artefatos criados no fluxo de _Análise e Desenho_.

- **Testes** (ES): um plano de testes é elaborado, definindo quais tipos de testes serão realizados. Nas fases de _Concepção_ e _Elaboração_ são feitos os testes de módulos e na fase de _Construção,_ os testes de integração.

- **Implantação** (ES): Neste fluxo de trabalho, um release do produto será criado, distribuído aos usuários e instalado no ambiente do cliente, ou seja, em seu local de trabalho.

	- **Gerência de Configuração e Mudança** (AS): Controla os artefatos e suas versões, garantindo que qualquer alteração corretiva ou evolutiva seja analisada antes da implementação. Conforme o projeto cresce, aumenta a complexidade do controle de mudanças, tornando essencial a rastreabilidade de requisitos, reavaliação por testes e atualização da documentação.
    
	- **Gerenciamento de Projeto** (AS): Define os artefatos utilizados no desenvolvimento e assegura a comunicação entre cliente e equipe. Inclui reuniões de entrega, revisões técnicas formais (RTF) e acompanhamento contínuo para garantir a correta implementação e evolução do projeto.
    
	- **Ambiente** (AS): Trata da infraestrutura necessária para o desenvolvimento, como ferramentas, organização de repositórios, backup de versões e ajustes ao longo das fases do projeto para garantir eficiência e segurança.

Esse modelo tem a característica de ser dirigido por casos de uso, isso significa que na captura de requisitos, esses são refinados e desenhados na forma de casos de uso da UML, o que torna os requisitos mais claros tanto para o cliente quanto para a equipe.

O Processo Unificado é focado em resolver os requisitos mais críticos no início do ciclo de vida do projeto, reduzindo as chances de falha.

Em resumo, o **Processo Unificado** oferece uma abordagem estruturada e flexível para o desenvolvimento de software. Essa flexibilidade se expressa em derivações evolutivas desse processo UP, são elas:

- [[MDS - Rational Unified Process (RUP)]]
- [[MDS - OpenUp]]
- [[MDS - Agile Unified Process (AUP)]]
