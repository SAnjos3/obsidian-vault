### Classificação de Sistemas Operacionais

![[Pasted image 20250524222743.png]]

- #### Sistemas Monoprogramáveis  / Monotarefa: 

	Apenas um processo era aplicado por vez. Assim o hardware ficava alocado para apenas essa tarefa. Esses sistemas monotarefa possuem raiz nos computadores da década de 60. 

- #### Sistemas Multiprogramáveis / Multitarefa: 

	Foi desenvolvido a partir da percepção de que se usava pouco do hardware  e isso afetava o desempenho. Esses sistemas permitiram que os recursos computacionais fossem compartilhados entre diversos usuários e aplicações.

	- Enquanto um programa esperava um evento, outros podiam utilizar o processamento.
	- Sistema operacional é o responsável por gerenciar o acesso a esses recursos.

	Foram desenvolvidas propostas diferentes para esses sistemas multiprogramáveis:
	![[Pasted image 20250524223143.png]]
	
	- **Sistemas Batch**: Foram criados na década de 60, e são inspirados nos cartões perfurados e fitas magnéticas.
		- Não exige interação do usuário com a aplicação.
		- As aplicações são organizadas e processadas em lote.

	- **Sistemas de tempo compartilhado**: Permitem que diferentes programas sejam executados a partir da divisão de tempo com o processador em pequenas fatias de tempo.
		- Muitas vezes baseado na interação do usuário com a aplicação.
		- Diversas mudanças no SO e no hardware são necessárias para permitir esse comportamento.

	- **Sistemas de tempo real**: É de certa forma semelhante ao funcionamento dos sistemas de tempo compartilhado. Porém trabalha com aplicações que possuem um rígido limite de tempo a ser cumprido.

- #### Sistemas com Múltiplos Processadores

	Possuem dois ou mais processadores interligados e trabalhando em conjunto. Permite vários programas sejam efetivamente executados simultaneamente. Também permite que um programa seja executado mais rapidamente, caso essa aplicação seja multi-threaded.
	![[Pasted image 20250524224729.png]]
	
	- **Sistemas Fortemente Acoplados**: refere-se a sistemas de múltiplos processadores onde os vários processadores compartilham de uma única memória física e dispositivos de entrada/saída são gerenciados por apenas um sistema operacional.
	
	- **Sistema Fracamente Acoplados**: caracterizam-se por possuir dois ou mais sistemas computacionais conectados através de  linhas de comunicação. Cada sistema funcionando de forma independente, possuindo seu próprio sistema operacional e gerenciando seus próprios recursos.

### Classificação de Sistemas Operacionais - Usabilidade

- #### **Sistemas Operacionais de Computadores Pessoais**:

	Sistemas Operacionais comumente utilizados para o uso simultâneo de apenas um usuário. 

	- Utilizados em computadores de mesa e notebooks.
	- Tipicamente, contém pacotes de escritório, com editores de texto e planilhas eletrônicas.
	- Exemplos: Windows XP, Windows 7, Windows 8.1, Windows 10. Ubuntu, Fedora, OpenSuse.

- #### **Sistemas Operacionais de Servidores**:

	Sistemas cujo objetivo é servir um maior número de usuários simultaneamente.

	- Pode incluir diferentes tipos de serviços: servidor web, email, servidor de autenticação, servidor de backup, etc.
	- Exemplos: Windows 2008 Server, Windows 2012 Server. Cent OS, Red Hat, Slackware.

- #### **Sistemas Operacionais Embarcados**:

	Sistema muito popular de grande crescimento ultimamente. Porém estão presentes em muitos mais dispositivos da rotina que não aparentam ser computadores, como micro-ondas, TV,  smartphones, entre outros.

	- Exemplos: PalmOS, Windows CE, Android, iOS, Windows Phone

### Classificação de Sistemas - Propósito

- #### **Sistema de Propósito Único**:

	Criados para executar uma única função específica.

	- Possuem poucos processos em execução, o que torna o controle mais simples.

- #### **Sistema de Propósito Geral**

	 Presente nos computadores modernos, onde os usuários podem rodar múltiplos programas diferentes simultaneamente
	
	- ```Tanenbaum: "Nos sistemas de propósito geral, múltiplos programas podem ser executados simultaneamente, o que requer um escalonador eficiente para alternar entre processos e evitar que um monopolize o processador."```
### Classificação das Estruturas dos Sistemas Operacionais

Uma das mais importantes classificações dos sistemas operacionais e esta relacionada com as configurações de seu kernel (núcleo). Dentre eles:

- **[[SOs - Sistemas Monolíticos]]**

- **[[SOs - Sistemas em Camadas]]**

- **[[SOs - Sistemas Micro-Kernel]]** 

- **[[SOs - Máquinas Virtuais]]**

- **[[SOs - Sistemas Exo-Kernel]]**
