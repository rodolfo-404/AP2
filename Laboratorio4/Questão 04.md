# Questão 04

4 - (Elabore um arquivo com extensão .h e .c) Crie uma função chamada int eh_primo (int num) que
verifica se o valor num (positivo, faça o tratamento de erro antes) que é passado por valor é primo, se
for primo retorne 1 e caso contrário, retorne 0.

---
### verifica_primo.h
```c
#ifndef VERIFICA_PRIMO_H
#define VERIFICA_PRIMO_H

int eh_primo(int num);

#endif
```
### verifica_primo.c 
```c
#include <stdio.h>
#include "verifica_primo.h"

int eh_primo(int num)
{
    if (num <= 1)
    {
        return 0;
    }
    for (int i = 2; i * i <= num; i++)
    {
        if (num % i == 0)
            return 0;
    }
    return 1;
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "verifica_primo.h"

int main()
{
    int n;
    printf("Digite um numero positivo: ");
    scanf("%d", &n);
    if (eh_primo(n))
    {
        printf("%d e primo.\n", n);
    }
    else
    {
        printf("%d nao e primo.\n", n);
    }
    return 0;
}