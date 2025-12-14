# Lista de Exercícios

Essa lista é composta por 10 exercícios (sendo da questão 8 à questão 17), os quais serão listados logo abaixo.

Ela foi desenvolvida utilizando um menu interativo, no qual o usuário pode escolher qual exercício deseja executar, e o programa exibe o resultado correspondente à opção selecionada.

O código está dividido da seguinte forma:

-> exercicios.h: contém os protótipos das funções de cada exercício;

-> exercicios.c: onde as funções dos exercícios são implementadas;

-> main.c: responsável pelo menu e pelo controle da execução do programa.

---
8 -  Escreva um módulo em C que, usando variáveis locais, declare uma variável inteira e um ponteiro
para essa variável, e depois altere o valor da variável através do ponteiro.

9 - Escreva um módulo em C que, usando variáveis locais, declare uma string e um ponteiro para essa
variável. Usando ponteiro, altere a string para sua versão em letras maiúsculas.

10 - Escreva um módulo em C que, usando variáveis locais, que declare um vetor com 5 posições e um
ponteiro para essa variável. Usando ponteiro, retorne a soma de todos os elementos do vetor.

11 -  Escreva um módulo em C que, usando variáveis locais, declare um vetor de inteiros e um ponteiro
para esse vetor. Depois, peça para o usuário digitar os valores do vetor e use o ponteiro para imprimir
os valores na tela.

12 - Escreva um módulo em C que, usando variáveis locais, declare um ponteiro para uma estrutura que
represente um aluno (com nome, idade e média). Depois, crie uma variável desse tipo e use o ponteiro
para preencher os dados da estrutura. Em seguida, imprima os dados do aluno na tela.

13 - Crie uma estrutura "Aluno" com os campos nome, idade e nota. Em seguida, declare um ponteiro
para uma variável da estrutura tipo Aluno. Usando o ponteiro, preencha os campos da estrutura com
dados informados pelo usuário e imprima os dados do aluno na tela.

14 - Crie uma estrutura "Pessoa" com os campos nome, idade e endereço (com os campos rua, número
e cidade). Em seguida, declare um ponteiro para uma variável do tipo Pessoa e imprima os dados da
pessoa na tela.

15 - Crie uma função que receba como parâmetro um array e o imprima. Não utilize índices para
percorrer o array, apenas aritmética de ponteiros. 

16 - Considere a seguinte declaração: 

int A, *B, **C, ***D;

Escreva um programa que leia a variável a e calcule e exiba o dobro, o triplo e o quádruplo desse valor
utilizando apenas os ponteiros B, C e D. O ponteiro B deve ser usada para calcular o dobro, C o triplo e
D o quadruplo. 

17 -  Implemente uma função que receba como parâmetro um array de números reais de tamanho N e
retorne quantos números negativos há nesse array. Essa função deve obedecer ao protótipo:
int negativos(float *vet, int N);