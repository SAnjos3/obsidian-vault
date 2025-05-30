A arquitetura de threads em modo híbrido combina as vantagens de threads implementados em modo usuário (TMU) e modo kernel (TMK). 

- Um processo pode ter vários TMKs e, por sua vez, um TMK pode ter vários TMUs. 
	
- O núcleo do sistema reconhece os TMKs e pode escaloná-los individualmente. 
	
- Um TMU pode ser executado em um TMK, em um determinado momento, e no instante seguinte ser executado em outro.

![[Pasted image 20250526112142.png]]

O **programador desenvolve a aplicação utilizando TMUs** e define **quantos TMKs serão associados ao processo**. Durante a execução, o mapeamento das TMUs nos TMKs permite um balanceamento eficiente de tarefas.

> O programador pode optar por usar apenas TMUs, apenas TMKs, ou uma **combinação de ambos**.

**Vantagens:**

- **Aproveita múltiplos núcleos** com bom desempenho e **baixa sobrecarga na troca de contexto** (como nos TMUs).
    
- **Maior flexibilidade**, adaptando-se bem a diferentes tipos de aplicações e arquiteturas modernas.
    
- **Equilíbrio entre desempenho e controle**, aproveitando os pontos fortes das abordagens anteriores.

**Desvantagens:**

- **Implementação mais complexa**, tanto no sistema operacional quanto na aplicação.
	
- Ainda pode sofrer com **heranças dos dois modelos**:
	
	- Se um TMK bloquear, **todas as TMUs associadas a ele também bloqueiam**.
    
	- Para TMUs utilizarem múltiplos processadores, **precisam ser associadas a TMKs distintos**, o que afeta o desempenho se mal gerenciado.
