Threads em Modo Kernel (TMK), também conhecidos como **Kernel-Level Threads (KLT)**, são gerenciados diretamente pelo núcleo do sistema operacional. Toda a criação, sincronização, escalonamento e eliminação de threads ocorre por meio de **chamadas ao sistema (syscalls)**, que acessam rotinas específicas do kernel responsáveis por seu gerenciamento.

![[Pasted image 20250526104312.png]]

Nesse modelo, o sistema operacional tem **conhecimento individual de cada thread**, o que permite realizar o **escalonamento e gerenciamento independentes** entre elas, mesmo que pertençam ao mesmo processo. Isso permite que, em ambientes com múltiplos processadores, diferentes threads do mesmo processo sejam **executadas em paralelo real**, aumentando significativamente o desempenho de aplicações concorrentes.

**Vantagens:**

- **Aproveitamento real de múltiplos núcleos**, com possibilidade de execução paralela de várias threads de um mesmo processo em diferentes UCPs (Unidades Centrais de Processamento).
    
-  **Individualidade de Threads**, caso uma thread for bloqueada (por exemplo, em uma operação de E/S), as demais podem continuar sendo executadas, já que o kernel gerencia cada thread separadamente.
    
- **Integração direta com o sistema operacional**, permitindo maior controle sobre prioridades, preempção e escalonamento baseado em tempo real.

**Desvantagens:**

- **Troca de contexto mais custosa**, pois envolve a transição entre o modo usuário e o modo kernel (mudança de privilégio), o que gera maior sobrecarga e impacto no desempenho.
    
- **Maior complexidade na implementação do sistema operacional**, já que ele precisa gerenciar diversas estruturas adicionais, como pilhas, contextos e estados de execução para cada thread.
    
- **Desempenho inferior em operações frequentes de criação ou sincronização de threads**, em comparação com threads em modo usuário, especialmente em aplicações com muitas trocas de contexto.