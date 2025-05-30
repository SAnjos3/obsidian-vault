O escalonamento circular (round robin scheduling) é um escalonamento do tipo preemptivo, projetado especialmente para sistemas de tempo compartilhado. 

Esse algoritmo é bastante semelhante ao FCFS, porém quando um processo passa para o estado de execução existe um tempo-limite para o uso contínuo do processador denominado fatia de tempo (time-slice) ou quantum.

![[Pasted image 20250525223955.png]]

No escalonamento circular, toda vez que um processo é escalonado para execução uma nova fatia de tempo é concedida. Caso a fatia de tempo expire, o sistema operacional interrompe o processo em execução, salva seu contexto e direciona-o para o final da fila de pronto. Esse mecanismo é conhecido como preempção por tempo.

### Vantagens

A principal vantagem do escalonamento circular é não permitir que um processo monopolize a UCP, sendo o tempo máximo alocado continuamente igual à fatia de tempo definido no sistema. 

No caso de sistemas de tempo compartilhado, onde existem diversos processos interativos concorrendo pelo uso do processador, o escalonamento circular é adequado.
### Desvantagens

Um problema presente nesta política é que processos CPU-bound são beneficiados no uso do processador em relação aos processos I/O-bound. 

Devido às suas características, os processos CPU-bound tendem a utilizar por completo a fatia de tempo, enquanto os processos I/O-bound têm mais chances de passar para o estado de espera antes de sofrerem preempção por tempo. Estas características distintas ocasionam um balanceamento desigual no uso do processador entre os processos.

### Problemática

Esse algorítimo se torna complexo no quesito da escolha das dimensões do time-slice. 

Caso a fatia de tempo tenha um valor muito alto, este escalonamento tenderá a ter o mesmo comportamento do escalonamento FIFO. 

Caso o valor do time slice seja pequeno, a tendência é que haja um grande número de preempções, o que ocasionaria excessivas mudanças de contexto, prejudicando o desempenho do sistema e afetando o tempo de turnaround dos processos.

---
### Tabela de Critérios

| Critério                      | Atende?                              | Justificativa                                                                                                                                                                                                                                                                                                                                                                        |
| ----------------------------- | ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Justiça                       | Sim                                  | É explicitamente descrito como um "Algoritmo justo". Ele garante que todos os processos tenham chances justas de uso do processador, dando a cada um um turno para executar. Isso evita a starvation (espera indefinida) para processos.                                                                                                                                             |
| Eficiência                    | OK (Depende do quantum)              | O objetivo geral é manter a CPU ocupada quando há trabalho. A eficiência do RR é sensível ao valor do quantum. Um quantum muito curto aumenta a frequência de trocas de contexto, gerando overhead e reduzindo a eficiência. Um quantum adequado permite alta eficiência.                                                                                                            |
| Minimizar o tempo de resposta | Sim (Especialmente para interativos) | É um algoritmo projetado para sistemas de tempo compartilhado, que visam oferecer baixo tempo de resposta a usuários interativos. Ao dar pequenas fatias de tempo a cada processo, ele fornece uma resposta inicial rápida, mesmo que o processo total seja longo. O tempo de resposta desejado é um critério para escolher o quantum.                                               |
| Minimizar o turnaround        | Não é o principal objetivo           | Embora possa distribuir melhor o tempo de CPU do que o FCFS, o SJF é o algoritmo focado em reduzir o tempo de turnaround médio. O overhead das trocas de contexto no RR pode, na verdade, aumentar o turnaround para tarefas curtas em comparação com algoritmos que não preemptam.                                                                                                  |
| Minimizar waiting time        | Não é o principal objetivo           | O RR proporciona um tempo de espera mais justo e evita esperas longas que podem ocorrer no FCFS, mas não é otimizado para minimizar o tempo médio de espera no mesmo sentido que o SJF é.                                                                                                                                                                                            |
| Maximizar throughput          | Não é o principal objetivo           | A preempção e as trocas de contexto inerentes ao RR adicionam um overhead que consome tempo de processador que poderia ser usado para executar instruções úteis. Embora evite que um processo longo monopolize a CPU (o que pode melhorar o throughput em cargas mistas comparado ao FCFS), o overhead pode impedir que ele atinja o throughput máximo teórico em todos os cenários. |
