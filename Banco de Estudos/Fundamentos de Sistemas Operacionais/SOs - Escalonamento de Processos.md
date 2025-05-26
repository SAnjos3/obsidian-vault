O **escalonamento de processos** é o mecanismo que permite ao sistema operacional gerenciar a execução dos processos na CPU, garantindo um uso eficiente dos recursos e a execução correta das tarefas concorrentes.

### Motivação para o Escalonamento

Os sistemas computacionais modernos executam múltiplos processos simultaneamente, mas como a CPU pode executar apenas um processo por vez (ou um número limitado em sistemas multicore), é necessário um mecanismo que determine **qual processo será executado em determinado momento**.

O sistema operacional realiza essa escolha com base em políticas de escalonamento, priorizando eficiência, tempo de resposta e justiça na distribuição do processador.

![[Pasted image 20250407123135.png]]

Executando concorrentemente pode-se obter uma melhor utilização da CPU, já que em momentos onde a CPU estaria ociosa em algum processo, ela é redirecionada a outro processo. 

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
### [[SOs - Algoritmos de Escalonamento de Processos]]




