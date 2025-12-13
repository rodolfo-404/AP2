# Questão 05

5 -  Crie uma função int verifica_ano_bissexto( ), que leia a variável global e verifique ser é um ano
bissexto (retorna 1) ou não (retorna 0). Ao final, retorna o valor da verificação para a função main( ),
para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int ano;
int verifica_ano_bissexto()
{
    if ((ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0))
    {
        return 1;
    }
    else
    {
        return 0;
    }
}

int main()
{
    setlocale(LC_ALL, "Portuguese");
    printf("\nDigite um ano: ");
    scanf("%d", &ano);
    int result = verifica_ano_bissexto();
    if (result == 1)
    {
        printf("O ano %d é um ano bissexto. \n", ano);
    }
    else if (result == 0)
    {
        printf("O ano %d não é um ano bissexto. \n", ano);
    }
    return 0;
}