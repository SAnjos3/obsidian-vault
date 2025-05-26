Um processo é formado por três partes, conhecidas como contexto de hardware, contexto de software e espaço de endereçamento, que juntos mantêm todas as informações necessárias à execução de um programa.

![[Pasted image 20250525171847.png]]

#### **Contexto de Hardware**

O contexto de hardware descreve o que o processo faz em nível de instruções e execução

Armazena o conteúdo dos registradores gerais da UCP, além dos registradores de uso específico. 
	Quando um processo está em execução, o seu contexto de hardware está armazenado nos registradores do processador. 
	No momento em que o processo perde a utilização da UCP, o sistema copia essas informações para dentro do PCB do processo.

#### **Contexto de Software**

O contexto de software não define o que o processo faz, mas como ele pode se comportar dentro do sistema. Isso representa **como o sistema operacional enxerga o processo**, **quais são suas permissões, limites e identidade**.

No contexto de software de um processo são especificados limites e características dos recursos que podem ser alocados pelo processo. O contexto de software é composto por três grupos de informações sobre o processo: identificação, quotas e privilégios.

- **Identificação**:
	Cada processo criado pelo sistema recebe uma identificação única (PID — process identification) representada por um número. Através do PID, o sistema operacional e outros processos podem fazer referência a qualquer processo existente, consultando seu contexto ou alterando uma de suas características.

- **Quotas**:
	As quotas são os limites de cada recurso do sistema que um processo pode alocar. Alguns exemplos de quotas presentes na maioria dos sistemas operacionais são:
	
	- Número máximo de arquivos abertos simultaneamente;
	- Tamanho máximo de memória principal e secundária que o processo pode alocar;
	- Número máximo de operações de E/S pendentes;
	- Tamanho máximo do buffer para operações de E/S;
	- Número máximo de processos, subprocessos e threads que podem ser criados.

- **Privilégios**:
	Os privilégios ou direitos definem as ações que um processo pode fazer em relação a ele mesmo, aos demais processos e ao sistema operacional.
	
	Privilégios que afetam o próprio processo permitem que suas características possam ser alteradas, como prioridade de execução, limites alocados na memória principal e secundária etc. 
	
	Privilégios que afetam os demais processos permitem, além da alteração de suas próprias características, alterar as de outros processos
	
	Privilégios que afetam o sistema são os mais amplos e poderosos, pois estão relacionados à operação e à gerência do ambiente, como a desativação do sistema, alteração de regras de segurança, criação de outros processos privilegiados, modificação de parâmetros de configuração do sistema, entre outros.

#### **Espaço de Endereçamento**

O espaço de endereçamento é a área de memória pertencente ao processo onde instruções e dados do programa são armazenados para execução. Cada processo possui seu próprio espaço de endereçamento, que deve ser devidamente protegido do acesso dos demais processos.

---

### Estrutura Geral 

![[Pasted image 20250525183101.png]]

### [[SOs - Bloco de Controle de Processos ( PCB )]]

