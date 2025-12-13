# Questão 07

7 - Crie uma struct para um Ponto2D com os campos x e y. Em seguida, crie uma struct Círculo que
tenha um campo do tipo Ponto2D (para o centro do círculo) e um campo raio (ponto flutuante).
Declare uma variável Círculo, preencha seus dados e exiba o centro (x e y) e o raio.

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct ponto_2d
    {
        float x, y;
    };

    struct circulo
    {
        struct ponto_2d centro;
        float raio;
    };
    
    struct circulo c1;
    c1.centro.x = 3.5;
    c1.centro.y = 7.2;
    c1.raio = 5.0;
    printf("\nCentro do círculo: (%.2f, %.2f)\n", c1.centro.x, c1.centro.y);
    printf("Raio: %.2f\n\n", c1.raio);
    return 0;
}