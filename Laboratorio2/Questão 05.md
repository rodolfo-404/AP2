# Questão 05

5 - Crie uma struct chamada Endereço com os campos rua, número e cidade. Em seguida, crie outra
struct chamada Pessoa que contenha os campos nome e uma variável do tipo Endereço. Declare uma
variável do tipo Pessoa, preencha os dados e imprima o nome da pessoa e o endereço completo.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct enderecos
    {
        char rua[100], cidade[100];
        int n;
    };
    struct pessoas
    {
        char nome[100];
        struct enderecos endereco;
    };
    struct pessoas p1;
    strcpy(p1.nome, "Maria");
    strcpy(p1.endereco.rua, "Avenida Principal");
    p1.endereco.n = 123;
    strcpy(p1.endereco.cidade, "Jataí");
    printf("Nome: %s\n", p1.nome);
    printf("Endereço: %s, %d, %s\n", p1.endereco.rua, p1.endereco.n,
           p1.endereco.cidade);
    return 0;
}