```Machado e Maia: A criação de processos é essencial para a execução de múltiplas tarefas em sistemas operacionais modernos, garantindo a execução paralela de programas."```

Nesse contexto se ressalta a importância de se adotar uma gerência de processos eficiente.

#### Criação de um Processo

Segundo Tanenbaum um processo pode ser criado de quatro formas diferentes:

- Início do Sistemas: quando o sistema operacional inicializa, ele cria processos essenciais para manter o funcionamento do sistema.

- Chamada de criação de processo feita por outro processo em execução: um programa pode criar novos processos realizando chamadas de sistema.

- Requisição do usuário: acontece quando o usuário executa um programa manualmente.

- Início de um job de lote: frequente em sistemas que processam tarefas automaticamente

Alguns processos executam em primeiro plano, ou seja, interagem com o usuário. Outros executam em segundo plano, conhecidos como daemons.

```Machado e Maia: "Os processos podem interagir com o usuário diretamente ou serem executados em segundo plano sem interação direta." ```

Primeiro Plano - Exemplos: Navegadores, editores de texto, jogos
Segundo Plano - Exemplos: No **Linux**, um **daemon** como `cron` executa tarefas agendadas. No **Windows**, o **"Spooler de Impressão"** gerencia a fila de impressão.

#### Hierarquia de Processos

![[Pasted image 20250402231441.png]]

Em alguns sistemas é comum que os processos forme uma estrutura hierárquica entre si. Essas estruturas são mais comuns em Unix/Linux.

``` Tanenbaum: "No Unix, processos são organizados hierarquicamente. Um processo pai cria processos filhos, formando uma árvore." ```

Nessa estrutura, todos os processos são descendentes do processo init.

No Unix existe apenas uma maneira de criar processos, que é através da clonagem. A partir de uma função, um clone é criado e posteriormente se torna necessário executar outra operação para alterar suas características:

- fork(); 
	- Clone idêntico ao processo que chamou
	- Normalmente, executa execve depois da chamada para mudar o “programa” em execução

No Windows, há uma função que trata o processo de criação quanto da carga do programa:

- **`CreateProcess()` já cria um processo e carrega o programa na memória**, sem precisar de um `fork()`.

#### Finalização de um Processo

Condição de Término de um Processo:

**Saídas voluntárias**: saídas que são motivadas pelo próprio processo que estava em execução.

- **Saída Normal**: quando um processo é encerrado sem código de erro. É considerada uma saída voluntária.

- **Saída por Erro**: acontece quando um processo é encerrado retornando um código de erro. É considerada uma saída voluntária.

**Saídas involuntárias**: saídas que são motivadas por aspectos externos ao processo em execução.

- **Erro Fatal**: acontece quando o processo em execução tenta realizar operações que ultrapassem os limites de permissão ou capacidade do mesmo. Ex: Segment Fault. É considerado um processo involuntário.

- **Cancelamento por Outro Processo**: ocorre quando um processo chama uma rotina de finalização para outro processo em execução. É considerado um processo involuntário.

**Hierarquia de Processos**:

Quando um processo é criado, ele mantem sua ligação de parentesco com o seu ascendente, ou seja, ligação com o processo que o gerou. Levando isso em consideração:

- Todos os processos são descendentes do processo init. 
- Alternativa: Systemd.

- O Windows não possui sistema de hierarquia


