Os **algoritmos de escalonamento** determinam a política usada para escolher qual processo será executado. 

Para o debate sobre escalonação, o conceito de preempção é muito importante.

	Preempção: Suspensão temporária da execução de um processo.

Os escalonadores podem ser classificados em dois tipos. São eles:
#### Não - Preemptivos 

São escalonadores onde nenhuma entidade externa pode retirar os recursos da CPU alocados em um processo. Quando um processo obtém o processador, ele roda até o fim ou até que ele peça uma operação que ocasione o seu bloqueio.
#### Preemptivos 

Diferente dos escalonadores não-preemptivos. Cada processo tem um **"fatiamento de tempo" (time-slice)**. Quando esse tempo acaba, o **SO força** a troca para outro processo. Isso acontece usando **interrupções de hardware**.

---
#### Algoritmos Não Preemptivos

- **[[SOs - Escalonamento FCFS (First Come, First Served)]]**: O primeiro processo a chegar é o primeiro a ser executado.
    
- **[[SOs - Escalonamento SJF (Shortest Job First)]]**: O processo com menor tempo de execução é escolhido primeiro.
    
#### Algoritmos Preemptivos

- **[[SOs - Escalonamento Round Robin (RR)]]**: Cada processo recebe um tempo fixo de CPU (quantum) antes de ser substituído por outro processo na fila. Versão preemptiva do escalonamento FCFS.
    
- **[[SOs - Escalonamento por Prioridade]]**: Cada processo recebe uma prioridade fixa ou dinâmica e os processos de maior prioridade são executados primeiro.

---
