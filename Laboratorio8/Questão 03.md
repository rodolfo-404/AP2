# Questão 03

3 - Faça um programa para criar um arquivo chamado ALUNOS.DAT, no qual cada registro será
composto pelos seguintes campos: matrícula, nome, curso, nota1 e nota2.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct alunos
{
    char nome[50];
    char curso[50];
    int matricula;
    float nota1;
    float nota2;
};
int main()
{
    struct alunos a[2];
    for (int i = 0; i < 2; i++)
    {
        printf("Nome: ");
        fgets(a[i].nome, 50, stdin);
        a[i].nome[strcspn(a[i].nome, "\n")] = '\0';
        printf("Curso: ");
        fgets(a[i].curso, 50, stdin);
        a[i].curso[strcspn(a[i].curso, "\n")] = '\0';
        printf("Matricula: ");
        scanf("%d", &a[i].matricula);
        printf("Nota 1: ");
        scanf("%f", &a[i].nota1);
        printf("Nota 2: ");
        scanf("%f", &a[i].nota2);
        getchar();
    }
    FILE *f;
    f = fopen("ALUNOS.dat", "w");
    if (f == NULL)
    {
        printf("Erro ao abrir o arquivo\n");
        system("pause");
        exit(1);
    }
    fprintf(f, "\n---Dados---\n");
    for (int i = 0; i < 2; i++)
    {
        fprintf(f, "Nome: %s\n", a[i].nome);
        fprintf(f, "Curso: %s\n", a[i].curso);
        fprintf(f, "Matricula: %d\n", a[i].matricula);
        fprintf(f, "Nota 1: %.2f\n", a[i].nota1);
        fprintf(f, "Nota 2: %.2f~\n", a[i].nota2);
    }
    fclose(f);
    system("pause");
    return 0;
}