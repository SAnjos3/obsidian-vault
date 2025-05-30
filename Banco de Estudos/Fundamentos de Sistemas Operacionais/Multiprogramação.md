Apesar de ser um conceito interessante e relativamente de fácil aplicação, o modelo multi-thread levanta questões a se considerar:

- O compartilhamento de dados pode causar muitos problemas.
- Alguns desafios são solucionados com boas práticas de programação.
- Projetar programas multi-thread que cooperem para resolver o mesmo problema é muito difícil
- Em sistemas modernos, normalmente as threads estão sujeitas a um escalonador preemptivo e que não sabemos como vai se comportar


### 1. Condição de Corrida

São situações em que duas ou mais threads/processos acessam concorrentemente uma mesma região de memória compartilhada sem nenhuma sincronização, levando a resultados imprevisíveis. Como o escalonador do sistema operacional pode interromper e trocar o contexto a qualquer momento, operações compostas (ex.: LOAD→INC→STORE) podem ser intercaladas, causando “lost updates” ou “overwrites” inesperados .

---

### 2. Seção Crítica

Trecho de código onde ocorre acesso (leitura ou escrita) a dados compartilhados. Deve-se garantir que **somente uma** thread/processo execute essa região por vez, para evitar condições de corrida .

---

### 3. Exclusão Mútua (Mutual Exclusion)

Conjunto de propriedades que um protocolo de sincronização deve satisfazer para controlar o acesso à seção crítica:

1. **Segurança**: nunca mais de um processo na seção crítica simultaneamente.
    
2. **Progresso**: threads fora da seção crítica não podem impedir indefinidamente outras de entrarem.
    
3. **Garantia de espera limitada**: não pode haver espera infinita (starvation).
    
4. **Independência de velocidade**: não depende de suposições sobre velocidades relativas ou número de CPUs .
    

---

### 4. Técnicas de Implementação de Exclusão Mútua

1. **Inibir Interrupções**
    
    - Desliga interrupções antes da região crítica e reativa depois. Grande impactos se interrupções não forem reativadas
        
    - Garante todas as características descritas na exclusão mútua. 
		
	- Simples e atômico em modo kernel, mas indisponível/inseguro em espaço de usuário .
	
2. **Espera Ocupada (Busy Waiting)**
    
    - **Variáveis de impedimento** (`lock`): spin-lock baseado em teste e atribuição não atômicos — sujeito a race no gap entre teste e set.
        
    - **Estrita Alternância**: alterna a vez entre dois processos; simples mas ineficiente se velocidades diferentes.
	    - A estrita alternância não deve ser utilizada quando um processo é muito mais lento do que outro
	    - Viola a regra de um processo fora da seção crítica bloquear outro processo.
	    - Não é uma solução genérica.
        
    - **Algoritmo de Peterson**: usa duas flags e uma variável `turn` para garantir exclusão mútua sem espera infinita.
	    - Esse algoritmo minimizou o número de loops e comparações necessárias.
	    - Garante a exclusão mútua
	    - Os processos possuem um id único (0 ou 1).
	    - O processo deve chamar uma função enter_region, que retorna só quando for seguro entrar na seção.
	    - Ao terminar o processamento, a função leave_region deve ser chamada para indicar que outros processos podem prosseguir.
	    - Isso garante que um processo fora da seção crítica não bloqueie outros
        
    - **Instruções atômicas de hardware** (`test_and_set`, TSL): combinam teste e set em uma única operação indivisível .
        
3. **Bloqueio de Processos (Blocking Locks)**
    
    - **Semáforos** (Dijkstra): contador atômico com operações `P()` e `V()`, bloqueantes quando zero.
        
    - **Mutexes**: versão binária de semáforo, bloqueante, eficiente em espaços de usuário (futexes) e kernel.
        
    - **Monitores**: abstração de alto-nível que combina exclusão mútua e variáveis de condição; só uma thread ativa por monitor.
        
    - **Variáveis de Condição**: usadas dentro de monitores para sincronizar esperando por condições específicas (`wait`/`signal`), sempre associadas a um mutex .