O **escalonamento de processos** é o mecanismo que permite ao sistema operacional gerenciar a execução dos processos na CPU, garantindo um uso eficiente dos recursos e a execução correta das tarefas concorrentes.

### Motivação para o Escalonamento

Os sistemas computacionais modernos executam múltiplos processos simultaneamente, mas como a CPU pode executar apenas um processo por vez (ou um número limitado em sistemas multicore), é necessário um mecanismo que determine **qual processo será executado em determinado momento**.

O sistema operacional realiza essa escolha com base em políticas de escalonamento, priorizando eficiência, tempo de resposta e justiça na distribuição do processador.

---
###  Objetivo do Escalonamento

O escalonador tem como principais objetivos:

- **Multiplexação da CPU**: alternar a execução entre vários processos;
    
- **Eficiência**: garantir que a CPU não fique ociosa sem necessidade;
    
- **Equidade**: distribuir o tempo de CPU entre os processos de forma justa;
    
- **Tempo de resposta otimizado**: reduzir a espera de processos interativos;
    
- **Melhor aproveitamento dos recursos**: evitando gargalos no sistema.

![[Pasted image 20250407123135.png]]

Executando concorrentemente pode-se obter uma melhor utilização da CPU, já que em momentos onde a CPU estaria ociosa em algum processo, ela é redirecionada a outro processo. 

---
### Escalonadores

Para o debate sobre escalonação, o conceito de preempção é muito importante.
	`Preempção: Suspensão temporária da execução de um processo.`

Os escalonadores podem ser classificados em dois tipos. São eles:

---
#### Não - Preemptivos 
São escalonadores onde nenhuma entidade externa pode retirar os recursos da CPU alocados em um processo. Quando um processo obtém o processador, ele roda até o fim ou até que ele peça uma operação que ocasione o seu bloqueio.
#### Preemptivos 
Diferente dos escalonadores não-preemptivos. Cada processo tem um **"fatiamento de tempo" (time-slice)**. Quando esse tempo acaba, o **SO força** a troca para outro processo. Isso acontece usando **interrupções de hardware**.

--- 
#### Funcionamento do Escalonamento

 O processador tem um **relógio interno (clock)** que gera interrupções frequentes. O SO tem um **contador de tempo** que é diminuído a cada "tick" do clock. Quando o contador chega em 0, o **tempo do processo acabou** e outro processo assume a CPU.

---
####  Troca de Contexto

A **troca de contexto** ocorre quando o sistema operacional **substitui um processo em execução por outro**. Esse processo envolve salvar o estado do processo atual e restaurar o estado do próximo processo a ser executado. Esse mecanismo garante a continuidade da execução dos processos sem perda de informações.

### [[SOs - Algoritmos de Escalonamento de Processos]]




