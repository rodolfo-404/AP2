# Questão 07

7 - Crie uma função int calcula_fatorial( ). A função principal deverá ler o valor g_N, chama a
função para calcular o Fatorial de g_N. Ao final, calcula_fatorial( ) retorna o valor da soma para a
função main( ), para imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int g_N;
int calcula_fatorial(int n)
{
    int fat = 1;
    for (int i = 1; i <= n; i++)
    {
        fat *= i;
    }
    return fat;
}

int main()
{
    setlocale(LC_ALL, "Portuguese");
    printf("\nDigite o número que será calculado o Fatorial: ");
    scanf("%d", &g_N);
    printf("Fatorial de %d = %d\n", g_N, calcula_fatorial(g_N));
    return 0;
}