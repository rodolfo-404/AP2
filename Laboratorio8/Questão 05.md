# Questão 05

5 - Faça um programa para alterar as notas dos alunos no arquivo criado no Exercício 3.

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
    struct alunos a[100];
    int n = 0;
    int op, matr, encontrado, matr_repete;
    FILE *f;
    f = fopen("ALUNOS.dat", "r");
    if (f != NULL)
    {
        while (fscanf(f, " --Aluno %*d--\n Nome: %[^\n]\n Curso: %[^\n]\n Matricula: %d\n Nota 1: % f\n Nota 2 : % f\n ", a[n].nome, a[n].curso, &a[n].matricula, &a[n].nota1, &a[n].nota2) == 5)
        {
            n++;
        }
        fclose(f);
        printf("%d alunos carregados do arquivo.\n", n);
    }
    else
    {
        printf("Nenhum arquivo existente encontrado. Comecando novo cadastro.\n");
    }
    do
    {
        printf("\n---MENU---\n");
        printf("1- Adicionar alunos\n");
        printf("2- Alterar notas dos alunos\n");
        printf("0- Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &op);
        getchar();
        switch (op)
        {
        case 1:
            printf("Quantos alunos deseja adicionar? ");
            int novos;
            scanf("%d", &novos);
            getchar();
            for (int i = 0; i < novos; i++)
            {
                printf("\n--Aluno %d--\n", n + 1);
                printf("Nome: ");
                fgets(a[n].nome, 50, stdin);
                a[n].nome[strcspn(a[n].nome, "\n")] = '\0';
                printf("Curso: ");
                fgets(a[n].curso, 50, stdin);
                a[n].curso[strcspn(a[n].curso, "\n")] = '\0';
                do
                {
                    matr_repete = 0;
                    printf("Matricula: ");
                    scanf("%d", &a[n].matricula);
                    getchar();
                    for (int j = 0; j < n; j++)
                    {
                        if (a[n].matricula == a[j].matricula)
                        {
                            printf("Erro: matricula ja cadastrada.\n");
                            matr_repete = 1;
                            break;
                        }
                    }
                } while (matr_repete);
                printf("Nota 1: ");
                scanf("%f", &a[n].nota1);
                printf("Nota 2: ");
                scanf("%f", &a[n].nota2);
                getchar();
                n++;
            }
            break;
        case 2:
            printf("Digite a matricula do aluno para alterar nota: ");
            scanf("%d", &matr);
            getchar();
            encontrado = 0;
            for (int i = 0; i < n; i++)
            {
                if (a[i].matricula == matr)
                {
                    printf("\nAluno encontrado: %s\n", a[i].nome);
                    printf("Digite a nova nota 1: ");
                    scanf("%f", &a[i].nota1);
                    printf("Digite a nova nota 2: ");
                    scanf("%f", &a[i].nota2);
                    encontrado = 1;
                    break;
                }
            }
            if (!encontrado)
                printf("Aluno nao encontrado.\n");
            break;
        case 0:
            printf("\nEncerrando e salvando...\n");
            break;
        default:
            printf("Opcao invalida.\n");
        }
    } while (op != 0);
    f = fopen("ALUNOS.dat", "w");
    if (f == NULL)
    {
        printf("Erro ao salvar arquivo.\n");
        exit(1);
    }
    for (int i = 0; i < n; i++)
    {
        fprintf(f, " --Aluno %d--\n", i + 1);
        fprintf(f, " Nome: %s\n", a[i].nome);
        fprintf(f, " Curso: %s\n", a[i].curso);
        fprintf(f, " Matricula: %d\n", a[i].matricula);
        fprintf(f, " Nota 1: %.2f\n", a[i].nota1);
        fprintf(f, " Nota 2: %.2f\n", a[i].nota2);
    }
    fclose(f);
    printf("Dados salvos em ALUNOS.dat com sucesso!\n");
    return 0;
}