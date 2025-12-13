# Questão 09

9 - Crie uma struct Telefone com os campos ddd e número. Em seguida, crie uma struct Contato com
os campos nome, e-mail e um vetor de 2 Telefones. Declare um vetor de 3 Contatos. Permita que o
usuário preencha os dados de todos eles e, no final, exiba a agenda completa, incluindo os dois
telefones de cada contato.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

struct Telefone
{
    int ddd, numero;
};

struct Contato
{
    char nome[200], email[200];
    struct Telefone numero[2];
};

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct Contato contatos[3];
    for (int i = 0; i < 3; i++)
    {
        printf("\nNome: \n");
        fgets(contatos[i].nome, 200, stdin);
        contatos[i].nome[strcspn(contatos[i].nome, "\n")] = '\0';
        for (int j = 0; j < 2; j++)
        {
            printf("\nDDD: \n");
            scanf("%d", &contatos[i].numero[j].ddd);
            getchar();
            printf("\nNúmero: \n");
            scanf("%d", &contatos[i].numero[j].numero);
            getchar();
        }
        printf("\nEmail: \n");
        fgets(contatos[i].email, 200, stdin);
        contatos[i].email[strcspn(contatos[i].email, "\n")] = '\0';
    }
    printf("\n---------------------Agenda---------------------");
    for (int i = 0; i < 3; i++)
    {
        printf("\nDados do Contato\n");
        printf("\nNome: %s\n", contatos[i].nome);
        for (int j = 0; j < 2; j++)
        {
            printf("Telefone %d: (%d) %d\n", j + 1, contatos[i].numero[j].ddd,
                   contatos[i].numero[j].numero);
        }
        printf("Email: %s\n", contatos[i].email);
        printf("\n");
    }
    return 0;
}