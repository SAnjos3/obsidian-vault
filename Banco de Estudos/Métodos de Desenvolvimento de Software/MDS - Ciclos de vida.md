Ciclos de vida podem ser definidos pelas fases que um projeto ir passar durante o processo de seu desenvolvimento.  Isso se difere do conceito de [[MDS - Processos]], que é onde se define em mais detalhes como serão desenvolvidas cada etapa do ciclo de vida

### Tipos de Ciclos de Vida que podem ser adotados no desenvolvimento de um projeto:
### 1.  Preditivo

![[Pasted image 20250327094001.png]]

**Descrição:**  
Esse é um dos primeiros modelos de ciclo de vida do software, baseado em uma abordagem sequencial. Cada fase começa apenas quando a anterior é concluída.

**Fases:**

1. **Requisitos:** Coleta e documentação das necessidades do cliente.
    
2. **Projeto (Design):** Planejamento da arquitetura e tecnologia do sistema.
    
3. **Implementação:** Codificação do software com base no projeto definido.
    
4. **Testes:** Verificação e validação do sistema para garantir que atenda aos requisitos.
    
5. **Implantação:** Entrega do software ao usuário final.
    
6. **Manutenção:** Correção de erros e possíveis atualizações.
    
---

### 2.  Iterativo

**Descrição:**  

Abordagem que permite feedback sobre o trabalho parcialmente concluído ou inacabado para melhorar e modificar esse trabalho.

**Fases:**

![[Pasted image 20250327093931.png]]

1. **Requisitos:** Coleta e documentação das necessidades do cliente.
    
2. **Análise (Design):** Planejamento da arquitetura e tecnologia do sistema.
	
	Loop . **Protótipo:** Gera protótipos para entregas para o cliente. Recebe o feedback e repete essa fase quantas vezes necessárias.
    
3. **Testes:** Verificação e validação do sistema para garantir que atenda aos requisitos.
	 
	 Loop. **Refinamento**: Verifica as funcionalidades do sistema refinando incontáveis vezes até q satisfaça o cliente.
	 
4. **Entrega:** Entrega do software ao usuário final.

---
### 3. Incremental 

Abordagem que permite entregas completas e funcionais para que o cliente possa usar imediatamente. Diferentemente do modelo iterativo, as entregas são feitas de produtos completos, ou seja, não há revisão sobre uma entrega anterior, apenas melhoras para uma próxima entrega.

![[Pasted image 20250327094322.png]]

Desenvolvimento:

1.  Requisitos
	
2. Design 
	
3. Construção
	
4. Teste
	
5. Entregas: repetidas entregas de produtos completos para o cliente. Repete o ciclo.

---
### 4. Iterativo e Incremental  / Ágil 

O ciclo de vida ágil aproveita tanto aspectos do ciclo de vida incremental e iterativo para realizar entregas frequentes para o cliente.

![[Pasted image 20250327101417.png]]

Descreve basicamente ciclos de desenvolvimento que contam tanto com iterações, quanto com entregas incrementais. Isso significa que os incrementos entregáveis ao cliente, são construídos ao longo de iterações, para ajustes e melhorias. Isso significa que cada entrega pode ser revisada e alterada com base na iteração e feedback com o cliente. A combinação dos elementos desses dois ciclos é simultânea.

![[Pasted image 20250327111642.png]]

Obs: A diferença na estrutura do ciclo de vida iterativo-incremental para o ciclo de vida ágil, esta principalmente na gestão dos incrementos. A palavra-chave nessa comparação é a flexibilidade. 

- **Iterativo-Incremental**: 
	Embora haja revisões internas, uma vez que um incremento é aprovado, ele geralmente não é alterado profundamente. A ideia é construir sobre ele, não refatorá-lo o tempo todo.

- **Ágil**:
	Baseia-se no feedback frequente do cliente. Ou seja, alterações nos incrementos anteriores são esperadas e até incentivadas, se o feedback assim apontar.

---
## 5.  Adaptativo

- Utiliza múltiplas abordagens para a resolução de um projeto 

- Os projetos podem combinar elementos de diferentes ciclos de vida para atingir determinados objetivos.

- Deve-se tomar cuidado para os valores e elementos dos diferentes ciclos de vida não sejam conflitantes entre si.

- A utilização dos elementos de diferentes ciclos, são feitos de forma assíncrona.

  ![[Pasted image 20250327103948.png]]
