Todas as informações sobre processos em execução são armazenadas na **Tabela de Processos**, também conhecida como **Bloco de Controle de Processo (PCB - Process Control Block)**. Essa tabela contém diversas informações:

![[Pasted image 20250525184703.png]]

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