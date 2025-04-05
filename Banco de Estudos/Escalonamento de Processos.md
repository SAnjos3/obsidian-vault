O **escalonamento de processos** é o mecanismo que permite ao sistema operacional gerenciar a execução dos processos na CPU, garantindo um uso eficiente dos recursos e a execução correta das tarefas concorrentes.

### Motivação para o Escalonamento

Os sistemas computacionais modernos executam múltiplos processos simultaneamente, mas como a CPU pode executar apenas um processo por vez (ou um número limitado em sistemas multicore), é necessário um mecanismo que determine **qual processo será executado em determinado momento**.

O sistema operacional realiza essa escolha com base em políticas de escalonamento, priorizando eficiência, tempo de resposta e justiça na distribuição do processador.

###  Objetivo do Escalonamento

O escalonador tem como principais objetivos:

- **Multiplexação da CPU**: alternar a execução entre vários processos;
    
- **Eficiência**: garantir que a CPU não fique ociosa sem necessidade;
    
- **Equidade**: distribuir o tempo de CPU entre os processos de forma justa;
    
- **Tempo de resposta otimizado**: reduzir a espera de processos interativos;
    
- **Melhor aproveitamento dos recursos**: evitando gargalos no sistema.
    

### Níveis de Escalonamento

O escalonamento ocorre em **diferentes níveis**, dependendo do momento da execução:

- **Escalonamento de Longo Prazo**: Decide **quais processos entram na fila de prontos**. Esse escalonador controla a taxa de admissão de novos processos no sistema e determina a carga geral do sistema.
    
- **Escalonamento de Médio Prazo**: É responsável pela **remoção temporária de processos da memória principal** (swap out) e sua reinserção quando necessário (swap in). Esse nível reduz a carga do sistema em momentos de sobrecarga.
    
- **Escalonamento de Curto Prazo**: Escolhe **qual processo da fila de prontos será executado na CPU**. Esse escalonador é acionado com maior frequência e é essencial para a eficiência do sistema.
    
- **Escalonamento de E/S**: Gerencia a **ordem de acesso a dispositivos de entrada e saída**, determinando a prioridade de operações de leitura/gravação.
    

###  Troca de Contexto

A **troca de contexto** ocorre quando o sistema operacional **substitui um processo em execução por outro**. Esse processo envolve salvar o estado do processo atual e restaurar o estado do próximo processo a ser executado. Esse mecanismo garante a continuidade da execução dos processos sem perda de informações.

### Algoritmos de Escalonamento

Os **algoritmos de escalonamento** determinam a política usada para escolher qual processo será executado. Eles podem ser divididos em **não preemptivos** (onde um processo não pode ser interrompido até terminar) e **preemptivos** (onde um processo pode ser interrompido para dar lugar a outro de maior prioridade).

#### Algoritmos Não Preemptivos

- **FIFO (First In, First Out)**: O primeiro processo a chegar é o primeiro a ser executado.
    
- **SJF (Shortest Job First)**: O processo com menor tempo de execução é escolhido primeiro.
    
- **Escalonamento por Prioridade**: Cada processo recebe uma prioridade fixa e os processos de maior prioridade são executados primeiro.
    

#### Algoritmos Preemptivos

- **Round Robin (RR)**: Cada processo recebe um tempo fixo de CPU (quantum) antes de ser substituído por outro processo na fila.
    
- **Escalonamento por Prioridade Dinâmica**: As prioridades dos processos mudam ao longo do tempo com base em critérios como tempo de espera e tempo de execução.
    
- **Multinível com Realimentação**: Os processos são divididos em filas com diferentes níveis de prioridade, e podem mudar de nível conforme seu comportamento.