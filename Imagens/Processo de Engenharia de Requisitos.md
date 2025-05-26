### **1. Elicitação e Descoberta**

A fase de elicitação no Touristeer focou em identificar necessidades dos usuários e desafios do setor turístico, alinhando-se à proposta de personalização e flexibilidade. Foram utilizadas as seguintes técnicas:

- **Brainstorming**: Sessões colaborativas com a equipe para explorar funcionalidades como geolocalização em tempo real, curadoria de pontos turísticos e integração com APIs.
    
- **Entrevistas com Stakeholders**: Reuniões quinzenais com o cliente (via Microsoft Teams) para validar demandas, como a necessidade de roteiros curtos e acessibilidade.
    
- **Prompt IA**: Ferramentas de IA generativa auxiliaram na sugestão de features inovadoras, como recomendações baseadas em histórico de uso e clima local.
    

---

### **2. Análise e Consenso**

Os requisitos coletados foram refinados e priorizados com base nas limitações técnicas e nas metas do projeto:

- **Negociação**: Discussões mediadas pelo Gerente de Projeto (Rodrigo Amaral) para equilibrar expectativas do cliente (ex.: integração com Google Maps) e viabilidade técnica (ex.: uso do Firebase para autenticação).
    
- **MoSCoW**: Classificação dos requisitos em _Must-have_ (geolocalização, filtros avançados), _Should-have_ (avaliações em tempo real), _Could-have_ (integração com redes sociais) e _Won’t-have_ (tradução automática para idiomas estrangeiros).
    
- **DEEP**: Detalhamento dos requisitos para garantir _Detailed_, _Estimated_, _Emergent_ e _Prioritized_.
    

---

### **3. Declaração**

Os requisitos foram formalizados em documentos alinhados à estratégia RAD:

- **Documento de Visão do Produto**: Descreve o objetivo central do Touristeer (roteiros autônomos e personalizados) e os segmentos de clientes (turistas urbanos, viajantes de fim de semana, moradores locais).
    
- **Especificação de Requisitos ARO (Ambientais, Regulatórios, Organizacionais)**: Inclui conformidade com leis de turismo brasileiras, integração com APIs pagas (Google Maps) e restrições de orçamento (uso de tecnologias open-source).
    

---

### **4. Representação**

A modelagem dos requisitos foi realizada por meio de:

- **Diagramas de Ishikawa**: Usados na identificação inicial das causas da rigidez dos serviços de turismo (p. 3 do documento).
    
- **Prototipagem**: Desenvolvimento de interfaces navegáveis no Figma durante a fase de _Design do Usuário_ (05/05 a 25/05), validadas em reuniões semanais com o cliente.
    
- **Histórias de Usuário**: Estruturação no Trello usando o formato _Como [usuário], quero [funcionalidade] para [benefício]_. Exemplo: _Como turista, quero filtrar atrações por acessibilidade para planejar rotas inclusivas_.
    

---

### **5. Verificação e Validação**

A qualidade dos requisitos foi garantida através de:

- **Definition of Ready (DoR)**: Critérios como "Requisito validado pelo cliente" e "Integração técnica aprovada pelo desenvolvedor" para iniciar uma sprint.
    
- **Definition of Done (DoD)**: Checklist incluindo "Testes de usabilidade concluídos" e "Documentação atualizada no GitHub".
    
- **Revisão por Pares**: Sessões no Discord para análise de código (ex.: lógica de rotas otimizadas) e validação de UX.
    
- **WSJF (Weighted Shortest Job First)**: Priorização de tarefas no Trello com base no valor para o cliente, custo de atraso e esforço técnico.
    

---

### **6. Organização e Atualização**

Os requisitos foram gerenciados de forma ágil:

- **Backlog Refinement**: Reuniões semanais (quartas-feiras) para ajustar prioridades com base no feedback do cliente.
    
- **PBB (Product Backlog Building)**: Estruturação do backlog em épicos (ex.: "Integração com cultura local") e temas (ex.: "Promoção de atrações menos conhecidas").
    
- **Atualização Contínua**: Uso do GitHub para versionamento e do Trello para rastrear mudanças em tempo real.
    

---

### **Integração com o Cronograma RAD**

- **Análise de Requisitos (07/04 – 04/05)**: Elicitação, priorização MoSCoW e documentação inicial.
    
- **Design do Usuário (05/05 – 25/05)**: Prototipagem e validação com stakeholders.
    
- **Desenvolvimento Iterativo (26/05 – 04/07)**: Implementação guiada pelo DoD e feedback contínuo via WhatsApp/Trello.
    
- **Implantação (05/07 – 15/07)**: Testes finais com base em cenários reais (ex.: simulação de rotas em Salvador).
    

---

### **Ferramentas e Práticas-Chave**

- **Comunicação**: WhatsApp para discussões rápidas, Teams para validação formal, Trello para gestão de tarefas.
    
- **Tecnologias**: React e Node.js para desenvolvimento, Firebase para autenticação, Google Maps para geolocalização.
    
- **Métricas**: Satisfação do usuário (via avaliações no app), tempo médio de planejamento de rotas e redução de reclamações sobre rigidez de pacotes.
    

Este processo assegurou que o Touristeer atendesse às demandas de personalização e flexibilidade, mantendo alinhamento com os prazos e a visão estratégica do cliente.