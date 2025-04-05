Processo é um programa em execução acompanhado de valores de tempo de execução. Esse é um dos conceitos mais importantes para Sistemas Operacionais. 

**Processo**:

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

	Machado & Maia: "A execução de um processo corresponde ao seu contexto de hardware, enquanto o seu ambiente de execução corresponde ao espaço de endereçamento e ao contexto de software."

Tanenbaum também divide o processo em espaço de endereçamento, contexto de hardware e contexto de software. 

Pode-se dizer que as informações de controle do SO define o contexto de software, enquanto o contexto de hardware pode ser definido pelo estado dos registradores.. 

	Tanenbaum: "Um processo consiste de um código em execução, seus dados e a pilha, além de um conjunto de registradores da CPU e outras informações de estado armazenadas pelo sistema operacional."

Processo podem ser classificados em dois tipos de acordo com o custo de troca de contexto e manutenção, mais sobre esse conteúdo pode ser encontrado em [[Gerência de Processos em Sistemas Operacionais]]

- [[Processos Heavyweight]] 
- Processos Lightweight

**[[Criação e Finalização de Processos em Sistemas Operacionais]]**

**Classificação de Processos**:

Processos podem ser classificados como:

- CPU-Bound: Possuem afinidade com a CPU, assim passam a maior parte do tempo usando a CPU, no estado rodando ou no estado pronto

- I/O-Bound: Possuem afinidade com Entrada e Saída, assim passam a maior parte do tempo em estado bloqueado por causarem muitas operações de Entrada e Saída.

Muitas aplicações de computadores pessoais que rodam em primeiro plano são exemplos de aplicações I/O Bound. Essas aplicações passam muito tempo em estado bloqueado, aguardando as informações dos usuários.