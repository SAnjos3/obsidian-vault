#### Formas de Implementar Threads

Existem **duas abordagens principais** para implementar threads:

##### 1. **Implementação no Sistema Operacional (Kernel-Level Threads – KLT)**

- Threads são **criadas e gerenciadas pelo kernel**.
    
- O **SO mantém uma tabela de threads** no kernel.
    
- Quando uma thread é bloqueada, **o kernel pode escalonar outra thread** (até de outro processo).

**Vantagens:**

- Aproveita **múltiplos núcleos** (execução paralela real).
    
- Se uma thread é bloqueada, **as outras continuam rodando**.
    

**Desvantagens:**

- **Troca de contexto mais custosa**, pois envolve chamadas ao sistema.
    
- **Maior complexidade** na implementação.
    

---
##### 2. **Implementação no Espaço do Usuário (User-Level Threads – ULT)**

- Threads são gerenciadas por **bibliotecas do usuário**, não pelo kernel.
    
- Cada processo possui sua **própria tabela de threads**.
    
- A troca de contexto é feita por **funções da biblioteca**.
    

**Vantagens:**

- **Troca de contexto muito rápida**, pois não há intervenção do kernel.
    
- **Cada processo pode ter seu próprio algoritmo de escalonamento**.
    

**Desvantagens:**

- Se uma thread fizer uma chamada bloqueante ao SO, **todo o processo pode travar**.
    
- **Menor aproveitamento de múltiplos núcleos**.
    

---
##### 3. Modelo Híbrido (M:N)

- Combina vantagens dos dois modelos.
    
- Um processo pode ter **várias threads de kernel**, e cada uma dessas pode gerenciar **múltiplas threads de usuário**.
    

**Exemplo:**

- 4 threads de usuário → mapeadas em 2 threads de kernel.
    

**Vantagens:**

- Aproveita múltiplos núcleos **sem perder velocidade de troca de contexto**.
    
- Flexível e mais eficiente em sistemas modernos.
    

**Desvantagens:**

- Implementação é **mais complexa**.

---

## 2.  Comparativo Entre Implementações

|Critério|Kernel-Level Threads (KLT)|User-Level Threads (ULT)|
|---|---|---|
|Escalonamento|Pelo kernel|Pela biblioteca do processo|
|Custo de troca de contexto|Alto|Baixo|
|Chamadas bloqueantes|Não bloqueia outras threads|Pode bloquear todas as threads|
|Portabilidade|Baixa|Alta|
|Uso de múltiplos núcleos|Sim|Não|

---

## 3. Problemas e Soluções em ULT

### Problema:

- Chamadas bloqueantes (ex: `read()`, `recv()`) podem travar **todas as threads**.
    

### Solução:

- **"Capa" de verificação** nas bibliotecas de threads:
    
    - Antes de chamar a função bloqueante, verifica se há outras threads disponíveis.
        
    - Se houver, troca para outra thread antes de bloquear.
        

**Observação:** Essa abordagem **gera overhead adicional** no sistema.

---

