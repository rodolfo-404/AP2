# Questões 01, 02 e 03

1 - Crie uma struct para representar um Aluno com os campos nome, idade e nota (tipo real). Em
seguida, declare um vetor de 5 alunos. Preencha os dados de forma automática para cada aluno e, por
fim, imprima os dados de todos eles.

2-  Utilizando a struct do exercício anterior, crie um programa que permita ao usuário cadastrar 3
alunos. Após o cadastro, o programa deve calcular e exibir a média das notas da turma.

3 ? Adapte o exercício 2 para que, depois de cadastrar os 3 alunos, o programa encontre e exiba o
nome do aluno que obteve a maior nota.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct aluno
    {
        char nome[50];
        int idade;
        float nota;
    } alunos[3];
    float soma = 0, turma, maior = 0;
    int i_maior = 0;
    for (int i = 0; i < 3; i++)
    {
        printf("Nome do Aluno: ");
        scanf("%s", alunos[i].nome);
        printf("Idade do Aluno: ");
        scanf("%d", &alunos[i].idade);
        printf("Nota do aluno: ");
        scanf("%f", &alunos[i].nota);
        printf("\n");
        soma += alunos[i].nota;
        if (alunos[i].nota >= maior)
        {
            maior = alunos[i].nota;
            i_maior = i;
        }
    }
    turma = soma / 3;
    printf("\n--------Dados dos Alunos--------\n\n");
    for (int i = 0; i < 3; i++)
    {
        printf("\nAluno: %s\n", alunos[i].nome);
        printf("Idade: %d\n", alunos[i].idade);
        printf("Nota do Aluno: %.2f\n", alunos[i].nota);
    }
    printf("\nMédia da Turma: %.2f\n", turma);
    printf("\nAluno com Maior Média: %s\n", alunos[i_maior].nome);
    printf("Média: %.2f\n", maior);
    return 0;
}