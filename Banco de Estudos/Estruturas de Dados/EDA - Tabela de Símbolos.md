Tabela de símbolos é uma estrutura de dados que guarda dados em pares (chaves e valores). Assim quando navega-se por essa estrutura, entrega-se uma chave para ser retornado um valor.

Uma **tabela de símbolos pode ser implementada de várias formas**:

| Implementação                 | Busca     | Inserção  | Remoção   | Ordenado? | Observações                                |
| ----------------------------- | --------- | --------- | --------- | --------- | ------------------------------------------ |
| Lista Encadeada não ordenada  | O(n)      | O(1)      | O(n)      | ❌         | Muito simples, mas lenta para buscas       |
| Lista Encadeada ordenada      | O(n)      | O(n)      | O(n)      | ✅         | Pouco usada hoje em dia                    |
| Array ordenado                | O(log n)  | O(n)      | O(n)      | ✅         | Boa para busca binária, ruim para inserção |
| Árvore Binária de Busca (BST) | O(log n)* | O(log n)* | O(log n)* | ✅         | Depende do balanceamento                   |
| Árvore Red-Black              | O(log n)  | O(log n)  | O(log n)  | ✅         | Sempre balanceada                          |
| [[EDA - Tabela Hash]]         | O(1)**    | O(1)**    | O(1)**    | ❌         | Extremamente rápida, mas sem ordenação     |

Exemplo de implementação básica de uma tabela de símbolos:

``` C
#define key int;

#define maxIntens 1000000;

#define less (A,B){ (key(A) < key(B)) }

#define key(A) (A.k)

#define eq (A,B) (key(A) == key(B))

#define STswap (Ai, Bi){ item tmp = Ai; Ai = Bi; B = temp; }

typedef struct {
	key k;
	data d;
}

int STinit(){
	st = malloc(sizeof(item) * maxItens);
	
	if(st == null) return 0;
		
	return 1;
}

void STinsert (item ni) {
	st[st_last++] = ni;
} 

int STempty(){
	return st_last == 0;
}

int STcount(){
	return st_last
}

int STsearch(key i){
	for(int i=0; i < st_last; i++){
		if(eq((item){ .key = s }, st[i])) return st[i]
	}
}

int STremove(key r){
	int toremove = STsearch(r);
	STswap(st[toremove],st[st_last-1]);
	st_last--;
}

```

 Essa implementação, por não ser ordenada, apresenta uma inserção de O(1), porem uma busca sequencial, ou seja, O(n). 
 Caso a fosse ordenado já na inserção, teríamos que STinsert(n), enquanto a busca seria O(log n).
Levando isso em consideração, essa solução não seria a melhor implementação. Assim, surge-se a ideia de busca direta.
 
``` C
# define NULLitem (item){-1}

STinit(){
	st = malloc(sizeof(item)*maxItens)
	for(int i=0; i < maxItens; i++){
		st[i] = NULLitem;
	}
}
STinsert(item ni){
	st[key(ni)] = ni;
}
STsearch(key s){

}

```

Essa implementação tem suas vantagens ao considerar que a busca e a inserção se tornam O(1) simultaneamente, resolvendo o problema da implementação anterior. 
Porém, ao criar a tabela de símbolos e acessa-la por ponteiros, seria necessário atribuir às posições vazias um valor de NULL, para diferenciarmos ela das não vazias.
E por isso a complexidade chega a maxItens.