
Structs são tipos de dados compostos que permitem agrupar variáveis de diferentes tipos sob um mesmo nome, facilitando a modelagem de entidades do mundo real (pessoas, produtos, datas etc.).

## Definição de `struct`

```c
struct Pessoa {
    char nome[50];
    int idade;
    float altura;
};
```

## `typedef` para structs

```c
typedef struct {
    char nome[50];
    int idade;
    float altura;
} Pessoa;
```

## Declaração de variáveis

```c
struct Pessoa p1;
Pessoa p2;
```

## Acessando campos

Variável direta:

```c
p1.idade = 25;
strcpy(p1.nome, "João");
```

Ponteiro para struct:

```c
Pessoa *ptr = &p1;
ptr->altura = 1.75f;   // equivalente a (*ptr).altura = 1.75f;
```

## Passagem de structs para funções

Por valor:

```c
void imprimePessoa(Pessoa p) {
    printf("%s — %d anos\n", p.nome, p.idade);
}
```

Por referência:

```c
void atualizaIdade(Pessoa *p, int novaIdade) {
    p->idade = novaIdade;
}
```

## Structs aninhadas

```c
typedef struct {
    int dia, mes, ano;
} Data;

typedef struct {
    char nome[50];
    Data nascimento;
} Pessoa;
```

Exemplo de uso:

```c
Pessoa p;
strcpy(p.nome, "Ana");
p.nascimento.dia = 15;
p.nascimento.mes = 8;
p.nascimento.ano = 1995;
```

## Arrays de structs

```c
Pessoa turma[3];
strcpy(turma[0].nome, "Carlos");
turma[0].idade = 22;
strcpy(turma[1].nome, "Beatriz");
turma[1].idade = 21;
strcpy(turma[2].nome, "Diego");
turma[2].idade = 23;
```

## Alocação dinâmica de structs

```c
Pessoa *aluno = malloc(sizeof(Pessoa));
strcpy(aluno->nome, "Felipe");
aluno->idade  = 20;
aluno->altura = 1.82f;
free(aluno);
```

## Array dinâmico de structs

```c
Pessoa *grupo = malloc(5 * sizeof(Pessoa));
for (int i = 0; i < 5; i++) {
    sprintf(grupo[i].nome, "Aluno %d", i+1);
    grupo[i].idade  = 18 + i;
    grupo[i].altura = 1.70f + 0.02f * i;
}
free(grupo);
```

## Ponteiro de ponteiro para structs

```c
Pessoa **mat = malloc(3 * sizeof(Pessoa*));
for (int i = 0; i < 3; i++) {
    mat[i] = malloc(4 * sizeof(Pessoa));
}
strcpy(mat[1][2].nome, "Larissa");
mat[1][2].idade  = 19;
mat[1][2].altura = 1.65f;
for (int i = 0; i < 3; i++) {
    free(mat[i]);
}
free(mat);
```

## Resumo

- `struct`: agrupa campos relacionados sob um único tipo  
- `typedef`: cria apelidos para tipos complexos  
- acesso a campos: `.` (variável direta) e `->` (ponteiro)  
- aninhamento: structs podem conter outras structs  
- arrays: suportados estáticos e dinâmicos  
- alocação dinâmica: `malloc`/`free`  
- ponteiro de ponteiro: matrizes dinâmicas de structs  
