# Questão 10

10 - Crie uma struct Motor com os campos cilindrada e potência. Em seguida, crie uma struct Carro
com os campos marca, modelo e um campo do tipo Motor. Declare um vetor de 4 Carros. Permita o
cadastro de todos os carros e, ao final, imprima a lista completa de veículos, incluindo a marca,
modelo e as informações do motor.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

struct Motor
{
    int cilindrada;
    int potencia;
};

struct Carro
{
    char marca[100];
    char modelo[100];
    struct Motor motor;
};

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct Carro carros[4];
    for (int i = 0; i < 4; i++)
    {
        printf("\n---Cadastro do Carro %d---\n\n", i + 1);
        printf("Marca: ");
        fgets(carros[i].marca, 100, stdin);
        carros[i].marca[strcspn(carros[i].marca, "\n")] = '\0';
        printf("\nModelo: ");
        fgets(carros[i].modelo, 100, stdin);
        carros[i].modelo[strcspn(carros[i].modelo, "\n")] = '\0';
        printf("\nCilindrada (cm^3) : ");
        scanf("%d", &carros[i].motor.cilindrada);
        printf("\nPotência (HP): ");
        scanf("%d", &carros[i].motor.potencia);
        getchar();
    }
    printf("\n------Lista de Carros------\n");
    for (int i = 0; i < 4; i++)
    {
        printf("\nCarro %d\n", i + 1);
        printf("Marca: %s\n", carros[i].marca);
        printf("Modelo: %s\n", carros[i].modelo);
        printf("Motor: %d cm^3, %d HP\n", carros[i].motor.cilindrada,
               carros[i].motor.potencia);
    }
    return 0;
}