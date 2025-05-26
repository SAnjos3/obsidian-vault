## Modelo Preemptivo

O escalonamento por prioridades é um escalonamento do tipo preemptivo realizado com base em um valor associado a cada processo denominado prioridade de execução. 

![[Pasted image 20250525231620.png]]

>**Observação**: Neste escalonamento, o conceito de fatia de tempo não existe, consequentemente um processo em execução não pode sofrer preempção por tempo.

No escalonamento por prioridades, a perda do uso do processador só ocorrerá no caso de uma mudança voluntária para o estado de espera ou quando um processo de prioridade maior passa para o estado de pronto. 

Neste caso, o sistema operacional deverá interromper o processo corrente, salvar seu contexto e colocá-lo no estado de pronto. Esse mecanismo é conhecido como preempção por prioridade. Após isso, o processo de maior prioridade é escalonado. Processo com mesmo valor de prioridade são escalonados conforme FIFO.
## Classificação de Prioridade

A prioridade de execução é uma característica do contexto de software de um processo, e pode ser classificada como estática ou dinâmica.

- **Prioridade Estática:** A prioridade estática não tem o seu valor alterado durante a existência do processo.

- **Prioridade Dinâmica:** A prioridade dinâmica pode ser ajustada de acordo com critérios definidos pelo sistema operacional

## Vantagens

O escalonamento por prioridade pode se tornar bastante útil, tanto em sistemas de tempo real e nas aplicações de controle de processo como também em aplicações de sistemas de tempo compartilhado, em que, às vezes, é necessário priorizar o escalonamento de determinados processos.

## Desvantagens

Um dos principais problemas no escalonamento por prioridades é o starvation. Processos de baixa prioridade podem não ser escalonados, permanecendo indefinidamente na fila de pronto.

Uma solução para este problema, possível em sistemas que implementam prioridade dinâmica, é a técnica de aging. Este mecanismo incrementa gradualmente a prioridade de processos que permanecem por muito tempo na fila de pronto.

---

## Tabela de Critérios

| Critério                      | Atende?                                                          | Justificativa                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Justiça                       | Não (Pode causar starvation)                                     | Este é um problema inerente ao escalonamento por prioridades. Processos de baixa prioridade podem não ser escalonados se processos de alta prioridade chegarem continuamente na fila de pronto.                                                                                                                                                                                                                                                                                               |
| Eficiência                    | Sim/OK (Objetivo geral do escalonamento)                         | O objetivo básico de manter a CPU ocupada quando há trabalho é atendido. A implementação preemptiva adiciona overhead devido às trocas de contexto, o que pode impactar ligeiramente a eficiência teórica em comparação com a versão não preemptiva, que tem menos trocas de contexto.                                                                                                                                                                                                        |
| Minimizar o tempo de resposta | Sim (Especialmente para alta prioridade)                         | Este algoritmo é eficaz para reduzir o tempo de resposta de processos de alta prioridade. Na implementação preemptiva, um processo de alta prioridade que chega ao estado de pronto interrompe imediatamente o processo de menor prioridade em execução, garantindo uma resposta rápida. Na implementação não preemptiva, o processo de alta prioridade que chega não causa preempção e deve esperar o processo atual liberar a CPU, resultando em um tempo de resposta potencialmente maior. |
| Minimizar o turnaround        | Não é o principal objetivo                                       | O escalonamento por prioridades prioriza a importância, não o tempo total. Processos de baixa prioridade podem ter tempos de turnaround muito elevados devido à espera.                                                                                                                                                                                                                                                                                                                       |
| Minimizar waiting time        | Não é o principal objetivo (Pode aumentar para baixa prioridade) | Similar ao turnaround, o tempo de espera pode ser muito longo para processos de baixa prioridade, levando a starvation.                                                                                                                                                                                                                                                                                                                                                                       |
| Maximizar throughput          | Não é o principal objetivo                                       | O objetivo principal é atender às prioridades. A starvation de processos de baixa prioridade pode reduzir o número total de tarefas concluídas (throughput)                                                                                                                                                                                                                                                                                                                                   |
## Alternativas

O escalonamento por prioridades também pode ser implementado de uma maneira não preemptiva. 

Neste caso, processos que passem para o estado de pronto com prioridade maior do que a do processo em execução não ocasionam preempção, sendo apenas colocados no início da fila de pronto.