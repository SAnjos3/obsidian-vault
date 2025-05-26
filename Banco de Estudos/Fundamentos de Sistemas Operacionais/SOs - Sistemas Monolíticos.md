É a organização de SO mais comum. O SO roda em modo protegido, todo restante em modo usuário.

	Tanenbaum: "Não há estrutura"/"Uma grande bagunça". O sistema operacional por inteiro é programado como um único componente. A estrutura do SO é mantida em organização de código.

![[Pasted image 20250524231344.png]]

 - Possui a melhor organização visando o tempo de resposta.

- Todos os procedimentos do núcleo são visíveis a todos os outros.

- Visando construir uma estrutura, todos os procedimentos são forçados a fazer um SVC (supervisor call).

- Possui três camadas: um procedimento principal que chama os procedimentos de serviço. E procedimentos utilitários, compartilhados entre os de serviço.

- Alguns sistemas monolíticos modernos não possuem todos os drives, possibilidades e serviços no núcleo, pois isso ocupa muito espaço em memória. Assim esses sistemas permitem que "módulos de kernel", dados existentes no espaço de usuário que são inseridos pelo administrador (root) no Kernel.

![[Pasted image 20250401013112.png]]
