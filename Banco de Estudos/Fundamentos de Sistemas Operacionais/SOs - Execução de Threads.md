# Padrões de Execução de Threads

## Modelo de Threads Dinâmicas

Nesse modelo, uma thread é criada **dinamicamente** para tratar cada nova requisição ou tarefa, sendo encerrada assim que seu trabalho for concluído. Isso significa que, a cada chegada de uma solicitação, o sistema invoca `thread_create`, delega a execução à nova thread e, ao final, chama `thread_exit`.

>**Exemplo**: em um servidor de processamento de mensagens, cada mensagem recebida dispara a criação de uma thread dedicada, que lê, processa e responde ao cliente antes de encerrar.

### **Vantagens**

- **Simplicidade**: fácil de implementar;
    
- **Isolamento de falhas**: erro em uma thread não afeta diretamente outras.

### **Desvantagens**

- **Overhead de criação/remoção**: alto custo de alocação de recursos a cada requisição;
    
- **Risco de esgotamento de recursos**: em cenários de pico, muitas threads simultâneas podem consumir memória e fiação do sistema.

---

## Modelo de Threads Estáticas

Aqui, o sistema inicializa **um conjunto fixo** de threads (o _pool_) no momento de startup, e mantém-nas vivas durante todo o tempo de execução. As tarefas chegam numa fila, e cada thread do pool faz `thread_yield` para buscar novo trabalho sempre que fica ociosa.

>**Exemplo**: num serviço de impressão em rede, um pool de 10 threads aguarda requisições; cada thread retira um job da fila, imprime e volta ao pool para próxima tarefa.

### **Vantagens**

- **Controle de recursos**: número de threads limitado evita esgotamento;
    
- **Desempenho previsível**: minimiza overhead de criação/terminação contínua.

### **Desvantagens**

- **Dimensionamento inflexível**: número fixo pode ser insuficiente em picos ou excessivo em baixa demanda;
    
- **Complexidade na fila**: demanda gerenciamento eficiente de enfileiramento e balanceamento.

---

## Modelo Despachante/ Trabalhador

Este modelo é um dos padrões que podem ser seguidos para a solução comum de criação e término de threads ou para a estruturação de como threads tratam tarefas durante a execução.

Nesse modelo existem dois tipos de threads:

- **Despachante**: esse tipo de thread tem a responsabilidade de receber o trabalho, sem processa-lo, e selecionar uma thread trabalhadora para entrega-lo.

- **Trabalhadora**: esse tipo de thread tem a responsabilidade de executar a solicitação feita pela thread despachante. Após o término da execução, a thread trabalhadora sinaliza o despachante.

![[Pasted image 20250527173611.png]]

**Exemplo**:

>  Um exemplo clássico de aplicação deste modelo é um servidor web. Um servidor web recebe diversas requisições de clientes. 
> 
> Se a mesma thread fosse responsável por receber uma nova requisição e também por realizar operações de leitura em disco (que podem ser demoradas), poderia surgir um problema, especialmente se o equipamento de rede fosse mais rápido que o disco. 
> 
> O modelo Despachante/Trabalhador permite separar essas responsabilidades.

### Vantagens

- **Consumo rápido de mensagens**.

- **Boa distribuição das requisições**.

- **Flexibilidade**: é possível mudar facilmente o número de threads trabalhadoras

### Desvantagens 

- **Pouco uso de CPU pela thread Despachante**

---

## Modelo Time

No **modelo Time**, não há despacho centralizado: cada thread atua de forma **autônoma**, “catando” tarefas de um pool compartilhado (um _task queue_) usando geralmente um mecanismo de polling. Assim, as próprias threads decidem quando estão prontas para executar, sem intervenção de um despachante.

![[Pasted image 20250527174648.png]]

>**Exemplo**: num sistema de processamento de arquivos, todas as threads do pool rodando em paralelo consultam continuamente a fila de arquivos a serem processados e cada uma retira a próxima disponível.

### **Vantagens**

- **Boa distribuição**: threads competem igualmente pelas tarefas;
    
- **Escalabilidade**: adicionar ou remover threads altera dinamicamente a capacidade de consumo.
    

### **Desvantagens**

- **Poll overhead**: constante verificação da fila consome CPU;
    
- **Cuidado na Implementação**: Em computadores modernos, uma thread inicia o programa e deve ser responsável por criar todas as outras. Após isso, ela deve se tornar uma thread normal do time

---

## Modelo Pipeline

O **pipeline** divide o processamento em **estágios sequenciais**, onde cada thread é responsável por um estágio específico do processo. Os dados fluem de uma thread para a seguinte, como em uma linha de montagem, e o resultado final sai pela última thread.

> `[Thread 1] –> [Thread 2] –> … –> [Thread N] –> saída final`

### **Vantagens**

- **Especialização**: cada thread otimizada para sua tarefa;
    
- **Fluxo contínuo**: bom para processamento em lote com etapas bem definidas.
    

### **Desvantagens**

- **Gargalo**: se uma etapa for muito lenta, atrasa o pipeline todo;
    
- **Divisão de tarefas**: nem sempre é trivial segmentar o trabalho em estágios independentes.