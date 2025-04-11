### Conceito de Porta

- As portas são identificadores numéricos que permitem que múltiplos processos em um mesmo computador utilizem a rede simultaneamente.

- Elas servem como "pontos de entrada e saída" para a comunicação entre processos locais e remotos.

- Toda comunicação em rede é feita através de uma combinação:  
	IP de origem : Porta de origem → IP de destino : Porta de destino
### Finalidade das Portas

- Diferenciar múltiplos processos que compartilham o mesmo IP.

- Direcionar corretamente os pacotes recebidos para o processo correto.

- Controlar o fluxo de comunicação entre máquinas na rede.

### Classificação das Portas

| Faixa       | Descrição                                   | Exemplos                                                  |
| ----------- | ------------------------------------------- | --------------------------------------------------------- |
| 0–1023      | **Portas conhecidas** (Well-known)          | 22 (SSH), 80 (HTTP), 443 (HTTPS)                          |
| 1024–49151  | **Portas registradas**                      | 5432 (PostgreSQL), 3306 (MySQL)                           |
| 49152–65535 | **Portas dinâmicas/efêmeras** (temporárias) | Atribuídas automaticamente pelo SO para conexões de saída |
### Classificação das Portas: Conhecidas vs. Dinâmicas

As portas são divididas em três grandes categorias, baseadas na forma como são atribuídas e utilizadas pelo sistema operacional.

#### **Portas Conhecidas (Well-Known Ports) [0-1023]**

- **Reservadas para serviços padrão** (definidas pela IANA).

- Aplicações populares sempre usam as mesmas portas, o que facilita a comunicação.

- Exemplos:
- **22** → SSH
- **80** → HTTP
- **443** → HTTPS
- **53** → DNS

#### **Portas Registradas (Registered Ports) [1024-49151]**

- **Designadas para aplicações específicas**, mas não são obrigatórias.

- Softwares podem usá-las para padronizar sua comunicação, mas nada impede que o usuário mude a configuração.

- Exemplos:
- **3306** → MySQL
- **5432** → PostgreSQL
- **27017** → MongoDB

#### **Portas Dinâmicas/Efêmeras (Dynamic/Ephemeral Ports) [49152-65535]**

- **Atribuídas temporariamente pelo sistema operacional** para conexões de saída.

- São utilizadas quando um processo cliente inicia uma conexão com um servidor.

- Cada nova conexão recebe uma porta aleatória dessa faixa, garantindo que não haja conflito entre processos.

- Exemplos:
- Um navegador acessando um site pode usar **49160** para conectar ao **443** (HTTPS) do servidor.

---
### Estado das Portas

#### `LISTEN`
- Indica que há um processo ouvindo nessa porta.
- A porta está aberta e aguardando conexões externas.

#### `ESTABLISHED`
- Indica uma **conexão ativa** entre cliente e servidor.
- Dados estão sendo trocados bidirecionalmente.

#### `CLOSED` / `TIME_WAIT` / etc
- Estados intermediários ou finais em conexões TCP, controlados pela pilha de rede do SO.

---

## Bidirecionalidade das Conexões

- As conexões de rede (ex: TCP) são **bidirecionais**.
- Mesmo que a conexão seja iniciada de um lado (cliente), ambos os lados podem enviar e receber dados.

Exemplo:
```bash
cliente: 192.168.0.10:54231 → servidor: 10.0.2.15:22
```

### Como TCP e UDP se Relacionam com Portas?

#### **Protocolo TCP (Transmission Control Protocol)**

- **Orientado à conexão** → Garante que os dados cheguem corretamente e na ordem certa.

- **Mecanismo de confiabilidade** → Usa técnicas como **handshake (três vias)**, retransmissão de pacotes perdidos e controle de fluxo.

- **Utilização**: Quando a integridade dos dados é essencial.
- Exemplos:
- SSH (porta 22)
- HTTP/HTTPS (portas 80 e 443)
- FTP (porta 21)

#### **Protocolo UDP (User Datagram Protocol)*

- **Não orientado à conexão** → Envia pacotes sem garantir entrega ou ordem correta.

- **Baixa latência** → Ideal para aplicações que priorizam velocidade sobre confiabilidade.

- **Utilização**: Quando a entrega rápida é mais importante que a precisão.

- Exemplos:
- DNS (porta 53)
- Streaming de vídeo (Netflix, YouTube)
- Jogos online e VoIP


### O Papel do Sistema Operacional na Gerência de Portas

O sistema operacional atua como **gerente de portas**, controlando quais processos podem abrir, usar e fechar portas. Algumas funções principais:

#### **Abertura e Alocação de Portas**

- Quando um programa precisa de uma porta específica, ele solicita ao SO.

- Se for um serviço conhecido (ex: SSH na porta 22), ele tenta abrir exatamente essa porta.

- Se for um processo cliente, o SO escolhe uma porta dinâmica livre.

#### **Mapeamento de Portas e Processos**

- Cada porta em estado **LISTEN** pertence a um processo específico.
- Comando para visualizar essa relação:

```bash
sudo ss -tulnp