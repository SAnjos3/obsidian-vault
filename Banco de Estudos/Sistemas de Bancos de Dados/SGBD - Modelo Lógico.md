O **modelo lógico** é a **representação dos dados com foco na estrutura lógica que será interpretada por um SGBD** (Sistema Gerenciador de Banco de Dados), sem ainda se preocupar com aspectos físicos, como tipos de armazenamento ou desempenho.

Dentro da [[SGBD - Arquitetura Three-Schema]] o Modelo Lógico **é a ponte entre o modelo conceitual e o modelo físico.**

- Traduz o modelo conceitual para uma estrutura lógica próxima do que o SGBD vai usar.
    
- Define **tipos de dados**, **restrições**, **chaves primárias e estrangeiras**, **relacionamentos normalizados**, etc.
    
- Serve como base para a **implementação física** do banco de dados.
    
- Garante que a estrutura lógica seja **compatível com o modelo suportado pelo SGBD escolhido** (relacional, hierárquico, etc).

#### **Modelo em Rede**

- Os **dados são representados por registros**, e as relações entre eles são **links (ponteiros)**.
    
- Os registros são organizados como **grafos** (ou seja, estruturas com nós e conexões flexíveis).
    
- Permite que um registro tenha **vários relacionamentos diretos com outros registros** (n-m).
    
- Bastante usado em sistemas legados.
    

>**Exemplo:** IDMS (Integrated Database Management System)

---

#### 🌲 **Modelo Hierárquico**

- É semelhante ao modelo em rede, mas com uma **organização em forma de árvore**.
    
- Cada registro **filho tem apenas um pai**, o que gera uma estrutura rígida.
    
- Os dados são organizados de forma **hierárquica**, e os acessos seguem o caminho da árvore.
    

> 🛠 **Exemplo clássico:** **IMS (Information Management System)** da IBM

---

#### **[[SGBD - ML -  Modelo Relacional]]** (o mais utilizado atualmente)

- Representa os dados em **tabelas (ou relações)**.
    
- Os relacionamentos entre dados são feitos **por meio de valores comuns**, **não por links**.
    
- É baseado em fundamentos matemáticos:
    
    - **Álgebra Relacional**
        
    - **Cálculo Relacional**
        
- Proporciona independência lógica dos dados, flexibilidade e padronização (ex: SQL).
    

>  **Exemplo:** MySQL, PostgreSQL, Oracle, SQL Server  
> **Precursor:** **Sistema R** da IBM