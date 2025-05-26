A gerência de processos é de suma importância para abordar a maneira como o sistema operacional mantém diversos processos ativos simultaneamente no computador. É a partir dessa gerência que sem mantém a ilusão de múltiplos processos sequenciais em uma máquina com uma CPU.

Sobre a Gerência de Processos, algumas informações são relevantes. 

---
### [[SOs - Criação e Finalização de Processos]]

```Machado e Maia: A criação de processos é essencial para a execução de múltiplas tarefas em sistemas operacionais modernos, garantindo a execução paralela de programas."```

---
### [[SOs - Estados de um Processo]]

Para o estudo da troca de contexto de um processo, se torna necessário os conceitos de estados de um processo.

---
### Troca de Contexto

Refere-se ao processo que permite que vários processos compartilhem a CPU de maneira eficiente. 

Na gerência de um processo, ocorrem principalmente três etapas em relação ao estado de um processo.

#### 1. Interrupção de Processo:

>As interrupções são eventos que permitem que a CPU interrompa a execução de um processo para atender eventos importantes, como entrada e saída de dados.

- A interrupção de um processo pode ser motivada pelas situações descritas: [[SOs - Criação e Finalização de Processos#Finalização de um Processo]].
	
- Quando ocorre uma interrupção, a CPU consulta o **vetor de interrupções**, que aponta para a **rotina de tratamento** (ISR – _Interrupt Service Routine_).
    
- O processo interrompido muda de estado (por exemplo, de “executando” para “pronto” ou “bloqueado”).

#### 2. Armazenamento de Estado:

 >Refere-se a operação de salvamento dos registradores de um processo e posterior restauração de registradores de outro processo.  
 
- Essas informações são salvas no [[SOs - Bloco de Controle de Processos ( PCB )]].
    
- O PCB funciona como uma “ficha do processo”, onde o SO guarda tudo o que é necessário para retomar o processo mais tarde.
    
- Em seguida, o SO **carrega o contexto de outro processo** (também a partir do PCB) e este novo processo assume a CPU.
 
#### 3.  [[SOs - Escalonamento de Processos]]

>Refere-se ao mecanismo que determine qual processo será executado em determinado momento, com o objetivo de melhor eficiência possível na execução de processos

- Baseia-se em algoritmos de escalonamento.
    
- Considera fatores como tempo de espera, prioridade, estado do processo, entre outros.
    
- Após a escolha, o SO carrega o contexto do novo processo escolhido, iniciando sua execução do ponto exato em que havia parado.


