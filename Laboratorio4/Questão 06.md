# Questão 06

6 - (Elabore um arquivo com extensão .h e .c) Crie uma calculadora completa separada em módulos
(calculadora.c, calculadora.h).

-> As operações devem ser funções independentes (soma, subtração, multiplicação, divisão, resto da
divisão, potência).

-> O usuário deve escolher a operação em um menu.

---
### calculadora.h
```c
#ifndef CALCULADORA_H
#define CALCULADORA_H

int soma(int a, int b);
int subtrai(int a, int b);
int multiplica(int a, int b);
float divide(int a, int b);
int resto(int a, int b);
int potencia(int a, int b);

#endif
```
### calculadora.c 
```c
#include <stdio.h>
#include "calculadora.h"

int soma(int a, int b)
{
    return a + b;
}
int subtrai(int a, int b)
{
    return a - b;
}
int multiplica(int a, int b)
{
    return a * b;
}
float divide(int a, int b)
{
    if (b == 0)
    {
        printf("\nErro. Divisao por zero.\n");
        return 0;
    }
    return (float)a / b;
}
int resto(int a, int b)
{
    if (b == 0)
    {
        printf("\nErro. Divisao por zero.\n");
        return 0;
    }
    return a % b;
}
int potencia(int base, int expoente)
{
    int resultado = 1;
    for (int i = 0; i < expoente; i++)
    {
        resultado *= base;
    }
    return resultado;
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "calculadora.h"

int main()
{
    int opcao, a, b;
    do
    {
        printf("\n==== CALCULADORA ====\n");
        printf("1 - Soma\n");
        printf("2 - Subtracao\n");
        printf("3 - Multiplicacao\n");
        printf("4 - Divisao\n");
        printf("5 - Resto da divisao\n");
        printf("6 - Potencia\n");
        printf("0 - Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);
        if (opcao == 0)
        {
            printf("\nEncerrando calculadora\n");
            break;
        }
        printf("\nDigite dois numeros: ");
        scanf("%d %d", &a, &b);
        switch (opcao)
        {
        case 1:
            printf("\nResultado: %d\n", soma(a, b));
            break;
        case 2:
            printf("\nResultado: %d\n", subtrai(a, b));
            break;
        case 3:
            printf("\nResultado: %d\n", multiplica(a, b));
            break;
        case 4:
            printf("\nResultado: %.2f\n", divide(a, b));
            break;
        case 5:
            printf("\nResultado: %d\n", resto(a, b));
            break;
        case 6:
            printf("\nResultado: %d\n", potencia(a, b));
            break;
        default:
            printf("\nOpcao invalida!\n");
        }
    } while (opcao != 0);
    return 0;
}