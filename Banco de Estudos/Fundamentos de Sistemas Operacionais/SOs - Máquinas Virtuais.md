Um Sistema Operacional baseado em Máquinas Virtuais é um SO projetado para hospedar múltiplos outros sistemas operacionais. Isso significa que o foco desse tipo de SO é ser eficiente no gerenciamento de VMs, garantindo que diferentes sistemas possam coexistir sem interferências.

![[Pasted image 20250524235632.png]]

**[[VMs]]** (Virtual Machine): são ambientes isolados que funcionam como computadores independentes. Porém precisam de um programa que os permita utilizar recursos do hardware

Nesse contexto, foi elaborado o **Monitor de Máquina Virtual.** Também conhecido como hipervisor, é o software responsável por gerenciar as máquinas virtuais. É por meio desse programa que há a criação de VMs, além do mesmo ser responsável por:

- **Gerência de Recursos**: Controla a alocação de CPU, memória, disco e dispositivos de entrada/saída entre as VMs.

- **Intermédio VMs e Hardware**: Como várias máquinas virtuais compartilham o mesmo hardware, o VMM gerencia e distribui os acessos ao processador, memória e dispositivos físicos.

- **Isolamento:** Se um sistema operacional dentro de uma máquina virtual falhar, isso não afeta as outras máquinas virtuais, pois todas estão separadas pelo VMM.

![[Pasted image 20250401014455.png]]

#### **Estrutura de um Sistema Operacional Baseado em Máquinas Virtuais**

1. **Hardware Real** → Processador, Memória, Disco, Dispositivos de Entrada e Saída.
    
2. **Monitor de Máquina Virtual (VMM)** → Controla e gerencia as máquinas virtuais.
    
3. **Máquinas Virtuais** → Cada uma tem seu próprio sistema operacional e aplicações.


```observação: É muito importante não confundir o conceito de hipervisor 1 com hipervisor 2. O hipervisor 1 refere-se à classificação de sistemas operacionais estudada nesse módulo. Enquanto isso, o hipervisor do tipo 2 é baseado em um software que roda sobre um SO host para tentar simular o hardware ```

