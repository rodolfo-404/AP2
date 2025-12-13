# Questão 03

3 -  (Elabore um arquivo com extensão .h e .c) Crie a função int calcula_mdc (int a, int b), que calcule o
máximo divisor comum entre os dois valores. Use o algoritmo de Euclides.

---

### calculamdc.h
```c
#ifndef CALCULAMDC_H
#define CALCULAMDC_H

int calcula_mdc(int a, int b);

#endif
```
### calculamdc.c 
```c
#include "calculamdc.h"

int calcula_mdc(int a, int b)
{
    int resto;
    while (b != 0)
    {
        resto = a % b;
        a = b;
        b = resto;
    }
    return a;
}

```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "calculamdc.h"

int main()
{
    int x, y;
    printf("Digite dois numeros: ");
    scanf("%d %d", &x, &y);
    printf("O MDC entre %d e %d e igual a %d\n", x, y, calcula_mdc(x, y));
    gg return 0;
}