# Questão 06

6 - Crie uma função int calcula_fibonacci( ). A função principal deverá ler o valor g_N, chama a
função para calcular o Fibonacci de g_N. Ao final, calcula_fibonacci( ) retorna o valor da soma para
a função main( ), para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int g_N;
int calcula_fibonacci(int n)
{
    if (n == 0)
    {
        return 0;
    }
    if (n == 1)
    {
        return 1;
    }
    return calcula_fibonacci(n - 1) + calcula_fibonacci(n - 2);
}

int main()
{
    setlocale(LC_ALL, "Portuguese");
    printf("\nDigite o número de termos da Sequência Fibonacci: ");
    scanf("%d", &g_N);
    for (int i = 0; i < g_N; i++)
    {
        printf("%d\n", calcula_fibonacci(i));
    }
    return 0;
}