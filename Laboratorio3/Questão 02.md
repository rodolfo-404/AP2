# Questão 02

2 - Crie uma função int verifica_par_impar( ), que leia o valor global e verifique se é par ou ímpar.
Ao final, retorna o valor da verificação para a função main( ), para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int n;
int par_impar()
{
    if (n % 2 == 0)
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
    printf("Digite um número inteiro: ");
    scanf("%d", &n);
    int result = par_impar();
    if (result == 1)
    {
        printf("O número %d é Par\n", n);
    }
    else
    {
        printf("O número %d é Ímpar\n", n);
    }
    return 0;
}