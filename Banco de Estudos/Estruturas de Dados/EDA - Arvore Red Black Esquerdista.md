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
#include <stdio.h>
#include <stdlib.h>

#define RED 1
#define BLACK 0

typedef struct Node {
    int key;
    int color;
    struct Node *left, *right;
} Node;

int isRed(Node* node) {
    if (node == NULL) return 0;
    return node->color == RED;
}

Node* rotateLeft(Node* h) {
    Node* x = h->right;
    h->right = x->left;
    x->left = h;
    x->color = h->color;
    h->color = RED;
    return x;
}

Node* rotateRight(Node* h) {
    Node* x = h->left;
    h->left = x->right;
    x->right = h;
    x->color = h->color;
    h->color = RED;
    return x;
}

void flipColors(Node* h) {
    h->color = RED;
    if (h->left) h->left->color = BLACK;
    if (h->right) h->right->color = BLACK;
}

Node* balance(Node* h) {
    if (isRed(h->right) && !isRed(h->left)) h = rotateLeft(h);
    if (isRed(h->left) && isRed(h->left->left)) h = rotateRight(h);
    if (isRed(h->left) && isRed(h->right)) flipColors(h);
    return h;
}

Node* insert(Node* h, int key) {
    if (h == NULL) {
        Node* node = malloc(sizeof(Node));
        node->key = key;
        node->left = node->right = NULL;
        node->color = RED;
        return node;
    }
    

    if (key < h->key)
        h->left = insert(h->left, key);
    else if (key > h->key)
        h->right = insert(h->right, key);
    else
        ; // chave já existe, não faz nada

    h = balance(h);
    h->color = 0;'
    return h;
}

void printInOrder(Node* root) {
    if (root == NULL) return;
    printInOrder(root->left);
    printf("%d (%s) ", root->key, root->color == RED ? "R" : "B");
    printInOrder(root->right);
}

void freeTree(Node* root) {
    if (!root) return;
    freeTree(root->left);
    freeTree(root->right);
    free(root);
}

int main() {
    Node* root = NULL;
    int keys[] = {10, 20, 30, 15, 5, 1};
    int n = sizeof(keys) / sizeof(int);

    for (int i = 0; i < n; ++i) {
        root = insert(root, keys[i]);
        root->color = BLACK; // a raiz sempre deve ser preta
    }

    printf("Árvore em ordem:\n");
    printInOrder(root);

    freeTree(root);
    return 0;
}

```

A inserção nessa arvore é complicada,