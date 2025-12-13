# Questão 08

8 - Crie uma variável global float g_vetor[5]. Em seguida, crie a função float calcula_media_aritmetica( ), que calcule a média aritmética dos elementos do vetor. A função main( ) deverá ler os
elementos de g_vetor, chamar a função calcula_media_aritmetica e imprimir o resultado.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

float g_vetor[5];
float calcula_media_aritmetica()

{
float soma = 0.0;
for (int i = 0; i < 5; i++)
{
soma += g_vetor[i];
}
return soma/5;
}

int main()
{
setlocale(LC_ALL, "Portuguese");
printf("\nDigite 5 valores\n");
for (int i = 0; i < 5; i++)
{
printf("Valor %d: ", i + 1);
scanf("%f", &g_vetor[i]);
}
float media = calcula_media_aritmetica();

printf("\nResultado da Média Aritmética dos Valores: %.2f", media);
return 0;
}