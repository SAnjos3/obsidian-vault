Processo é um programa em execução acompanhado de valores de tempo de execução. Esse é um dos conceitos mais importantes para Sistemas Operacionais. 

**Processo*:

- Contém um Código Executável

- Possui Pilha de Execução: contendo valores de variáveis locais, endereços de retorno de chamadas de funções, parâmetros passados para funções, informações auxiliares para controle de execução.
	 - *Apontador para Pilha*: registrador da CPU que armazena em qual área a próxima da memória se encontra a pilha. O valor aponta para o endereço do topo da pilha.
	 
- *Contador de Programa*:  registrador da CPU que armazena qual a próxima instrução a ser executada. Essa instrução vem da memória onde o código do programa esta armazenado.

Existe uma diferença entre Programa e Processo. Abordando uma analogia de cozinha:

- Programa é a receita do Bolo (Passivo) Envolvem Algorítimos
- Processo é o ato de fazer o Bolo (Ativo) Envolvem uma Atividade
- Cozinheiro: CPU
- Ingredientes do Bolo: dados de entrada.
- Bolo: dados de saída

Processos são divididos em duas grandes partes (Ambiente e Execução).

- **Ambiente**: considera os fatores que um processo necessita para existir na memória e ser executado. 
	- **Espaço de Endereçamento**: código de programa, pilha, heap.
	- **Contexto de Software**

Existem dois tipos de processo, Processos de Ambiente e Processos de Execução.

Condição de Término de um Processo:

**Saídas voluntárias**: saídas que são motivadas pelo próprio processo que estava em execução.

- Saída Normal: quando um processo é encerrado sem código de erro. É considerada uma saída voluntária.
- Saída por Erro: acontece quando um processo é encerrado retornando um código de erro. É considerada uma saída voluntária.

**Saídas involuntárias**: saídas que são motivadas por aspectos externos ao processo em execução.

- Erro Fatal: acontece quando o processo em execução tenta realizar operações que ultrapassem os limites de permissão ou capacidade do mesmo. Ex: Segment Fault. É considerado um processo involuntário.
- Cancelamento por Outro Processo: ocorre quando um processo chama uma rotina de finalização para outro processo em execução. É considerado um processo involuntário.

**Hierarquia de Processos**:

Quando um processo é criado, ele mantem sua ligação de parentesco com o seu ascendente, ou seja, ligação com o processo que o gerou. Levando isso em consideração:

- Todos os processos são descendentes do processo init. 
- Alternativa: Systemd.

- O Windows não possui sistema de hierarquia

**Estados dos Processos**:

Embora processos sejam autossuficientes, muitas vezes eles necessitam acessar recursos do hardware, o que pode gerar desempenhos não muito eficientes. 

Ex: Ocorre situações onde um processo está realizando uma leitura de disco, ou leitura de rede, que são processos lentos.

Nesse contexto, se tornou perceptível ao longo da evolução de SOs que seria necessário criar uma melhor gerência desses processos. Para isso, criou-se estados de processo:

- Rodando 
- Bloqueado
- Pronto

![[Pasted image 20250402132749.png]]
 
(1) O processo bloqueia-se aguardando uma entrada

(2) O evento aguardado pelo processo ocorreu, pode-se iniciar a executar. 

(3) O tempo de posse do processador esgotou-se 

(4) O processo é escolhido pelo escalonador para executar


**Classificação de Processos**:

Processos podem ser classificados como:

- CPU-Bound: Possuem afinidade com a CPU, assim passam a maior parte do tempo usando a CPU, no estado rodando ou no estado pronto

- I/O-Bound: Possuem afinidade com Entrada e Saída, assim passam a maior parte do tempo em estado bloqueado por causarem muitas operações de Entrada e Saída.

Muitas aplicações de computadores pessoais que rodam em primeiro plano são exemplos de aplicações I/O Bound. Essas aplicações passam muito tempo em estado bloqueado, aguardando as informações dos usuários.