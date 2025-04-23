A estrita alternância resolve o problema da exclusão mútua para dois processos. A ideia é que o processo marque que está na seção crítica e outro processo aguarda a saída. 

Assim não há ocorrência de um processo entrando duas vezes.

- Solução: int turn = 0;

	![[Pasted image 20250416124912.png]]

**Desvantagens**:

- A estrita alternância não deve ser utilizada quando um processo é muito mais lento do que outro. (Desvantajosa)

- Estrita alternância viola a regra de um processo fora da seção crítica bloquear outro processo. (Desvantajosa)

- Não é uma solução genérica (Desvantajosa)

Em 1981, Peterson melhorou o algorítimo baseado em outro chamado Dekker. Esse algorítimo minimizou o número de loops e comparações necessárias.

- Passou a garantir a exclusão mútua
- Os processos possuem um id único ( 0 ou 1).
- O processo deve chamar uma função enter_region, que retorna quando for seguro entrar na seção.
- Ao terminar o processamento, a função leave_region deve ser chamada para indicar que outros processos podem prosseguir.
- Garante que um processo fora da seção crítica não bloqueie outros.

![[Pasted image 20250416131416.png]]
