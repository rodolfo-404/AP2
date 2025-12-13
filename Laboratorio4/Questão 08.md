# Questão 08

8 -  (Elabore um arquivo com extensão .h e .c) Uma locadora de bicicletas cobra uma taxa mínima de
R$5,00 para até duas horas de uso. Após esse período, é cobrado um adicional de R$2,00 por hora ou
fração excedente. O valor máximo a ser pago em um mesmo dia é de R$30,00.
Admita que nenhum cliente fique com a bicicleta por mais de 24 horas. Escreva um programa em C que:

1. Leia o tempo de uso (em horas) de três clientes que alugaram bicicletas ontem.
2. Use uma função calculaTaxa(int horas) que receba o tempo de uso e retorne o valor a ser cobrado.
3. Imprima os resultados em formato de tabela, mostrando:
o Cliente
o Horas usadas
o Valor a pagar
4. Calcule e exiba também o total recebido pela locadora no dia de ontem.

---

### locadora.h
```c
#ifndef LOCADORA_H
#define LOCADORA_H

float calculaTaxa(int horas);

#endif
```
### locadora.c 
```c
#include <stdio.h>
#include "locadora.h"

float calculaTaxa(int horas)
{
    float valor = 5.0;
    if (horas > 2)
    {
        valor += (horas - 2) * 2.0;
    }
    if (valor > 30.0)
    {
        valor = 30.0;
    }
    return valor;
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "locadora.h"

int main()
{
    int horas[3];
    float valores[3];
    float total = 0;
    printf("\nDigite o tempo de uso (em horas) de 3 clientes:\n");
    for (int i = 0; i < 3; i++)
    {
        printf("\nCliente %d: ", i + 1);
        scanf("%d", &horas[i]);
        valores[i] = calculaTaxa(horas[i]);
        total += valores[i];
    }
    printf("\n===================================================\n");
    printf("Cliente\tHoras utilizadas\tValor (R$)\n");
    for (int i = 0; i < 3; i++)
    {
        printf("%d\t%d\t\t\t%.2f\n", i + 1, horas[i], valores[i]);
    }
    printf("---------------------------------------------------\n");
    printf("Total\t\t\t\t%.2f\n", total);
    printf("===================================================\n");
    return 0;
}