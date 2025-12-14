# exercicios.c

Onde as funções dos exercícios são implementadas.
---
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
#include <string.h>
#include <ctype.h>
#include "exercicios.h"

int troca(int *a, int *b)
{
    int aux;
    aux = *a;
    *a = *b;
    *b = aux;
    return 0;
}

int funcao(int *a, int *b)
{
    (*a)--;
    (*b)++;
    return 0;
}

int exercicio_1()
{
    int n;
    printf("\n-------Exercicio 1 Selecionado-------\n");
    int a, b;
    printf("\nDigite dois numeros\n");
    scanf("%d %d", &a, &b);
    printf("\nValores digitados: \n");
    printf("A = %d \t | \t %d\n", a, &a);
    printf("B = %d \t | \t %d\n", b, &b);
    troca(&a, &b);
    printf("\nValores trocados: \n");
    printf("A = %d \t | \t %d\n", a, &a);
    printf("B = %d \t | \t %d\n", b, &b);
    funcao(&a, &b);
    printf("\nValor decrementado: A = %d \t | %d\n", a, &a);
    printf("Valor incrementado: B = %d \t | %d\n", b, &b);
    printf("\n-------Fim do Exercicio 1-------\n");
    return 0;
}

int ehvogal(char letra)
{
    letra = tolower(letra);
    if (letra == 'a' || letra == 'e' || letra == 'i' || letra == 'o' || letra == 'u')
    {
        return 1;
    }
    return 0;
}

void contarvogal(char frase[], char vogal, int *v)
{
    int i;
    *v = 0;
    for (i = 0; frase[i] != '\0'; i++)
    {
        if (tolower(frase[i]) == vogal)
        {
            (*v)++;
        }
    }
}

int exercicio_2()
{
    int contador = 0;
    char frase[100];
    char letra[10];
    printf("\n-------Exercicio 2 Selecionado-------\n");
    int c;
    while ((c = getchar()) != '\n' && c != EOF)
    {
    }
    printf("\nDigite uma frase: ");
    fgets(frase, 100, stdin);
    printf("\nDigite uma vogal: ");
    fgets(letra, 10, stdin);
    printf("\nLetra: %c\n", letra[0]);
    if (ehvogal(letra[0]))
    {
        contarvogal(frase, letra[0], &contador);
        printf("\nA letra %c apareceu %d vezes.\n", tolower(letra[0]), contador);
    }
    else
    {
        printf("\nA letra informada nao e vogal.\n");
    }
    printf("\n-------Fim do Exercicio 2-------\n");
    return 0;
}

void altera(habitante *x)
{
    int c;
    while ((c = getchar()) != '\n' && c != EOF)
    {
    }
    printf("\nDigite seu nome: ");
    fgets(x->nome, 50, stdin);
    x->nome[strcspn(x->nome, "\n")] = '\0';
    printf("\nDigite sua idade: ");
    scanf("%d", &x->idade);
    while ((c = getchar()) != '\n' && c != EOF)
    {
    }
    printf("\nSexo: ");
    fgets(x->sexo, 15, stdin);
    x->sexo[strcspn(x->sexo, "\n")] = '\0';
    printf("\nDigite seu salario: ");
    scanf("%f", &x->salario);
    while ((c = getchar()) != '\n' && c != EOF)
    {
    }
    printf("\nNumero de filhos: ");
    scanf("%d", &x->numfilhos);
    while ((c = getchar()) != '\n' && c != EOF)
    {
    }
}

void exibe(habitante *x)
{
    printf("\nNome: %s\n", x->nome);
    printf("Idade: %d\n", x->idade);
    printf("Sexo: %s\n", x->sexo);
    printf("Salario: %.2f\n", x->salario);
    printf("Numero de filhos: %d filhos\n", x->numfilhos);
}

int exercicio_3()
{
    printf("\n-------Exercicio 3 Selecionado-------\n");
    habitante h;
    altera(&h);
    exibe(&h);
    printf("\n-------Fim do Exercicio 3-------\n");
    return 0;
}

