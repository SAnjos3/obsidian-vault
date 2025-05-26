No escalonamento shortest-job-first (SJF scheduling), também conhecido como shortest-process-next (SPN scheduling), o algoritmo de escalonamento seleciona o processo que tiver o menor tempo de processador ainda por executar. 

Dessa forma, o processo em estado de pronto que necessitar de menos tempo de UCP para terminar seu processamento é selecionado para execução.

![[Pasted image 20250525221234.png]]

> **Observação**: Não é possível precisar o tempo de processador previamente para cada processo. Assim uma estimativa é realizada com base em análises estatísticas de execuções passadas dos programas
### Vantagem

Na sua concepção inicial, o escalonamento SJF é um escalonamento não preemptivo. Sua vantagem sobre o escalonamento FIFO está na redução do tempo médio de turnaround dos processos. 
### Desvantagem

No SJF é possível haver starvation para processos com tempo de processador muito longo ou do tipo CPU-bound. Isso remete a situação onde um processo nunca entra na CPU, pois novos processos curtos continuam surgindo e sendo priorizados.

---
### Tabela de Critérios

| Critério                        | Atende?      | Justificativa                                                                                                                                                                                                                  |
|--------------------------------|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Justiça                        | Não          | É possível haver starvation (espera indefinida) para processos com tempo de processador muito longo ou do tipo CPU-bound, pois processos mais curtos são sempre priorizados.                                                  |
| Eficiência                     | OK           | A política SJF seleciona um processo para execução da fila de pronto, o que implica que o processador estará ocupado se houver processos prontos.                                                                            |
| Minimizar o tempo de resposta  | Parcialmente | O SJF tende a reduzir o tempo de resposta para processos curtos e interativos, pois prioriza menores bursts. No entanto, por ser não-preemptivo, um processo curto pode ter que esperar a conclusão de um processo longo.     |
| Minimizar o turnaround         | Sim          | O SJF foi projetado para sistemas em lote com o objetivo de reduzir o tempo de turnaround. Sua vantagem sobre o FIFO está na redução do tempo médio de turnaround dos processos.                                              |
| Minimizar waiting time         | Sim          | Ao executar os processos com menor tempo de processador primeiro, o SJF tende a reduzir o tempo médio de espera dos processos na fila de pronto.                                                                             |
| Maximizar throughput           | Sim          | Ao completar tarefas curtas mais rapidamente, o SJF permite que um maior número de tarefas seja executado em uma unidade de tempo.                                                                                           |

### Alternativas 

Uma implementação do escalonamento SJF com preempção é conhecida como escalonamento shortest remaining time (SRT scheduling). 

Nesta política, toda vez que um processo no estado de pronto tem um tempo de processador estimado menor do que o processo em execução o sistema operacional realiza uma preempção, substituindo-o pelo novo processo.