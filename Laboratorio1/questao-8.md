# Questão 8

Crie uma struct para controlar ações de uma bolsa de valores com as seguintes informações:

Nome da companhia; Área de atuação da companhia; Valor atual da ação (em reais); Valor anterior; Variação da ação em porcentagem (double), ou seja, quanto a ação cresceu ou caiu desde a abertura da bolsa no dia. 

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
    return 0;
}