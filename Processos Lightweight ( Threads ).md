Para falar sobre esse tema, algumas informações importantes sobre processo é necessário. Pode-se dividir um processo em duas partes:

- Ambiente
	- Espaço de Endereçamento
	- Arquivos abertos
	- Processos filhos
	- Sinais
	- Estatísticas de Uso

- Execução:
	- Contador de Programa (PC)
	- Apontador de Pilha
	- Conjunto de Registradores 
	- Estado de Execução

A troca de contexto entre os processo tradicionais é pesada, isso se deve ao fato dessa troca ser equivalente a:

 - Contexto = Ambiente + Execução 

O processos tradicionais não compartilham memória e possuem apenas um fluxo de execução, threads de controle.

#### Threads - Processos Lightweight

Esses processos, diferentemente dos tradicionais, separam os conceitos de agrupamento de recursos e execução. Nessa nova separação, tem-se que:
- Processos: agrupam 

