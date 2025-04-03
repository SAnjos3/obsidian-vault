Esse um sistema que visa projetar um núcleo de sistema operacional de forma mais enxuta possível. O Exo-Kernel poupa recursos ao retirar camadas de abstração que normalmente fazem mapeamento dos recursos de hardware. Pra substituir essa tecnologia, ele se concentra em:

- **Multiplexação Segura**:
	
	- *Multiplexação*: Significa basicamente compartilhar os recursos de hardware (como CPU, memória, dispositivos) entre várias entidades (processos, máquinas virtuais, ou, no caso do Exo-kernel, diferentes LibOS).
	
	- *Segurança no Exo-kernel*: O Exo-Kernel garante que, mesmo que múltiplos sistemas (os LibOS) estejam acessando o hardware, nenhum deles consiga interferir de maneira que comprometa os demais ou o próprio hardware, compondo assim uma camada de proteção.

Ao invés de esconder o hardware por trás de abstrações (como outros modelos de sistema operacionais fazem), o Exo-Kernel expõe o hardware diretamente para os processos que rodam no espaço do usuário. Isso significa que o Exo-Kernel não controla diretamente o hardware, ele adota uma abordagem de permissões, para que as aplicações utilizando essas permissões possam ter acesso aos recursos

- **Primitivas Básicas**: São fornecidas primitivas básicas (instruções ou funções mínimas) para acessar os recursos de hardware.

- **Implementação de Abstrações em Modo Usuário:** Com essas primitivas, as abstrações tradicionais do sistema operacional (como sistemas de arquivos, gerenciamento de memória, etc.) são implementadas no espaço do usuário, através de bibliotecas.

#### Divisão do Sistema Operacional Exo-kernel

O sistema operacional baseado em Exo-Kernel é dividido em duas partes principais:

- **Exo-kernel:**
    
    - **Função:** Atua como um núcleo minimalista cuja principal responsabilidade é multiplexar os recursos de hardware de forma segura.
        
    - **Proteção:** Garante que os recursos do hardware sejam usados sem interferências indevidas, mantendo a segurança e a integridade do sistema.
        
- **LibOS (Library Operating System):**
    
    - **Função:** Trata-se de um conjunto de bibliotecas que implementam as abstrações de alto nível típicas de um sistema operacional, como gerenciamento de arquivos, redes, processos, etc.
        
    - **Operação em Modo Usuário:** Essas bibliotecas rodam em modo usuário, permitindo que diferentes aplicações possam ter suas próprias implementações de abstrações conforme suas necessidades, sem depender de um único kernel monolítico.