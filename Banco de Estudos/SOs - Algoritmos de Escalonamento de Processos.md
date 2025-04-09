Os **algoritmos de escalonamento** determinam a política usada para escolher qual processo será executado. Eles podem ser divididos em **não preemptivos** (onde um processo não pode ser interrompido até terminar) e **preemptivos** (onde um processo pode ser interrompido para dar lugar a outro de maior prioridade).

#### Algoritmos Não Preemptivos

- **FIFO (First In, First Out)**: O primeiro processo a chegar é o primeiro a ser executado.
    
- **SJF (Shortest Job First)**: O processo com menor tempo de execução é escolhido primeiro.
    
- **Escalonamento por Prioridade**: Cada processo recebe uma prioridade fixa e os processos de maior prioridade são executados primeiro.
    

#### Algoritmos Preemptivos

- **Round Robin (RR)**: Cada processo recebe um tempo fixo de CPU (quantum) antes de ser substituído por outro processo na fila.
    
- **Escalonamento por Prioridade Dinâmica**: As prioridades dos processos mudam ao longo do tempo com base em critérios como tempo de espera e tempo de execução.
    
- **Multinível com Realimentação**: Os processos são divididos em filas com diferentes níveis de prioridade, e podem mudar de nível conforme seu comportamento.

---
#### Critérios de Escalonamento

Ao se projetar um escalonador, devemos observar vários critérios que devem estar presentes em um bom algoritmo de escalonamento:

- **Justiça**: garantir que todos os processos terão chances justas de uso de processador. Não são chances iguais.

- **Eficiência**: quando existir trabalho a fazer, o processador deve estar ocupado.

- **Minimizar o tempo de resposta**: reduzindo o tempo dos usuários interativos, reduz o tempo entre a entrada de usuário e a resposta dada (não considera tempo total de execução)

- **Minimizar o turnaround**: reduzir o tempo desde o lançamento do processo até seu término. Soma de: tempo de espera por recursos (memória, processador, E/S) e tempo de utilização da CPU. Mais utilizado em processamento batch

- **Minimizar waiting time**: Esse critério visa minimizar o tempo de espera pela CPU

- **Maximizar throughtput**: Maximizar o número de tarefas executados em uma unidade de tempo


	`obs: Não é possível atingir todos esses critérios de escalonamento, muito são contraditórios entre si.`

---

##### 🔹 First Come First Served (FCFS)

O algoritmo FCFS atende os processos na ordem de chegada, ou seja, o primeiro processo que solicita a CPU será o primeiro a executá-la. É um algoritmo **não-preemptivo**, o que significa que, uma vez que um processo esteja em execução, ele continuará até terminar ou até que ele mesmo se bloqueie. A principal vantagem é sua simplicidade, porém ele pode causar longos tempos de espera se um processo com execução longa for o primeiro da fila. Não prioriza processos interativos e pode levar ao problema conhecido como **convoy effect**, onde processos curtos ficam presos atrás de um processo longo.

##### 🔹 Round-Robin (RR)

No Round-Robin, cada processo recebe um **quantum** (intervalo de tempo fixo) para executar. Se o processo não terminar dentro desse tempo, ele é colocado no final da fila de prontos e outro processo é escalonado. É um algoritmo **preemptivo**, justo, e muito usado em sistemas interativos. O principal desafio está em escolher um valor de quantum adequado: se for muito longo, o algoritmo se comporta como FCFS; se for muito curto, há perda de desempenho por excesso de trocas de contexto.

##### 🔹 Escalonamento por Prioridades

Nesse algoritmo, cada processo recebe uma **prioridade**, e o processo com a maior prioridade é executado primeiro. As prioridades podem ser **estáticas** (definidas previamente e fixas) ou **dinâmicas** (ajustadas em tempo de execução, por exemplo, favorecendo processos I/O-bound). Pode ser preemptivo ou não-preemptivo. Um problema comum é a **inanição** de processos com prioridade baixa, que podem nunca ser executados se houver um fluxo constante de processos com prioridades mais altas.

##### 🔹 Shortest Job First (SJF)

O SJF seleciona para execução o processo com o **menor tempo de execução estimado**. É ideal para minimizar o tempo de turnaround, sendo muito eficiente em sistemas batch. 
Contudo, requer conhecimento prévio do tempo de execução de cada processo, o que nem sempre é possível. Uma possível solução é estimar esse tempo com base em execuções anteriores. O algoritmo também sofre do problema de inanição, pois processos longos podem ser constantemente adiados se processos curtos continuarem chegando.