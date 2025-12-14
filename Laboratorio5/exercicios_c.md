# exercicios.c
Onde as funções dos exercícios são implementadas

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
#include <string.h>
#include "exercicios.h"

int func_g(int n)
{
    if (n == 0)
    {
        return 0;
    }
    else
    {
        printf("%d\n", n);
        return func_g(n - 1);
    }
}
int exercicio_1()
{
    int n;
    printf("\n-------Exercicio 1 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 0)
    {
        printf("Apenas numeros positivos\n");
        return 1;
    }
    printf("%d\n", func_g(n));
    printf("\n-------Fim do Exercicio 1-------\n");
    return 0;
}

int func_h(int n)
{
    if (n == 1)
    {
        return 1;
    }
    else
    {
        return n + func_h(n - 1);
    }
}
int exercicio_2()
{
    int n;
    printf("\n-------Exercicio 2 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 0)
    {
        printf("Apenas numeros positivos\n");
        return 1;
    }
    printf("Soma de 1 ate %d: %d\n", n, func_h(n));
    printf("\n-------Fim do Exercicio 2-------\n");
    return 0;
}

int func_j(int n)
{
    if (n == 0 || n == 1)
    {
        return 1;
    }
    else
    {
        return n * func_j(n - 1);
    }
}
int exercicio_3()
{
    int n;
    printf("\n-------Exercicio 3 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 0)
    {
        printf("Apenas numeros positivos\n");
        return 1;
    }
    printf("Resultado do fatorial de %d: %d\n", n, func_j(n));
    printf("\n-------Fim do Exercicio 3-------\n");
    return 0;
}

int func_k(int n, int e)
{
    if (e == 0)
    {
        return 1;
    }
    else
    {
        return n * func_k(n, e - 1);
    }
}
int exercicio_4()
{
    int n, e;
    printf("\n-------Exercicio 4 Selecionado-------\n");
    printf("\nDigite um numero inteiro para ser a base: ");
    scanf("%d", &n);
    printf("\nDigite outro numero inteiro para ser o expoente: ");
    scanf("%d", &e);
    if (e < 0)
    {
        printf("Apenas numeros positivos no expoente\n");
        return 1;
    }
    else
        printf("Resultado de %d elevado a %d: %d", n, e, func_k(n, e));
    printf("\n-------Fim do Exercicio 4-------\n");
    return 0;
}

int func_b(int n)
{
    if (n == 0)
    {
        return 0;
    }
    else if (n == 1)
    {
        return 1;
    }
    else
    {
        return func_b(n - 1) + func_b(n - 2);
    }
}
int exercicio_5()
{
    int n;
    printf("\n-------Exercicio 5 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 0)
    {
        printf("Apenas numeros positivos\n");
        return 1;
    }
    printf("%d termo da sequencia de Fibonacci: %d\n", n, func_b(n));
    printf("\n-------Fim do Exercicio 5-------\n");
    return 0;
}

int func_digit(int n)
{
    if (n < 10)
    {
        return 1;
    }
    else
    {
        return 1 + func_digit(n / 10);
    }
}
int exercicio_6()
{
    int n;
    printf("\n-------Exercicio 6 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 1)
    {
        printf("Apenas numeros maiores que zero\n");
        return 1;
    }
    printf("Quantidade de digitos do numero %d: %d digitos\n", n,
           func_digit(n));
    printf("\n-------Fim do Exercicio 6-------\n");
    return 0;
}

int func_primo(int n, int d)
{
    if (n < 2)
    {
        return 0;
    }
    if (d == 1)
    {
        return 1;
    }
    if (n % d == 0)
    {
        return 0;
    }
    return func_primo(n, d - 1);
}
int exercicio_7()
{
    int n, d;
    printf("\n-------Exercicio 7 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 0)
    {
        printf("Apenas numeros positivos\n");
        return 1;
    }
    if (func_primo(n, n - 1))
    {
        printf("%d e primo\n", n);
    }
    else
    {
        printf("%d nao e primo\n", n);
    }
    printf("\n-------Fim do Exercicio 7-------\n");
    return 0;
}

int func_invert(int n, int d)
{
    if (n == 0)
        return 0;
    return (n % 10) * pow(10, d - 1) + func_invert(n / 10, d - 1);
}
int exercicio_8()
{
    int n;
    printf("\n-------Exercicio 8 Selecionado-------\n");
    printf("\nDigite um numero inteiro: ");
    scanf("%d", &n);
    if (n < 1)
    {
        printf("Apenas numeros maiores que zero\n");
        return 1;
    }
    int d = func_digit(n);
    printf("Numero original: %d\n", n);
    printf("Numero invertido: %d\n", func_invert(n, d));
    printf("\n-------Fim do Exercicio 8-------\n");
    return 0;
}

int func_mdc(int n, int i)
{
    if (i == 0)
    {
        return n;
    }
    else
    {
        return func_mdc(i, n % i);
    }
}
int exercicio_9()
{
    int n, i;
    printf("\n-------Exercicio 9 Selecionado-------\n");
    printf("\nDigite dois numeros inteiros para calcular MDC: ");
    scanf("%d %d", &n, &i);
    if ((n < 0) || (i < 0))
    {
        printf("Apenas numeros maiores que zero\n");
        return 1;
    }
    printf("O resultado do MDC entre %d e %d e igual a %d\n", n, i,
           func_mdc(n, i));
    printf("\n-------Fim do Exercicio 9-------\n");
    return 0;
}

int func_p(char str[], int inicio, int fim)
{
    if (inicio >= fim)
        return 1;
    if (str[inicio] != str[fim])
        return 0;
    return func_p(str, inicio + 1, fim - 1);
}
int exercicio_10()
{
    char palavra[100];
    printf("\n-------Exercicio 10 Selecionado-------\n");
    printf("Digite uma palavra: ");
    scanf("%s", palavra);
    if (func_p(palavra, 0, strlen(palavra) - 1))
    {
        printf("Palindromo\n");
    }
    else
    {
        printf("Nao e palindromo\n");
    }
}