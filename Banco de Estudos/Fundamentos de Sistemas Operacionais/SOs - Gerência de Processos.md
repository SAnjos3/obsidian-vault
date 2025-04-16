A gerência de processos é de suma importância para abordar a maneira como o sistema operacional mantém diversos processos ativos simultaneamente no computador. É a partir dessa gerência que sem mantém a ilusão de múltiplos processos sequenciais em uma máquina com uma CPU.

Sobre a Gerência de Processos, algumas informações são relevantes. Dentre elas temos 
#### Troca de Contexto

Refere-se a operação de salvamento dos registradores de um processo e posterior restauração de registradores de outro processo. Isso permite que vários processos compartilhem a CPU de maneira eficiente. 

1. O sistema salva o estado do processo atual (valores dos registradores, ponteiro de pilha, etc.).
    
2. Escolhe outro processo pronto para execução.
    
3. Carrega o estado do novo processo e transfere o controle da CPU para ele.

A multiprogramação conta com essa operação básica para trocas de processador entre os processos.

#### Interrupções e Vetor de Interrupção

As interrupções são eventos que permitem que a CPU interrompa a execução de um processo para atender eventos importantes, como entrada e saída de dados.

Cada dispositivo de hardware tem um endereço específico no **vetor de interrupções**, que contém as rotinas de tratamento associadas. Quando ocorre uma interrupção:

1. O hardware salva o estado do processo em execução.
    
2. O sistema operacional executa a rotina de tratamento de interrupção.
    
3. Após o atendimento da interrupção, o sistema retorna ao processo anterior ou escolhe outro processo para execução.

Todas as informações sobre processos em execução são armazenadas na **Tabela de Processos**, também conhecida como **Bloco de Controle de Processo (PCB - Process Control Block)**. Essa tabela contém diversas informações:

1. **Gerenciamento de Processos**
    
    - Identificador do processo (**PID**)
        
    - Processo pai (**PPID**)
        
    - Estado do processo (executando, pronto, bloqueado)
        
    - Contador de programa (**PC**)
        
    - Prioridade de execução
        
2. **Gerenciamento de Memória**
    
    - Ponteiro para os segmentos de código, dados e pilha
        
3. **Gerenciamento de Arquivos**
    
    - Arquivos abertos pelo processo
        
    - Diretório de trabalho

![[SOs - Estados de um Processo]]


Assim levando os conceitos acima em consideração, temos que a gerência e implementação dos processos ocorrem da seguinte maneira:

1. O processo P1 solicita a operação.

2. O SO altera o estado de P1 para bloqueado.

3. O SO escolhe um dos processos prontos (P2) e o coloca para executar.

4. A solicitação de P1 é atendida pelo hardware.

5. O hardware interrompe P2, salvando seu estado de execução na pilha.

6. O hardware acesso um endereço de memória física específico que contém o vetor de interrupções.

7. O vetor de interrupções contém funções de tratamento geradas por cada tipo de dispositivos.

8. A rotina de tratamento de interrupção é executada pelo SO.

9. Os registradores que foram empilhados pelo hardware são salvos na tabela de processo do P2.

10. A interrupção é tratada.

11. O processo P1 é colocado na fila de prontos 

12. O SO acessa a entrada da tabela de processos escolhido e carrega o conteúdo da tabela nos registradores de máquina (restauração).

13. O processo escolhido reinicia a execução.

[[SOs - Escalonamento de Processos]]
