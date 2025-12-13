# Questão 04

4 - Crie uma função int calcula_soma( ), que declare uma variável local int x. A função deverá ler o
valor x e calcular a soma entre x e a variável global num. Ao final, retorna o valor da soma para a
função main( ), para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int num = 5;
int calcula_soma(int x)
{
    return num + x;
}

int main()
{
    setlocale(LC_ALL, "Portuguese");
    int x;
    printf("\nDigite um número inteiro: ");
    scanf("%d", &x);
    int result = calcula_soma(x);
    printf("Valor Global: %d\n", num);
    printf("Valor digitado: %d\n", x);
    printf("Soma: 5 + %d = %d", x, result);
    return 0;
}