Processos heavyweight é uma das classificações dos processos em **relação ao custo de troca de contexto e da manutenção**. Se trata de um processo tradicional e possui as seguintes características:

- Cada processo possui seu próprio **espaço de endereçamento e contexto de execução**.

	```Tanenbaum: "Cada processo tem seu próprio espaço de endereçamento e roda como se fosse o único processo no sistema, mesmo que vários processos estejam ativos ao mesmo tempo."```

- O sistema operacional deve gerenciar completamente cada processo de forma independente. Ou seja, os processos são independentes entre si.

- Cada processo possui um único fluxo de controle.

- A troca de contexto é muito cara. Isso acontece porque nessas situações, se torna necessário salvar muitas informações (registradores, memória, tabela de páginas etc) para que posteriormente seja possível restaurá-las.  

- O processador é chaveado entre vários processos ativos, pois um único processador não pode executar todos ao mesmo tempo. Isso significa que o processador precisa alternar rapidamente entre os processos ativos.

	```Tanenbaum: "A CPU pode executar apenas um processo por vez, então o sistema operacional realiza a troca de contexto, suspendendo um processo e iniciando outro, dando a ilusão de paralelismo." ```

Para que todo essa operação ocorra de forma eficiente, é necessária uma [[SOs - Criação e Finalização de Processos]].

