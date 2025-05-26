O Definition of Done (DoD) é usado para garantir a qualidade e a consistência do trabalho entregue pela equipe a partir de uma definição clara e objetiva de critérios que precisam ser atendidos para que um item do backlog (User Story) seja considerado como concluído. A seguir, será apresentado os critérios escolhidos pela equipe para composição do DoD:

| **Critério**                | **Descrição**                                                                                                                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Implementação Completa**  | Código desenvolvido, integrado ao repositório principal e funcionando na plataformas-alvo.                                                                                     |
| **Testes Realizados**       | - Testes em unidades individuais do código de forma isolada.  <br>- Testes de integração com APIs (Google Maps, Firebase).  <br>- Testes de usabilidade com 5+ usuários reais. |
| **Documentação Atualizada** | - Comentários no código explicando lógicas complexas.    <br>- Documentação técnica de APIs e fluxos.                                                                          |
| **Revisão de Código**       | Peer review realizado, seguindo padrões de código (ex: ESLint para JavaScript) e boas práticas de segurança.                                                                   |
| **Performance Validada**    | - Tempo de resposta ≤2 segundos para ações do usuário.                                                                                                                         |
| **Conformidade Legal**      | - LGPD aplicada para coleta de dados (ex: avaliações de rotas).  <br>- Termos de uso e política de privacidade atualizados.                                                    |
| **Validação do Cliente**    | Aprovado pelo Product Owner em reunião formal, com demonstração da funcionalidade em ambiente de staging.                                                                      |

#### **1. Implementação Completa**

- **Por que?** Garante que a funcionalidade esteja integrada ao sistema e funcione em todas as plataformas (ex: RF04 "Exibir rotas no mapa" deve funcionar igualmente em iOS e Android).
    
- **Exemplo para RF19 (Obter localização):**
    
    - Geolocalização funciona offline com mapas pré-baixados.
        

#### **2. Testes Realizados**

- **Por que?** Assegura qualidade e confiabilidade.
    
    - **Testes unitários:** Evitam bugs em funcionalidades críticas (ex: RF24 "Conversor de moedas" deve converter valores corretamente).
        
    - **Testes de usabilidade:** Valida a experiência do turista (ex: RF12 "Cadastrar grupos de viajantes" deve ser intuitivo).
        

#### **3. Documentação Atualizada**

- **Por que?** Facilita a manutenção e o onboarding de novos desenvolvedores.
    
    - **Exemplo para RF21 (Salvar PDF):**
        
        - Documentar como o PDF é gerado (ex: uso da React PDF Library).
            

#### **4. Revisão de Código**

- **Por que?** Mantém a qualidade técnica e a segurança.
    
    - **Exemplo para RF17 (Notificações por e-mail):**
        
        - Verificar se dados sensíveis (e-mails) são criptografados.
            

#### **5. Performance Validada**

- **Por que?** Impacta diretamente a experiência do usuário.
    
    - **Exemplo para RF04 (Exibir rotas no mapa):**
        
        - Carregamento do mapa em ≤3 segundos mesmo com baixa conexão.
            

#### **6. Conformidade Legal**

- **Por que?** O Touristeer lida com dados de usuários (ex: RF11 "Avaliar rotas").
    
    - **Exemplo:**
        
        - Armazenar avaliações de forma anônima, se configurado pelo usuário.
            

#### **7. Design e Acessibilidade**

- **Por que?** Atende a requisitos não funcionais do projeto (ex: "interface minimalista").
    
    - **Exemplo para RF23 (Mudar idioma):**
        
        - Botões de idioma devem ser claros e acessíveis (alt text para ícones).
            

#### **8. Validação do Cliente**

- **Por que?** Garante que a funcionalidade atenda às expectativas do negócio.
    
    - **Exemplo para RF22 (Compartilhar rotas por e-mail):**
        
        - PO valida o formato do e-mail (incluindo mapa anexo em PDF).