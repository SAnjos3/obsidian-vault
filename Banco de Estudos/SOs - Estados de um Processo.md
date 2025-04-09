Embora processos sejam autossuficientes, muitas vezes eles necessitam acessar recursos do hardware, o que pode gerar desempenhos não muito eficientes. 

Ex: Ocorre situações onde um processo está realizando uma leitura de disco, ou leitura de rede, que são processos lentos.

Nesse contexto, se tornou perceptível ao longo da evolução de SOs que seria necessário criar uma melhor gerência desses processos. Para isso, criou-se estados de processo:

- Rodando 
- Bloqueado
- Pronto

![[Pasted image 20250402132749.png]]
 
(1) O processo bloqueia-se aguardando uma entrada

(2) O evento aguardado pelo processo ocorreu, pode-se iniciar a executar. 

(3) O tempo de posse do processador esgotou-se 

(4) O processo é escolhido pelo escalonador para executar

