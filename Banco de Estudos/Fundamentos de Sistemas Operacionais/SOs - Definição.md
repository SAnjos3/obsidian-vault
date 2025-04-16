### Conceitos básicos

Computador é divido em:

- Hardware: componentes físicos. 
- Software: conjunto de todos os programas do computador.
- SO: também é um programa ou conjunto de programas 

### Sistema Computacional

Em uma visão geral, um sistema computacional pode ser controlado por dois modos de operação, são elas: 

 - Modo usuário: possui uma série de restrições no que diz respeito ao controle do sistema e do hardware.
 - Modo protegido: esse modo não possui qualquer restrição sobre seu controle do hardware. Nesse modo, é possível utilizar todos as instruções disponíveis para controle dos hardware.
 
		obs: o modo protegido não é o modo administrador. O modo administrador ainda é considerado como parte do modo de usuário. 
 
Além disso separa-se o sistema computacional em:

- Hardware: inclui a linguagem de máquina, microarquitetura, dispositivos físicos.
- Software Base:  Se refere ao sistema operacional e softwares básicos necessários para o funcionamento da máquina. Esses software básicos podem ser compiladores, o shell e o GUI.
- Softwares Aplicativos: São software instalados encima do sistema operacional de acordo com a experiência necessária para o usuário.
### Sistema Operacional, conceitos:

Tendo como base os conceitos acima, é possível contemplar  a definição de sistemas operacionais de acordo com importantes autores:

 - Tanenbaum:
 
	 Softwares possuem dois modos de operação, são eles o modo protegido (modo kernel) e o modo de usuário. A diferença entre esse modos é a quantidade de poder sobre o hardware cada um possui. Enquanto o modo de usuário possui restrições no que diz respeito a sua capacidade de controlar o hardware, o modo protegido não tem nenhum. 
	 
	E é nesse ponto em que entra o conceito de sistemas operacionais de acordo com o Tanenbaum. O sistema operacional é aquele que controla a maquina no modo protegido, ou seja, sem restrições. 
	
	O SO é a parte fundamental de software que executa em modo protegido, onde possui acesso a todo hardware e pode executar qualquer instrução que a máquina é capaz de executar

 - Machado & Maia : 
	 A grande diferença entre um sistema operacional e aplicações convencionais é a maneira como suas rotinas são executadas em função do tempo.
	 
	 Um sistema operacional não é executado de forma linear como na maioria das aplicações, com início, meio e fim.
	 
	 Suas rotinas são executadas concorrentemente em função de eventos assíncronos (que podem ocorrer a qualquer momento).

Em relação à função do sistema operacional, alguns autores concluíram certas afirmações:

- Madnick 74: 
	O sistema operacional é o gerenciador de recursos da máquina. 
	
- Fortifier 86: 
	O sistema operacional fornece ao usuário uma visão de sua interface com a máquina.
	
- Krakowiack87/Tanenbaum95: 
	Um sistema operacional possui duas grandes funções: criar para o usuário uma abstração do hardware (máquina estendida) e gerenciar os recursos da máquina.

### Máquinas Estendidas

Uma máquina estendida é um sistema projetado para apresentar ao usuário uma interface mais simples e simpática do que a máquina real. O termo utilizado pode mudar para máquina abstrata e ela é equivalente ao hardware, porém mais simples de programar.

## Gerenciador de Recursos

Um computador é um conjunto de recursos que devem ser administrados e compartilhados. Existem dois tipos de recursos:

- Físicos: processadores, memórias, discos, rede, entre outros.
- Abstratos: processos, arquivos, entre outros.

É papel do sistema operacional proteger esses recursos, especialmente quando o ambiente está sendo usado por mais de um usuário. Assim evitando que esses processos se interfiram entre si. Assim, para todo recursos, o SO deve:

- Manter informações relevantes sobre o recurso (endereço, estado, etc).
- Decidir permissões
- Alocar e liberar o recurso

Todo esse processo deve visar o máximo de eficiência.

### [[SOs - Estrutura e Componentes]]

Nesse tópico são encontradas classificações de SOs em relação a suas estruturas, componentes e abordagens