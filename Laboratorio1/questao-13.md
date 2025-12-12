# Questão 13

Crie uma estrutura representando os alunos de um determinado curso. A estrutura deve conter
a matrícula do aluno, nome, nota da primeira prova, nota da 
segunda prova e nota da terceira prova.

- Declare duas variáveis x e y.
- Faça a leitura dos campos das variáveis x e y.
- Encontre o aluno com maior nota da primeira prova.
- Encontre o aluno com maior média geral.
- Encontre o aluno com menor média geral.
- Para cada aluno diga se ele foi aprovado ou reprovado, considerando o valor 6 para aprovação.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>
int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct aluno
    {
        int matricula;
        float n1, n2, n3;
        char nome[100];
    };
    struct aluno x, y;
    float media_x, media_y;
    printf("Digite a matrícula do primeiro aluno: ");
    scanf("%d", &x.matricula);
    getchar();
    printf("Digite o nome do aluno: ");
    fgets(x.nome, sizeof(x.nome), stdin);
    printf("Digite a nota 1: ");
    scanf("%f", &x.n1);
    printf("Digite a nota 2: ");
    scanf("%f", &x.n2);
    printf("Digite a nota 3: ");
    scanf("%f", &x.n3);
    printf("Digite a matrícula do segundo aluno: ");
    scanf("%d", &y.matricula);
    getchar();
    printf("Digite o nome do aluno: ");
    fgets(y.nome, sizeof(y.nome), stdin);
    printf("Digite a nota 1: ");
    scanf("%f", &y.n1);
    printf("Digite a nota 2: ");
    scanf("%f", &y.n2);
    printf("Digite a nota 3: ");
    scanf("%f", &y.n3);
    media_x = (x.n1 + x.n2 + x.n3) / 3.0;
    media_y = (y.n1 + y.n2 + y.n3) / 3.0;
    if (x.n1 > y.n1)
    {
        printf("\nMaior nota da primeira prova: %s (%.2f)\n\n", x.nome, x.n1);
    }
    else if (y.n1 > x.n1)
    {
        printf("\nMaior nota da primeira prova: %s (%.2f)\n\n", y.nome, y.n1);
    }
    else
    {
        printf("\nEmpate na nota da primeira prova (%.2f)\n\n", y.n1);
    }
    if (media_x > media_y)
    {
        printf("\nMaior média geral: %s (%.2f)\n\n", x.nome, media_x);
        printf("\nMenor média geral: %s (%.2f)\n\n", y.nome, media_y);
    }
    else if (media_y > media_x)
    {
        printf("\nMaior média geral: %s (%.2f)\n\n", y.nome, media_y);
        printf("\nMenor média geral: %s (%.2f)\n\n", x.nome, media_x);
    }
    else
    {
        printf("\nEmpate na média geral (%.2f)\n\n", media_x);
    }
    if (media_x >= 6)
    {
        printf("\nAluno %s aprovado com média %.2f\n\n", x.nome, media_x);
    }
    else
    {
        printf("\nAluno %s reprovado com média %.2f\n\n", x.nome, media_x);
    }
    if (media_y >= 6)
    {
        printf("\nAluno %s aprovado com média %.2f\n\n", y.nome, media_y);
    }
    else
    {
        printf("\nAluno %s reprovado com média %.2f\n\n", y.nome, media_y);
    }
    return 0;
}