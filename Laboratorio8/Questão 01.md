# Questão 01

1 - Faça um programa que crie um arquivo TEXTO em disco, com o nome ?dados.txt? e escreva
neste arquivo em disco uma contagem de 20 em 20, que vá de 0 até 1000, com um número em
cada linha.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main()
{
    FILE *f;
    f = fopen("dados.txt", "w");
    if (f == NULL)
    {
        printf("Erro na abertura\n");
        system("pause");
        exit(1);
    }
    int n = 0;
    int i;
    for (i = 0; i <= 50; i++)
    {
        fprintf(f, "%d\n", n);
        n += 20;
    }
    fclose(f);
    system("pause");
    return 0;
}