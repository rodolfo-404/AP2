# Questão 08

8 - Crie as structs Autor e Livro dos exercícios anteriores. Declare um vetor de 5 Livros. Permita que
o usuário cadastre as informações de cada livro (título, ano e dados do autor). Ao final, imprima o
catálogo completo.

---

```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

struct Autor
{
    char nome[200], nacionali[100];
};

struct Livro
{
    int ano;
    char titulo[200];
    struct Autor autor;
};

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct Livro livros[5];
    for (int i = 0; i < 5; i++)
    {
        printf("\nTítulo: \n");
        fgets(livros[i].titulo, 200, stdin);
        livros[i].titulo[strcspn(livros[i].titulo, "\n")] = '\0';
        printf("\nAno de publicação: \n");
        scanf("%d", &livros[i].ano);
        getchar();
        printf("\nAutor: \n");
        fgets(livros[i].autor.nome, 200, stdin);
        livros[i].autor.nome[strcspn(livros[i].autor.nome, "\n")] = '\0';
        printf("\nNacionalidade: \n");
        fgets(livros[i].autor.nacionali, 100, stdin);
        livros[i].autor.nacionali[strcspn(livros[i].autor.nacionali, "\n")] = '\0';
    }
    printf("\n---------------------Catálogo Completo---------------------");
    for (int i = 0; i < 5; i++)
    {
        printf("\nDados do Livro\n");
        printf("Título: %s\n", livros[i].titulo);
        printf("Ano de Publicação: %d\n", livros[i].ano);
        printf("Autor: %s\n", livros[i].autor.nome);
        printf("Nacionalidade: %s\n", livros[i].autor.nacionali);
        printf("\n");
    }
    return 0;
}