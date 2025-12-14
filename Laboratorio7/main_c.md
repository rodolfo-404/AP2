# main.c

Responsável pelo menu e pelo controle da execução do programa.

---
```c
#include <stdio.h>
#include <stdlib.h>
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
        printf("8- Exercicio 8\n");
        printf("9- Exercicio 9\n");
        printf("10- Exercicio 10\n");
        printf("11- Exercicio 11\n");
        printf("12- Exercicio 12\n");
        printf("13- Exercicio 13\n");
        printf("14- Exercicio 14\n");
        printf("15- Exercicio 15\n");
        printf("16- Exercicio 16\n");
        printf("17- Exercicio 17\n");
        printf("0- Sair\n");
        printf("-------------------------------------\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);
        switch (opcao)
        {
        case 8:
            exercicio_8();
            break;
        case 9:
            exercicio_9();
            break;
        case 10:
            exercicio_10();
            break;
        case 11:
            exercicio_11();
            break;
        case 12:
            exercicio_12();
            break;
        case 13:
            exercicio_13();
            break;
        case 14:
            exercicio_14();
            break;
        case 15:
            exercicio_15();
            break;
        case 16:
            exercicio_16();
            break;
        case 17:
            exercicio_17();
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