# Questão 06

6 - Faça um programa para alterar o curso dos alunos do arquivo criado no Exercício 3.

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
    struct alunos a[200];
    int n = 0;
    int op, matr;
    int encontrado, matr_repete;
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
        printf("Nenhum arquivo encontrado. Criando novo cadastro.\n");
    }
    do
    {
        printf("\n---MENU---\n");
        printf("1 - Adicionar alunos\n");
        printf("2 - Alterar notas de um aluno\n");
        printf("3 - Alterar curso de um aluno\n");
        printf("0 - Sair e salvar\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &op);
        getchar();
        switch (op)
        {
        case 1:
        {
            int novos;
            printf("Quantos alunos deseja adicionar? ");
            scanf("%d", &novos);
            getchar();
            for (int i = 0; i < novos; i++)
            {
                printf("\n--Novo aluno %d--\n", n + 1);
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
                            printf("Erro: já existe um aluno com essa matrícula.\n");
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
        }
        case 2:
            printf("Digite a matrícula do aluno para alterar as notas: ");
            scanf("%d", &matr);
            getchar();
            encontrado = 0;
            for (int i = 0; i < n; i++)
            {
                if (a[i].matricula == matr)
                {
                    printf("\nAluno encontrado: %s\n", a[i].nome);
                    printf("Nota 1 atual: %.2f\n", a[i].nota1);
                    printf("Nota 2 atual: %.2f\n", a[i].nota2);
                    printf("Digite a nova Nota 1: ");
                    scanf("%f", &a[i].nota1);
                    printf("Digite a nova Nota 2: ");
                    scanf("%f", &a[i].nota2);
                    getchar();
                    encontrado = 1;
                    printf("Notas alteradas com sucesso!\n");
                    break;
                }
            }
            if (!encontrado)
                printf("Aluno com matrícula %d não encontrado.\n", matr);
            break;
        case 3:
            printf("Digite a matrícula do aluno para alterar o curso: ");
            scanf("%d", &matr);
            getchar();
            encontrado = 0;
            for (int i = 0; i < n; i++)
            {
                if (a[i].matricula == matr)
                {
                    printf("\nAluno encontrado: %s\n", a[i].nome);
                    printf("Curso atual: %s\n", a[i].curso);
                    printf("Digite o novo curso: ");
                    fgets(a[i].curso, 50, stdin);
                    a[i].curso[strcspn(a[i].curso, "\n")] = '\0';
                    encontrado = 1;
                    printf("Curso alterado com sucesso!\n");
                    break;
                }
            }
            if (!encontrado)
                printf("Aluno com matrícula %d não encontrado.\n", matr);
            break;
        case 0:
            printf("\nSalvando e encerrando...\n");
            break;
        default:
            printf("Opcao invalida.\n");
        }
    } while (op != 0);
    f = fopen("ALUNOS.dat", "w");
    if (f == NULL)
    {
        printf("Erro ao abrir o arquivo.\n");
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
    printf("Dados salvos com sucesso em ALUNOS.dat!\n");
    return 0;
}