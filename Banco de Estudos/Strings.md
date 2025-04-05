Antes de pensarmos em strings, devemos levar em consideração o conceito de caracteres na linguagem C.

```C
char a;
```

Quando estamos falando de linguagens de programação, tudo é números. A diferença entre esses números é a abstração feita para de adequar a linguagem humana. Chars também são considerados números, mais especificamento falando:

`char -> 8 bits, 1 byte, 0 ~ 255, -127 ~ 127

A abstração dos números em formato de char é feito por meio de uma tabela chamada ASCII, essa tabela relaciona valores em bits com os símbolos (chars).

Ao abordar o conceito de strings, percebe-se que uma palavra é um conjunto de caracteres, assim, uma string em uma linguagem de programação é definido por um vetor de chars.

Em C, as strings contém um caracter especial, que é conhecido como "EOS" (End of String) e em C ele tem a seguinte aparência:

` 0 - '\0' `

Em C, por exemplo, uma string será printada até que seja encontrado esse caracter especial.  A falta desse caracter causa erro no algorítimo. Levando isso em consideração, quando se inicia uma string, é necessário levar em consideração esse caracter.

```C
char palavra[10]
scanf("%s",palavra);

// Entrada: "123456789"
// palavra[10] para armazenar a string que contém apenas 9 caracteres, isso porque na verdade tem-se:
// palavra = "123456789\0"

palavra = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "\0"];
```