Threads em Modo Usuário (TMU), também chamadas de **User-Level Threads (ULT)**, são gerenciadas inteiramente no espaço do usuário, ou seja, **sem envolvimento direto do sistema operacional**. Para isso, utiliza-se uma **biblioteca de suporte à multithread**, responsável por fornecer mecanismos para criação, finalização, sincronização e escalonamento das threads dentro de um processo

![[Pasted image 20250526102705.png]]

Como o kernel **não tem conhecimento da existência dessas threads**, ele enxerga e gerencia o processo como se possuísse apenas **um único fluxo de execução** (processo). 

Todas as operações de troca de contexto entre threads, sincronização e gerenciamento de estado são feitas exclusivamente pela biblioteca no modo usuário.

**Vantagens:**

- **Troca de contexto muito rápida e eficiente**, pois não envolve chamadas ao sistema operacional nem transições entre modo usuário e modo kernel.
    
- **Flexibilidade no escalonamento**, já que cada processo pode adotar sua própria política de escalonamento de threads.
    
- **Portabilidade**, permitindo o uso de multithread mesmo em sistemas operacionais que não suportam threads no nível do kernel.

**Desvantagens:**

- **Chamadas bloqueantes afetam todo o processo**: se uma thread executa uma syscall bloqueante (como leitura de arquivo ou espera por socket), o kernel bloqueia o processo inteiro, impedindo que outras threads, mesmo prontas para execução, sejam executadas.
	
	>Para contornar isso, a biblioteca precisa oferecer **rotinas não bloqueantes** que simulem o comportamento desejado sem interromper o processo inteiro.
	
- **Sem paralelismo real em multiprocessadores**: como o SO só escala processos e não threads, todas as threads de um processo são executadas em um único núcleo por vez, mesmo que o sistema tenha múltiplos processadores disponíveis.
    
- **Gerenciamento complexo de sinais**: sinais como o temporizador (clock) chegam ao processo como um todo, não às threads individualmente, exigindo que a biblioteca intercepte e distribua corretamente os sinais — o que pode ser especialmente crítico em sistemas de tempo compartilhado (timesharing).

#### Chamadas Blocantes Solução

- **"Capa" de verificação** nas bibliotecas de threads:
    
    - Antes de chamar a função bloqueante, verifica se há outras threads disponíveis.
        
    - Se houver, troca para outra thread antes de bloquear.
        

**Observação:** Essa abordagem **gera overhead adicional** no sistema.