void min_multiplica(int vetor[], int *xmin, int n)
{
    int i;
    *xmin = vetor[0];
    for (i = 1; i < n; i++)
    {
        if (vetor[i] < *xmin)
            *xmin = vetor[i];
    }
    for (i = 0; i < n; i++)
    {
        vetor[i] = vetor[i] * (*xmin);
    }
}

int exercicio_4()
{
    printf("\n-------Exercicio 4 Selecionado-------\n");
    int vetor[10];
    int xmin;
    int n;
    int i;
    printf("\nQuantos elementos o vetor tera?\n");
    scanf("%d", &n);
    if (n <= 0 || n > 10)
    {
        printf("Tamanho invalido de vetor.\n");
        return 0;
    }
    for (i = 0; i < n; i++)
    {
        printf("Digite o elemento %d: ", i + 1);
        scanf("%d", &vetor[i]);
    }
    printf("\nVetor digitado: ");
    for (int i = 0; i < n; i++)
    {
        printf("[%d]", vetor[i]);
    }
    min_multiplica(vetor, &xmin, n);
    printf("\nMenor elemento: %d\n", xmin);
    printf("\nVetor multiplicado:\n");
    for (int i = 0; i < n; i++)
    {
        printf("[%d]", vetor[i]);
    }
    printf("\n-------Fim do Exercicio 4-------\n");
    return 0;
}

void crescente(int *a, int *b, int *c)
{
    int aux;
    if (*a > *b)
    {
        aux = *a;
        *a = *b;
        *b = aux;
    }
    if (*a > *c)
    {
        aux = *a;
        *a = *c;
        *c = aux;
    }
    if (*b > *c)
    {
        aux = *b;
        *b = *c;
        *c = aux;
    }
}

int exercicio_5()
{
    int a;
    int b;
    int c;
    printf("\n-------Exercicio 5 Selecionado-------\n");
    printf("\nDigite tres valores inteiros:\n");
    scanf("%d %d %d", &a, &b, &c);
    crescente(&a, &b, &c);
    printf("\nValores organizados em ordem crescente:\n");
    printf("%d \t|\t %d\n%d \t|\t %d\n%d \t|\t %d\n", a, &a, b, &b, c, &c);
    printf("\n-------Fim do Exercicio 5-------\n");
    return 0;
}

float soma(float *v, int tamanho)
{
    float total = 0;
    for (int i = 0; i < tamanho; i++)
    {
        total += v[i];
    }
    return total;
}

float media(float *soma, int tamanho)
{
    return *soma / tamanho;
}

float desvio(float *v, float media, int tamanho)
{
    float soma = 0;
    for (int i = 0; i < tamanho; i++)
    {
        soma += pow(v[i] - media, 2);
    }
    return sqrt(soma / tamanho);
}

void substitui(float *v, int tamanho)
{
    for (int i = 0; i < tamanho; i++)
    {
        if (v[i] < 0)
            v[i] = 0;
    }
}

int exercicio_6()
{
    float v[5];
    int tamanho = 5;
    printf("\n-------Exercicio 6 Selecionado-------\n");
    for (int i = 0; i < tamanho; i++)
    {
        printf("\nDigite o valor %d do vetor:\n", i + 1);
        scanf("%f", &v[i]);
    }
    printf("\nVetor original:\n");
    for (int i = 0; i < tamanho; i++)
    {
        printf("[%.2f] ", v[i]);
    }
    substitui(v, tamanho);
    printf("\nVetor apos substituir negativos por zero:\n");
    for (int i = 0; i < tamanho; i++)
    {
        printf("[%.2f] ", v[i]);
    }
    float s = soma(v, tamanho);
    float m = media(&s, tamanho);
    float d = desvio(v, m, tamanho);
    printf("\nSoma dos valores: %.2f", s);
    printf("\nMedia dos valores: %.2f", m);
    printf("\nDesvio padrao: %.2f", d);
    printf("\n-------Fim do Exercicio 6-------\n");
    return 0;
}