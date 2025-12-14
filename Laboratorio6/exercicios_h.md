# exercicios.h

Contém os protótipos das funções de cada exercício.

---
```c
#ifndef EXERCICIOS_H
#define EXERCICIOS_H

int exercicio_1();
int troca(int *a, int *b);
int funcao(int *a, int *b);

int exercicio_2();
int ehvogal(char letra);
void contarvogal(char frase[], char vogal, int *v);

int exercicio_3();
typedef struct
{
char nome [50];
char sexo [15];
int idade;
int numfilhos;
float salario;
}habitante;
void altera(habitante *x);
void exibe(habitante *x);

int exercicio_4();
void min_multiplica(int vetor[], int *xmin, int n);

int exercicio_5();
void crescente(int *a, int *b, int *c);

int exercicio_6();
float soma(float *v, int tamanho);
float media(float *soma, int tamanho);
float desvio(float *v, float media, int tamanho);
void substitui(float *v, int tamanho);

#endif