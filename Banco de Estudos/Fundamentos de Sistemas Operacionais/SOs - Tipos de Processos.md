
Processo podem ser classificados em dois tipos de acordo com a [[SOs - Gerência de Processos]]

- [[SOs - Processos Heavyweight ( Tradicionais )]] 
- [[SOs - Processos Lightweight ( Threads )]]

### CPU-bound e I/O-bound:

Processos podem ser classificados como CPU-bound ou I/O-bound de acordo com a utilização do processador e dos dispositivos de E/S..

- **CPU-Bound**: Possuem afinidade com a CPU, assim passam a maior parte do tempo usando a CPU, no estado rodando ou no estado pronto

- **I/O-Bound**: Possuem afinidade com Entrada e Saída, assim passam a maior parte do tempo em estado bloqueado por causarem muitas operações de Entrada e Saída.

Muitas aplicações de computadores pessoais que rodam em primeiro plano são exemplos de aplicações I/O Bound. Essas aplicações passam muito tempo em estado bloqueado, aguardando as informações dos usuários.

#### [[SOs - Portas de Rede]]