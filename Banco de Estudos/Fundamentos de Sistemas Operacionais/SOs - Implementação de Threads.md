Existem diferentes abordagens na implementação dos pacotes de threads em um sistema operacional, o que influenciará no desempenho, na concorrência e na modularidade das aplicações multithread.
##### 1. **[[SOs - Threads em Modo Kernel (Kernel-Level Threads – KLT)]]**

---
##### 2. **[[SOs - Threads em Modo Usuário (TMU)]]**

---
##### 3. **[[SOs - Threads em Modo Híbrido (M x N)]]**

---
###  Comparativo entre as Implementações

|Critério|Kernel-Level Threads (KLT)|User-Level Threads (ULT)|
|---|---|---|
|Escalonamento|Pelo kernel|Pela biblioteca do processo|
|Custo de troca de contexto|Alto|Baixo|
|Chamadas bloqueantes|Não bloqueia outras threads|Pode bloquear todas as threads|
|Portabilidade|Baixa|Alta|
|Uso de múltiplos núcleos|Sim|Não|

---

### Implementação em Diferentes SOs

![[Pasted image 20250526113035.png]]