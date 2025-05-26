É formado pelo servidor e pelo lado do cliente. 
	- **Servidor**: formado pelos dados e metadados e pelo Sistema Gerenciador de Banco de Dados.
	- **Cliente**: formado pelas aplicações que utilizam banco de dados. Geralmente utilizados em computadores pessoais como notebooks.

![[Pasted image 20250330213111.png]]
#### Duas Camadas -  Aplicações Desktop

- **Cliente**: Interface + maior parte da lógica de negócio.
	- Interface: parte gráfica.
	- + Lógica de Negócio: regras e schema do negócio.

- **Servidor**: BD + parte ( pequena ) da lógica de negócio.
	- BD: armazenamento de dados.
	- - Lógica de Negócio: pequenos detalhes adicionais ao schema de negócio. Uma verificação a mais sobre a validação dos dados. Exemplo: se um campo pode ou não ser deixado em branco, qual é a data do dia em que o dado esta sendo armazenado, entre outros.

![[Pasted image 20250330221600.png]]

#### Três Camadas - Sistema de Redes

- **Cliente**: Interface + parte específica da lógica de negócio.
	- A lógica nessa camada se torna cada vez mais simples.
	
- **Servidor**: BD + SGBD + Computador Servidor de Aplicação.
	- Com o Servidor, as aplicações começam a ser divididas no em server side e client side.
	- Servidor de Aplicação é o computador/servidor responsável por executar a lógica de negócio que antigamente estava no cliente.

![[Pasted image 20250330223011.png]]

#### Quatro Camadas - Adaptatividade 

- **Cliente**: Se torna mais simples. E agora a interface não é mais guardada nesse lado. Isso permitiu que por exemplo uma mesma aplicação tivesse a mesma interface para diferentes browsers, enquanto antes era necessário implementar para cada um dos navegadores.

- **Servidor**: DB <- SGBD <- Servidor de Aplicação <- Servidor de Interface 
	- Servidor de Interface é o computador/servidor dedicado a gerar e entregar a interface gráfica para o cliente.

![[Pasted image 20250330222806.png]]


