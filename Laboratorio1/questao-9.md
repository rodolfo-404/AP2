# Questão 9

Faça um programa que: Preencha os campos da struct do exercício anterior e Imprima os campos da struct do exercício anterior.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct ficha_companhia
    {
        char nome_companhia[80];
        char area_atuacao[80];
        float valoratual, valoranterior;
        double variacao;
    };
    struct ficha_companhia companhia;
    printf("\n-----------------Bolsa de Valores-----------------\n\n");
    printf("Nome da Companhia: ");
    fgets(companhia.nome_companhia, 80, stdin);
    printf("Área de Atuação da Companhia: ");
    fgets(companhia.area_atuacao, 80, stdin);
    printf("Valor atual da ação (em reais): ");
    scanf("%f", &companhia.valoratual);
    printf("Valor anterior: ");
    scanf("%f", &companhia.valoranterior);
    companhia.variacao = ((companhia.valoratual - companhia.valoranterior) /
                          companhia.valoranterior) *
                         100;
    printf("\n----Resumo da Ação----\n");
    printf("Nome: %s\n", companhia.nome_companhia);
    printf("Àrea de Atuação: %s\n", companhia.area_atuacao);
    printf("Valor anterior: R$ %.2f\n", companhia.valoranterior);
    printf("Valor atual: R$ %.2f\n", companhia.valoratual);
    printf("Variação: %.2f%%\n\n", companhia.variacao);
    return 0;
}