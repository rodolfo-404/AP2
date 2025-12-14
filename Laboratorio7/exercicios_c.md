# exercicios.c

Onde as funções dos exercícios são implementadas.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>
#include "exercicios.h"

int exercicio_8()
{
    printf("\n-------Exercicio 8 Selecionado-------\n");
    int a = 15;
    int *p;
    p = &a;
    printf("Antigo valor de A: %d\n", a);
    *p = 10;
    printf("Valor de A alterado: %d\n", a);
    printf("\n-------Fim do Exercicio 8-------\n");
    return 0;
}

int exercicio_9()
{
    printf("\n-------Exercicio 9 Selecionado-------\n");
    char str[] = "sao paulo futebol clube";
    char *p;
    p = str;
    printf("\nAntes: %s\n", str);
    do
    {
        *p = toupper(*p);
        p++;
    } while (*p != '\0');
    printf("Depois: %s\n", str);
    printf("\n-------Fim do Exercicio 9-------\n");
    return 0;
}

int soma(int s, int *p)
{
    for (int i = 0; i < 5; i++)
    {
        s += *p;
        p++;
    }
    return s;
}

int exercicio_10()
{
    printf("\n-------Exercicio 10 Selecionado-------\n");
    int v[5] = {0, 1, 2, 3, 4};
    int *p;
    p = v;
    int resul = soma(0, p);
    printf("\nVetor: ");
    for (int i = 0; i < 5; i++)
    {
        printf("[%d]", v[i]);
    }
    printf("\nResultado da soma = %d\n", resul);
    printf("\n-------Fim do Exercicio 10-------\n");
    return 0;
}

int exercicio_11()
{
    printf("\n-------Exercicio 11 Selecionado-------\n");
    int v[5];
    int *p;
    p = v;
    for (int i = 0; i < 5; i++)
    {
        printf("Digite o valor %d:\n", i + 1);
        scanf("%d", &p[i]);
    }
    printf("\nVetor: ");
    for (int i = 0; i < 5; i++)
    {
        printf("[%d]", *p);
        p++;
    }
    printf("\n-------Fim do Exercicio 11-------\n");
    return 0;
}

struct aluno
{
    char nome[50];
    int idade;
    float media;
};

int exercicio_12()
{
    printf("\n-------Exercicio 12 Selecionado-------\n");
    struct aluno aluno1;
    struct aluno *p;
    p = &aluno1;
    sprintf(p->nome, "Juscelino");
    p->idade = 94;
    p->media = 8.9;
    printf("\n---Dados do Aluno---\n");
    printf("Nome: %s\n", p->nome);
    printf("Idade: %d\n", p->idade);
    printf("Media: %.2f\n", p->media);
    printf("\n-------Fim do Exercicio 12-------\n");
    return 0;
}

struct aluno13
{
    char nome[50];
    int idade;
    float nota;
};

int exercicio_13()
{
    printf("\n-------Exercicio 13 Selecionado-------\n");
    struct aluno13 aluno2;
    struct aluno13 *p;
    p = &aluno2;
    printf("Digite o nome do aluno: ");
    scanf(" %49[^\n]", p->nome);
    printf("Digite a idade do aluno: ");
    scanf("%d", &p->idade);
    printf("Digite a nota do aluno: ");
    scanf("%f", &p->nota);
    printf("\n---Dados do Aluno---\n");
    printf("Nome: %s\n", p->nome);
    printf("Idade: %d\n", p->idade);
    printf("Media: %.2f\n", p->nota);
    printf("\n-------Fim do Exercicio 13-------\n");
    return 0;
}

struct endereco
{
    char rua[50];
    int num;
    char cidade[50];
};

struct pessoa
{
    char nome[50];
    int idade;
    struct endereco endereco;
};

int exercicio_14()
{
    printf("\n-------Exercicio 14 Selecionado-------\n");
    struct pessoa pessoa1;
    struct pessoa *p;
    p = &pessoa1;
    sprintf(p->nome, "Messi");
    p->idade = 30;
    sprintf(p->endereco.rua, "rua 10");
    p->endereco.num = 123;
    sprintf(p->endereco.cidade, "Jatai");
    printf("\n---Dados da Pessoa---\n");
    printf("Nome: %s\n", p->nome);
    printf("Idade: %d\n", p->idade);
    printf("Rua: %s\n", p->endereco.rua);
    printf("Numero: %d\n", p->endereco.num);
    printf("Cidade: %s\n", p->endereco.cidade);
    printf("\n-------Fim do Exercicio 14-------\n");
    return 0;
}

void array(int *p, int tamanho)
{
    printf("Elementos do array:\n");
    for (int i = 0; i < tamanho; i++)
    {
        printf("%d", *(p + i));
    }
    printf("\n");
}

int exercicio_15()
{
    printf("\n-------Exercicio 15 Selecionado-------\n");
    int v[5] = {5, 6, 7, 8, 9};
    array(v, 5);
    printf("\n-------Fim do Exercicio 15-------\n");
    return 0;
}

int exercicio_16()
{
    printf("\n-------Exercicio 16 Selecionado-------\n");
    int a;
    int *b;
    int **c;
    int ***d;
    printf("Digite um valor para A: ");
    scanf("%d", &a);
    b = &a;
    c = &b;
    d = &c;
    printf("\nValor original: %d\n", a);
    printf("Dobro: %d\n", (**c) * 2);
    printf("Triplo: %d\n", (***d) * 3);
    printf("Quadruplo: %d\n", (*b) * 4);
    printf("\n-------Fim do Exercicio 16-------\n");
    return 0;
}

int negativos(float *vet, int n)
{
    int cont = 0;
    for (int i = 0; i < n; i++)
    {
        if (*(vet + i) < 0)
        {
            cont++;
        }
    }
    return cont;
}

int exercicio_17()
{
    printf("\n-------Exercicio 17 Selecionado-------\n");
    int n;
    printf("Digite o tamanho do vetor: ");
    scanf("%d", &n);
    float vetor[n];
    for (int i = 0; i < n; i++)
    {
        printf("Digite o valor %d: ", i + 1);
        scanf("%f", &vetor[i]);
    }
    int quant_negativo = negativos(vetor, n);
    printf("\nQuantidade de numeros negativos: %d\n", quant_negativo);
    printf("\n-------Fim do Exercicio 17-------\n");
    return 0;
}