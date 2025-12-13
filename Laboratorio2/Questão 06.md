# Questão 06

6 - Crie uma struct Autor com os campos nome e nacionalidade. Depois, crie uma struct Livro com
os campos título, ano de publicação e um campo do tipo Autor. Declare uma variável do tipo Livro,
preencha os dados e exiba as informações completas do livro, incluindo o nome e a nacionalidade do
autor.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct Autor
    {
        char nome[100], nacionali[100];
    };
    
    struct livro
    {
        int ano;
        char titulo[100];
        struct Autor autor;
    };

    struct livro l1;
    strcpy(l1.titulo, "Diario de um Banana");
    strcpy(l1.ano, "1999");
    strcpy(l1.autor.nome, "Jose");
    strcpy(l1.autor.nacionali, "Brasileiro");
    printf("Título: %s\n", l1.titulo);
    printf("Ano de publicação: %s\n", l1.ano);
    printf("Autor: %s\n", l1.autor.nome);
    printf("Nacionalidade: %s", l1.autor.nacionali);
    return 0;
}