# Questão 01

1 -  Criar um menu iterativo para selecionar os exercícios da lista. Usando o módulo void Exercicio
(int questao), invoque o exercício que deverá estar salvo numa biblioteca *.h.

---
### exercicio.h
```c
#ifndef EXERCICIO_H
#define EXERCICIO_H

void exercicio (int questao);

#endif
```
### exercicio.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "exercicio.h"

void exercicio(int questao)
{
    switch (questao)
    {
    case 1:
        printf("Você escolheu o exercício 1\n");
        break;
    case 2:
        printf("Você escolheu o exercício 2\n");
        break;
    case 3:
        printf("Você escolheu o exercício 3\n");
        break;
    case 4:
        printf("Você escolheu o exercício 4\n");
        break;
    case 5:
        printf("Você escolheu o exercício 5\n");
        break;
    case 6:
        printf("Você escolheu o exercício 6\n");
        break;
    case 7:
        printf("Você escolheu o exercício 7\n");
        break;
    case 8:
        printf("Você escolheu o exercício 8\n");
        break;
    default:
        printf("Valor inválido\n");
        break;
    }
}
```
### main.c 
```c
#include <stdio.h>
#include <stdlib.h>
#include "exercicio.h"

int main()
{
    int questao;
    printf("Escolha um exercício da lista (1 a 8)\n");
    scanf("%d", &questao);
    exercicio(questao);
    return 0;
}