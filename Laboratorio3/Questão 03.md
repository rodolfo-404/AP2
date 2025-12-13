# Questão 03

3 - Crie uma função int verifica_positivo_negativo( ), que leia o valor global e verifique ser é positivo (retorna 1) ou não (retorna 0). Ao final, retorna o valor da verificação para a função main( ),
para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int n;
int verifica()
{
    if (n > 0)
    {
        return 1;
    }
    else if (n == 0)
    {
        return 0;
    }
    else
    {
        return 2;
    }
}

int main()
{
    setlocale(LC_ALL, "Portuguese");
    printf("\nDigite um número inteiro: ");
    scanf("%d", &n);
    int result = verifica();
    if (result == 1)
    {
        printf("O número %d é Positivo \n", n);
    }
    else if (result == 0)
    {
        printf("Número %d (Zero) \n", n);
    }
    else if (result == 2)
    {
        printf("O número %d é Negativo \n", n);
    }
    return 0;
}