# Lista de Exercícios

Essa lista é composta por 06 exercícios, os quais serão listados logo abaixo.

Ela foi desenvolvida utilizando um menu interativo, no qual o usuário pode escolher qual exercício deseja executar, e o programa exibe o resultado correspondente à opção selecionada.

O código está dividido da seguinte forma:

-> exercicios.h: contém os protótipos das funções de cada exercício;

-> exercicios.c: onde as funções dos exercícios são implementadas;

-> main.c: responsável pelo menu e pelo controle da execução do programa.

---
Exercícios: 

1 - Crie um programa para testar as funções a seguir: Uma função que receba dois números a e b, em seguida, faça a troca destes dois números. A e b devem ser passados por referência. Uma função que receba dois números a e b, em seguida, decremente o primeiro e incremente o segundo. A e b devem ser passados por referência.

2 - Faça um programa que receba uma frase no módulo principal. Elabore um módulo que receba a frase
e uma determinada vogal, ao final, mostre a quantidade de vezes que a vogal apareceu na frase. Fazer
tratamento de erro para evitar que leia consoante.

3 - Foi realizada uma pesquisa com os habitantes de bairro. Crie um programa que define a estrutura
habitante com os dados: nome, idade, sexo, salário e número de filhos. Usando o módulo altera (*
habitante x) altere os dados e do módulo exibe ( * habitante x), para exibir os membros da struct.

4 - Crie uma sub-rotina que receba como parâmetros um vetor, *xmin e a quantidade de elementos do
vetor (use o comando sizeof( ) dentro do módulo principal). A rotina deverá calcular o menor elemento
do vetor e também deverá fazer a multiplicação de cada elemento com o menor elemento do vetor.

5 - Crie uma sub-rotina que receba como parâmetros por referência três valores inteiros. A sub-rotina
deverá ordenar de forma crescente os valores.

6 - Construa um programa que leia um vetor de números reais e que possui 5 posições. O programa
principal fará as seguintes chamadas de funções:

a) int soma(float *v, int tamanho) - Retorna o somatório dos valores do vetor;

b) float media(int *soma, int tamanho) - Retorna a média dos valores do vetor;

c) float desvio(float *v, float media, int tamanho) - Calcule o desvio-padrão;

d) float substitui(float*v, int tamanho) - Substitui por zero os valores negativos.