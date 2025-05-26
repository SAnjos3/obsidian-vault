No escalonamento first-in-first-out (FIFO scheduling), também conhecido como first-come-first-served (FCFS scheduling), o processo que chegar primeiro ao estado de pronto é o selecionado para execução. 

![[Pasted image 20250525215752.png]]

Quando um processo vai para o estado de espera, o primeiro processo da fila de pronto é escalonado. Todos os processos quando saem do estado de espera entram no final da fila de pronto

![[Pasted image 20250525220209.png]]

### Vantagens 

- **Simplicidade**: Este algoritmo é bastante simples, sendo necessária apenas uma fila, onde os processos que passam para o estado de pronto entram no seu final e são escalonados quando chegam ao seu início. 
	
- **Eficiente:** A CPU sempre será utilizada.

### Desvantagens

- **Imprevisibilidade:** principal problema é a impossibilidade de prever-se quando um processo terá sua execução iniciada, já que isso varia em função do tempo de execução dos demais processos posicionados à sua frente na fila de pronto.
	
- **Critério de Tempo de Espera:** pela prioridade ocorrer em relação a ordem de chegada, o tempo de espera e tempo de turnaround não são priorizados.
	
	- Caso A:
		(0 + 10 + 14) / 3 = 8   |   Tempo médio de espera.
		 
	- Caso B:
		(0 + 4 + 7) / 3 = 3,8    |   Tempo médio de espera.
	
	A diferença entre as médias é bastante significativa, justificada pela diferença dos tempos de processador entre os processos.
	
- **CPU-bound > I/O-bound:** processos CPU-bound levam vantagem no uso do processador sobre processos I/O-bound. No caso de existirem processos I/O-bound mais importantes do que os CPU-bound, não é possível tratar este tipo de diferença.

---
### Tabela de Critérios

| Critério                      | Atende? | Justificativa                                                                        |
| ----------------------------- | ------- | ------------------------------------------------------------------------------------ |
| Justiça                       | Não     | Um processo pode monopolizar a CPU, prejudicando outros.                             |
| Eficiência                    | OK      | A CPU sempre é utilizada, se houver trabalho disponível.                             |
| Minimizar o tempo de resposta | Não     | Caso um processo monopolize a CPU, os outros terão tempo de resposta alto.           |
| Minimizar o turnaround        | Não     | Tarefas longas podem ser executadas primeiro, aumentando o turnaround médio.         |
| Minimizar waiting time        | Não     | O tempo de espera não é considerado durante o escalonamento.                         |
| Maximizar throughput          | Não     | Se a primeira tarefa for longa, o tempo até completar a primeira termina sendo alto. |

### Alternativas

O escalonamento FIFO é do tipo não preemptivo e foi inicialmente implementado em sistemas monoprogramáveis com processamento batch, sendo ineficiente, se aplicado da forma original em sistemas interativos de tempo compartilhado. 

O algorítimo [[SOs - Escalonamento Round Robin (RR)| Round Robin ou Escalonamento Circular]]  é uma opção de implementação semelhante ao FCFS, porém com preempção.
