# main.c

Responsável pelo menu e pelo controle da execução do programa.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
#include <string.h>
#include <ctype.h>
#include "exercicios.h"

int main()
{
    int opcao;
    do
    {
        printf("\n-----MENU DE EXERCICIOS-----\n");
        printf("-------------------------------------\n");
        printf("1- Exercicio 1\n");
        printf("2- Exercicio 2\n");
        printf("3- Exercicio 3\n");
        printf("4- Exercicio 4\n");
        printf("5- Exercicio 5\n");
        printf("6- Exercicio 6\n");
        printf("0- Sair\n");
        printf("-------------------------------------\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);
        switch (opcao)
        {
        case 1:
            exercicio_1();
            break;
        case 2:
            exercicio_2();
            break;
        case 3:
            exercicio_3();
            break;
        case 4:
            exercicio_4();
            break;
        case 5:
            exercicio_5();
            break;
        case 6:
            exercicio_6();
            break;
        case 0:
            printf("Encerrando\n");
            break;
        default:
            printf("Opcao invalida\n");
        }
    } while (opcao != 0);
    return 0;
}