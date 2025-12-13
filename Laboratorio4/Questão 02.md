# Questão 02

2 -  (Elabore um arquivo com extensão .h e .c) Crie uma função int verifica_positivo_negativo (int n),
que receba um valor e retorne 1 se o número digitado for positivo ou 0 se o número for negativo.

---
### positivo_negativo.h
```c
#ifndef POSITIVO_NEGATIVO_H
#define POSITIVO_NEGATIVO_H

int verifica_positivo_negativo (int n);

#endif
```
### positivo_negativo.c 
```c
#include "positivo_negativo.h"

int verifica_positivo_negativo(int n)
{
    if (n >= 0)
    {
        return 1;
    }
    else
    {
        return 0;
    }
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "positivo_negativo.h"

int main()
{
    int n;
    printf("Diigite um numero: ");
    scanf("%d", &n);
    if (verifica_positivo_negativo(n))
    {
        printf("\nO numero %d e positivo (ou zero).\n", n);
    }
    else
    {
        printf("\nO numero %d e negativo.\n", n);
    }
    return 0;
}