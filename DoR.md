O DoR é um conjunto de critérios que fala sobre quando um item, independente de ser uma história, tarefa ou épico, está pronto para a equipe de desenvolvimento trabalhar nela ou outro grupo no projeto. O que significa que é um acordo feito entre as partes interessadas – Product Owner, equipe de desenvolvimento, stakeholders, etc. o qual garante clareza, alinhamento e pré-requisitos para o trabalho poder ser feito. Os critérios para realização do DoR serão listados abaixo:

| **Critério**                | **Descrição**                                                                                                                                                                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Clareza da User Story**   | Cada funcionalidade deve ser descrita como uma user story no formato: _"Como [usuário], quero [ação] para [objetivo]"_. Exemplo: _"Como turista, quero ver minha localização em tempo real no mapa para não me perder durante o passeio"_. |
| **Critérios de Aceitação**  | Condições específicas e mensuráveis para validar a funcionalidade. Exemplo: _"A localização deve atualizar a cada 15 segundos com precisão ≤10 metros"_.                                                                                   |
| **Dependências Resolvidas** | APIs, designs e recursos externos necessários já estão disponíveis. Exemplo: _Integração com a API do Google Maps concluída_.                                                                                                              |
| **Recursos Alocados**       | Equipe e ferramentas definidas. Exemplo: _Desenvolvedor front-end (React Native) e biblioteca de geolocalização instalada_.                                                                                                                |
| **Riscos Mitigados**        | Problemas potenciais identificados e soluções propostas. Exemplo: _Fallback para redes móveis caso o GPS falhe_.                                                                                                                           |
| **Dados para Teste**        | Dados fictícios ou cenários prontos para validação. Exemplo: _Coordenadas de teste (São Paulo, Nova York)_.                                                                                                                                |
| **Validação do PO**         | Aprovação do Product Owner em reunião formal. Exemplo: _PO validou a priorização da precisão sobre velocidade_.                                                                                                                            |

### **Justificativa dos Critérios**

#### **1. Clareza da User Story**

- **Contexto:** O Touristeer precisa atender a diversos perfis de turistas (ex: grupos, seniores, moradores locais). User stories claras garantem que cada RF (como RF12 "Cadastrar grupos de viajantes") seja desenvolvido para resolver necessidades específicas.
    
- **Exemplo:** RF17 ("Notificações de início de rota") deve especificar o formato da notificação (e-mail/SMS) e o gatilho (15 minutos antes).
    

#### **2. Critérios de Aceitação**

- **Contexto:** Funcionalidades como RF04 ("Exibir rotas no mapa") exigem precisão técnica. Critérios como "trajeto colorido no mapa" evitam ambiguidades.
    
- **Alinhamento com RFs:** RF19 ("Obter localização atual") precisa de critérios como "precisão ≤10 metros em áreas urbanas".
    

#### **3. Dependências Resolvidas**

- **Contexto:** Integrações críticas (Google Maps para RF04, Firebase para RF12) devem estar contratadas antes do desenvolvimento para evitar atrasos.
    
- **Exemplo:** RF24 ("Conversor de moedas") depende de API de câmbio em tempo real (ex: Exchange Rates API).
    

#### **4. Recursos Alocados**

- **Contexto:** O RAD exige equipe multidisciplinar. Exemplo: RF21 ("Salvar PDF") precisa de dev front-end (React PDF Library) e back-end (Node.js para gerar arquivos).
    

#### **5. Riscos Mitigados**

- **Contexto:** Riscos como alta latência (RF04) ou falha de notificação (RF17) impactam a experiência do turista.
    
- **Exemplo:** Para RF23 ("Mudar idioma"), definir fallback para inglês caso a tradução falhe.
    

#### **6. Dados para Teste**

- **Contexto:** Testes realistas validam funcionalidades complexas. Exemplo: RF18 ("Adicionar grupo à rota") requer dados de grupos com 2-10 usuários.
    

#### **7. Validação do PO**

- **Contexto:** Validação contínua garante alinhamento com os objetivos do projeto (ex: RF22 "Compartilhar rotas por e-mail" deve incluir campos personalizados).
    
