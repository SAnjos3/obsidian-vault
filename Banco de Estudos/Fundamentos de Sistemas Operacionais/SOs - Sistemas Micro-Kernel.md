Os sistemas operacionais baseados em micro-kernel buscam minimizar as funções que são executadas no núcleo do sistema, assim como seu tamanho. 

Essa é uma abordagem que se contrasta, quando comparada com os [[SOs - Sistemas Monolíticos]], os quais possuem a maioria dos serviços do SO sendo implementados em seus próprios núcleos. Esse sistema funciona com um conceito de cliente-servidor:

**Cliente-Servidor**: nesse modelo, a maior parte das funcionalidades o SO passam a ser operadas no modo de usuário. E essas funcionalidades serão divididas basicamente em dois tipos de processo:

- **Processos-Cliente**: abordam as funcionalidades ligadas às aplicações dos clientes.

- **Processos-Servidores**: incluem a maior parte das funcionalidades do SO, como o gerenciamento de arquivos, controle de dispositivos, protocolos de rede e outros serviços de alto nível.

![[Pasted image 20250524234417.png]]

Essa abordagem permite uma separação modular que facilita a manutenção e atualização dos componentes individuais do sistema.

Para isso, existe um núcleo de Sistema Operacional reduzido que atua como servidor central, o qual é responsável por atuar como intermediário essencial, fornecendo abstração de processos e mecanismos de comunicação entre os processos (IPC) e funções de baixo nível para interação com o hardware.

#### **Funcionalidades que permanecem no microkernel (núcleo):**

- **Gerenciamento Básico de Processos e Escalonamento:**  
    O microkernel cuida da criação, término e escalonamento dos processos. Ele gerencia a troca de contexto e garante que os processos recebam tempo de CPU de forma justa.
    
- **Comunicação Interprocessual (IPC):**  
    Ele fornece os mecanismos básicos para que os processos se comuniquem entre si, permitindo que os servidores e clientes troquem mensagens de forma segura e controlada.
    
- **Tratamento de Interrupções e Acesso Crítico ao Hardware:**  
    Para garantir segurança e desempenho, o microkernel lida com interrupções e com as funções mais essenciais que exigem acesso direto ao hardware, como a resposta imediata a um evento de hardware.

#### Características dos Microkernels:

- **Comunicação por Troca de Mensagens:** Os processos interagem com o sistema operacional por meio de troca de mensagens, um método que facilita a implementação de sistemas distribuídos e melhora a modularidade.​
    
- **Adaptabilidade a Sistemas Distribuídos:** Devido à sua estrutura modular e ao uso de comunicação por mensagens, os microkernels são altamente adaptáveis a ambientes distribuídos, onde diferentes componentes do sistema podem estar localizados em máquinas distintas.​
    
- **Desafios de Implementação:** Apesar das vantagens, implementar um microkernel pode ser desafiador. Algumas operações de baixo nível, como carregar comandos nos registradores físicos, são complexas de realizar dentro desse esquema devido às restrições de acesso direto ao hardware impostas pela separação entre núcleo e servidores.​
    
- **Popularidade Relativa:** Embora a implementação de microkernels seja complexa, eles têm ganhado popularidade em certos contextos, especialmente onde a segurança, a modularidade e a estabilidade são prioritárias.
	
- **Isolamento de Falhas**: Esta é uma das vantagens mais significativas do modelo. No microkernel, se um servidor (por exemplo, o servidor de arquivos ou o servidor de memória) que executa em modo usuário encontrar um erro, ele poderá parar, mas o sistema operacional não ficará inteiramente comprometido.