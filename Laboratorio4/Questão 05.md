# Questão 05

5 -  (Elabore um arquivo com extensão .h e .c) Crie o módulo int eh_triangulo (int a, int b, int c), que
verifique se os valores passados formam um triângulo e se formarem o triângulo, imprima na tela o tipo
de triângulo. A função eh_triangulo (int a, int b, int c) só será invocada se os valores formarem um
triângulo e apresenta os seguintes retornos:

1 - Triângulo escaleno;
2 - Triângulo isósceles;
3 - Triângulo equilátero.

---
### triangulo.h
```c
#ifndef TRIANGULO_H
#define TRIANGULO_H

int eh_triangulo(int a, int b, int c);

#endif
```
### triangulo.c 
```c
#include <stdio.h>
#include "triangulo.h"

int eh_triangulo(int a, int b, int c)
{
    if (a == b && b == c)
    {
        printf("Triangulo equilatero\n");
        return 3;
    }
    else if (a == b || a == c || b == c)
    {
        printf("Triangulo isosceles\n");
        return 2;
    }
    else
    {
        printf("Triangulo escaleno\n");
        return 1;
    }
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "triangulo.h"

int main()
{
    int a, b, c;
    printf("Digite os lados do triangulo: ");
    scanf("%d %d %d", &a, &b, &c);
    if (a + b > c && a + c > b && b + c > a)
    {
        int tipo = eh_triangulo(a, b, c);
    }
    else
    {
        printf("Os valores nao formam um triangulo\n");
    }
    return 0;
}