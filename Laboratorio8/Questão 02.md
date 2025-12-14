# Questão 02

2 - Faça um programa que renomeie o arquivo criado no exercício 1, para MATRICULADOS.TXT.

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
    int resultado = rename("dados.txt", "MATRICULADOS.txt");
    if (resultado == 0)
    {
        printf("Arquivo renomeado\n");
    }
    else
    {
        printf("Erro ao renomear\n");
    }
    fclose(f);
    system("pause");
    return 0;
}