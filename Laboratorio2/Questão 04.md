# Questão 04

4 ? Crie uma struct para um Produto com os campos código (inteiro), nome (string) e preço (real).
Declare um vetor para 3 produtos e, utilizando um for, permita que o usuário cadastre as informações
de todos eles. Ao final, exiba a lista completa de produtos.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct produto
    {
        char nome[100];
        int codigo;
        float preco;
    } produtos[3];
    for (int i = 0; i < 3; i++)
    {
        printf("Nome do Produto: ");
        fgets(produtos[i].nome, 100, stdin);
        produtos[i].nome[strcspn(produtos[i].nome, "\n")] = ?\0?;
        printf("Código do Produto: ");
        scanf("%d", &produtos[i].codigo);
        printf("Preço do Produto: ");
        scanf("%f", &produtos[i].preco);
        getchar();
        printf("\n");
    }
    printf("\n--------Dados dos Produtos--------\n");
    for (int i = 0; i < 3; i++)
    {
        printf("\nProduto: %s\n", produtos[i].nome);
        printf("Código: %d\n", produtos[i].codigo);
        printf("Preço: R$ %.2f\n", produtos[i].preco);
    }
    return 0;
}