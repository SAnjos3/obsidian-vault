## Evolução dos Sistemas de Bases de Dados

Primeiros Bancos de Dados foram projetados na década de 70. Nessa época as organizações trabalhavam com um sistema mainframe, isso significa que existia um computador principal o qual guardava os dados com a estrutura abaixo. Assim existiam terminais espalhados pela organização que eram conectados com o banco de dados. 

Esses terminais eram considerados "Terminais Burros", o que remete a sua característica de apenas receber os comandos do usuário e retornar o resultado. Porém os Programas de aplicação que utilizavam o banco de dados não se encontravam no terminal, e sim no computador principal, o qual tinha proporções muito grandes.

![[Pasted image 20250330210246.png]]

Cerca de 10 a 20 anos depois, esse sistema mainframe foi substituído por computadores pessoais. Esses computadores já possuíam capacidade de processar. Também surgiu redes de computadores.

Os computadores passaram a rodar as aplicações e o SGBD dentro deles, porem espaços de armazenamento ainda eram um problema, por serem muito caros. Assim a ideia de mainframes ainda se aplicava no quesito de onde os dados eram armazenados. 

Isso gerava uma série de problemas, como quando várias consultas eram feitas por um computador. Em cenários como esse, a rede era obstruída por essa transação

![[Pasted image 20250330214324.png]]

Conforme essa questão de armazenamento foi melhorando. Começou a utilizar "computadores pessoais" mais capazes como servidores dos SGBD. Assim, diferente de antes que era implementado apenas um servidor para arquivos, servidores para os SGBDs passaram a ser usados.

Esses servidores do SGBD continham os dados que seriam consultados com frequência, enquanto dados mais específicos seriam armazenados no servidor de arquivos, como dados dos funcionários por exemplo. Essa nova implementação soluciona o problema do sistema anteriormente adotado, pois os dados serão localmente acessados pelo Servidor SGBD, isso faz com que apenas informações necessárias trafeguem pela rede, e não toda a consulta como acontecia antes, isso desobstrui a rede

![[Pasted image 20250330214638.png]]
## [[SGBD - Arquitetura Cliente-Servidor]]

## [[SGBD - Arquitetura Three-Schema]]

## [[SGBD - Ciclo de Vida]]
