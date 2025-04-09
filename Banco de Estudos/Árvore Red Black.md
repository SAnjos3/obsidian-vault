Definição: Uma BST rubo-negra  é uma BST cujo os links são negros e rubros e têm as seguintes propriedades:

- Links rubro se inclinam para a esquerda;

- Nenhum nó incide em dois links rubros.

-  Balanceamento negro perfeito: todo caminho da raiz até "z" tem o mesmo número de links negros.

 - Se links rubros forem desenhados horizontalmente e depois contraídos , teremos uma árvore 2-3:

- Todos os links "z" estão à mesma profundidade negra:

- A profundidade negra de um nó "x" é o número de links negros no caminho da raiz até "x".

- A altura negra da árvore é o máximo da profundidade negra de todos os nós

-  A informação sobre o link ser rubro ou negro é armazenada nos nós.

```C
enum tipo {RED, BLACK}
#define RED 0
#define BlACK 1
typedef struct STNOde* link;
struct STNode {Item item; link l; r; int N; link h; link z;
link NEW(Item item, link l, link r, int N){
link x = malloc(sizeof(*x));
x -> Item = item; x->l=l; x->r=r; n->n=n;
return x;
}

}
```

A inserção nessa arvore é complicada,