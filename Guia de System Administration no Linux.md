## O que é System Administration?

System Administration (Administração de Sistemas) é a prática de gerenciar, configurar e manter sistemas operacionais, redes e serviços essenciais em um ambiente de computação. O administrador de sistemas (sysadmin) lida com instalação de software, gerenciamento de usuários, configuração de rede, segurança e monitoramento de desempenho.

---

## Comandos Essenciais

### 1. Gerenciamento de Arquivos e Diretórios

| Comando                    | Descrição                          |
| -------------------------- | ---------------------------------- |
| `ls`                       | Lista arquivos e diretórios        |
| `pwd`                      | Mostra o diretório atual           |
| `cd <dir>`                 | Navega para o diretório `<dir>`    |
| `mkdir <dir>`              | Cria um diretório                  |
| `rm <file>`                | Remove um arquivo                  |
| `rm -r <dir>`              | Remove um diretório recursivamente |
| `cp <origem> <destino>`    | Copia arquivos ou diretórios       |
| `mv <origem> <destino>`    | Move ou renomeia arquivos          |
| `find <dir> -name "*.txt"` | Busca arquivos dentro de `<dir>`   |
| `df -h`                    | Mostra espaço disponível no disco  |
| `du -sh <dir>`             | Mostra o tamanho de um diretório   |

---

### 2. Gerenciamento de Usuários e Permissões

|   |   |
|---|---|
|Comando|Descrição|
|`whoami`|Mostra o usuário atual|
|`id`|Mostra informações sobre o usuário|
|`adduser <user>`|Cria um novo usuário|
|`passwd <user>`|Altera a senha de um usuário|
|`usermod -aG <grupo> <user>`|Adiciona um usuário a um grupo|
|`groups <user>`|Lista os grupos de um usuário|
|`chmod 755 <file>`|Modifica permissões de arquivos|
|`chown user:group <file>`|Altera o dono de um arquivo|
|`sudo`|Executa um comando como superusuário|

---

### 3. Configuração de Rede

|   |   |
|---|---|
|Comando|Descrição|
|`ip a`|Mostra interfaces de rede e IPs|
|`ip r`|Exibe a tabela de roteamento|
|`ping <host>`|Testa conectividade com um host|
|`nslookup <domínio>`|Obtém informações de DNS|
|`traceroute <host>`|Mostra o caminho de pacotes até um destino|
|`netstat -tulnp`|Lista portas abertas e processos associados|
|`ss -tulnp`|Alternativa moderna ao `netstat`|
|`curl -I <URL>`|Obtém o cabeçalho HTTP de um site|
|`wget <URL>`|Faz download de um arquivo|

---

### 4. Processos e Monitoramento do Sistema

|   |   |
|---|---|
|Comando|Descrição|
|`ps aux`|Lista processos ativos|
|`top`|Exibe processos em tempo real|
|`htop`|Versão interativa do `top` (pode precisar de instalação)|
|`kill <PID>`|Encerra um processo pelo PID|
|`killall <nome>`|Encerra todos os processos com um nome específico|
|`nice -n <valor> <comando>`|Define prioridade de um processo|
|`renice <valor> -p <PID>`|Altera prioridade de um processo em execução|

---

###  Segurança e Controle de Acesso

|   |   |
|---|---|
|Comando|Descrição|
|`sudo ufw enable`|Ativa o firewall UFW|
|`sudo ufw allow <porta>`|Abre uma porta específica|
|`sudo ufw deny <porta>`|Bloqueia uma porta específica|
|`sudo ufw status`|Exibe o status do firewall|
|`sudo fail2ban-client status`|Exibe o status do Fail2Ban (proteção contra brute-force)|
|`history`|Mostra o histórico de comandos|
|`alias ll='ls -la'`|Cria um alias para comandos|

---

### 6. Gerenciamento de Serviços e Logs

|   |   |
|---|---|
|Comando|Descrição|
|`systemctl status <serviço>`|Verifica o status de um serviço|
|`systemctl start <serviço>`|Inicia um serviço|
|`systemctl stop <serviço>`|Para um serviço|
|`systemctl restart <serviço>`|Reinicia um serviço|
|`systemctl enable <serviço>`|Ativa um serviço para iniciar no boot|
|`systemctl disable <serviço>`|Desativa um serviço no boot|
|`journalctl -u <serviço>`|Exibe logs de um serviço específico|
|`tail -f /var/log/syslog`|Monitora logs do sistema em tempo real|

---

## 🎭 7. Virtualização e Contêineres (Conceito)

- **QEMU** → Virtualização de máquinas completas.
    
- **Docker** → Contêineres leves para executar aplicações isoladas.
    
- **LXC/LXD** → Contêineres semelhantes ao Docker, mas mais próximos de VMs.
    
- **KVM** → Virtualização nativa no Linux usando hardware.
    
- **Virt-Manager** → Interface gráfica para gerenciar VMs com QEMU/KVM.