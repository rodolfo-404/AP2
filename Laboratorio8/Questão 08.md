# Questão 08

8 - Faça um programa para consultar o número, o nome e a média de todos os alunos cadastrados no
arquivo do Exercício 3.

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
        printf("4 - Consultar todos os alunos\n");
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
                            printf("Erro: ja existe um aluno com essa matricula.\n");
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
            printf("Digite a matricula do aluno para alterar as notas: ");
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
                printf("Aluno com matricula %d nao encontrado.\n", matr);
            break;
        case 3:
            printf("Digite a matricula do aluno para alterar o curso: ");
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
                printf("Aluno com matricula %d nao encontrado.\n", matr);
            break;
        case 4:
            if (n == 0)
            {
                printf("\nNenhum aluno cadastrado.\n");
            }
            else
            {
                printf("\n---LISTA DE ALUNOS---\n");
                for (int i = 0; i < n; i++)
                {
                    float media = (a[i].nota1 + a[i].nota2) / 2.0;
                    printf("\nAluno %d\n", i + 1);
                    printf("Nome: %s\n", a[i].nome);
                    printf("Matricula: %d\n", a[i].matricula);
                    printf("Media: %.2f\n", media);
                }
            }
            break;
        case 0:
            printf("\nRemovendo alunos reprovados e salvando...\n");
            break;
        default:
            printf("Opcao invalida.\n");
        }
    } while (op != 0);
    struct alunos aprovados[200];
    int n_aprovados = 0;
    for (int i = 0; i < n; i++)
    {
        float media = (a[i].nota1 + a[i].nota2) / 2;
        if (media >= 6.0)
        {
            aprovados[n_aprovados] = a[i];
            n_aprovados++;
        }
        else
        {
            printf("Aluno %s reprovado (media %.2f), sera excluido.\n", a[i].nome,
                   media);
        }
    }
    f = fopen("ALUNOS.dat", "w");
    if (f == NULL)
    {
        printf("Erro ao abrir o arquivo.\n");
        exit(1);
    }
    for (int i = 0; i < n_aprovados; i++)
    {
        fprintf(f, " --Aluno %d--\n", i + 1);
        fprintf(f, " Nome: %s\n", aprovados[i].nome);
        fprintf(f, " Curso: %s\n", aprovados[i].curso);
        fprintf(f, " Matricula: %d\n", aprovados[i].matricula);
        fprintf(f, " Nota 1: %.2f\n", aprovados[i].nota1);
        fprintf(f, " Nota 2: %.2f\n", aprovados[i].nota2);
    }
    fclose(f);
    printf("\nDados salvos com sucesso! Total de aprovados: %d\n", n_aprovados);
    return 0;
}