O sistema é organizado em camadas funcionais. Cada camada faz uma requisição à camada inferior, a camada inferior trata a complexidade do procedimento de sua forma e retorna um produto para a camada superior.

Esses sistemas são estruturados de forma hierárquica, criando uma separação clara de responsabilidades e funcionalidades. Essa abordagem facilita a manutenção, depuração e compreensão do sistema.

A noção de camadas é fortemente reforçada pelo hardware.

**Estrutura Geral de um Sistema Operacional em Camadas:**

1. **Camada 0:** Gerencia o hardware diretamente, lidando com a alocação do processador e alternância entre processos.​

2. **Camada 1:** Responsável pelo gerenciamento de memória, alocando espaço para processos na memória principal e secundária.​

3. **Camada 2:** Cuida da comunicação entre o console do operador e os processos.​

4. **Camada 3:** Gerencia dispositivos de entrada e saída.

5. **Camada 4:** Contém os programas de usuário.

6. **Camada 5:** Representa o usuário final.

- Exemplos: THE (1968 - Dijkstra), MULTICS (Bell, MIT)

THE:
![[Pasted image 20250331134040.png]]
