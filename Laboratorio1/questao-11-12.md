# Questões 11 e 12

### 11 - 
Declarar o registro Ficha de Cliente que tem a seguinte forma:

Ficha de Cliente

Nome: | Endereço: | E-mail:

Idade: | CPF: | Sexo:

Data de nascimento: | Altura: | Peso:

IMC:

---
### 12 -
Usando a estrutura definida no exercício anterior, faça:

-> Declarar uma variável do tipo Ficha de Cliente;

-> Ler os campos da ficha;

-> Escrever os campos da ficha;

-> Ler uma variável denominada id. Depois comparar a variável id ao campo do registro nome;

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>
int intervalo(int valor, int min, int maxi)
{
    return valor < min || valor > maxi;
}
int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct ficha_cliente
    {
        int numero, idade, dia, mes, ano;
        float altura, peso, imc;
        char nome[100], bairro[100], rua[100], email[40], sexo[15], cpf[12];
        char id[100];
    };
    struct ficha_cliente cliente;
    printf("\n-------------------Ficha de Cliente-------------------\n\n");
    printf("Nome: ");
    fgets(cliente.nome, 100, stdin);
    cliente.nome[strcspn(cliente.nome, "\n")] = '\0';
    printf("\n---Endereço---\n");
    printf("Bairro: ");
    fgets(cliente.bairro, 100, stdin);
    printf("Rua: ");
    fgets(cliente.rua, 100, stdin);
    printf("Número: ");
    scanf("%d", &cliente.numero);
    getchar();
    printf("Email: ");
    fgets(cliente.email, 40, stdin);
    printf("Idade: ");
    scanf("%d", &cliente.idade);
    getchar();
    printf("CPF: ");
    scanf("%11s", cliente.cpf);
    getchar();
    printf("Sexo: ");
    fgets(cliente.sexo, 15, stdin);
    printf("Data de Nascimento\n");
    printf("Dia: ");
    scanf("%d", &cliente.dia);
    getchar();
    printf("Mês: ");
    scanf("%d", &cliente.mes);
    getchar();
    printf("Ano: ");
    scanf("%d", &cliente.ano);
    getchar();
    printf("Altura: ");
    scanf("%f", &cliente.altura);
    getchar();
    printf("Peso: ");
    scanf("%f", &cliente.peso);
    getchar();
    cliente.imc = cliente.peso / (cliente.altura * cliente.altura);
    if (intervalo(cliente.mes, 1, 12))
    {
        printf("\nERRO! Data inválida.\n");
    }
    else
    {
        printf("\n-------------------Ficha de Cliente-------------------\n\n");
        printf("\nNome: %s\n", cliente.nome);
        printf("Endereço: \n");
        printf("Bairro %s", cliente.bairro);
        printf("Rua %s", cliente.rua);
        printf("Número %d\n", cliente.numero);
        printf("Email: %s\n", cliente.email);
        printf("Idade: %d\n", cliente.idade);
        printf("CPF: %s\n", cliente.cpf);
        printf("Sexo: %s\n", cliente.sexo);
        printf("Data de Nascimento: %02d/%02d/%02d\n", cliente.dia, cliente.mes,
               cliente.ano);
        printf("Altura: %.2fm\n", cliente.altura);
        printf("Peso: %.2fkg\n", cliente.peso);
        printf("IMC (Índice de Massa Corporal): %.2f\n", cliente.imc);
        printf("\n\nDigite um nome para verificar: ");
        fgets(cliente.id, 100, stdin);
        cliente.id[strcspn(cliente.id, "\n")] = '\0';
        if (strcmp(cliente.nome, cliente.id) == 0)
        {
            printf("\nO nome é igual ao registrado\n");
        }
        else
        {
            printf("\nO nome é diferente do registrado\n");
        }
    }
    return 0;
}