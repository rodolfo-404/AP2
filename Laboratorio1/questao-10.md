# Questão 10

Escreva um trecho de código para fazer a criação dos novos tipos de dados conforme solicitado abaixo:

Horário: composto de hora, minutos e segundos.
Data: composto de dia, mês e ano.
Agenda: composto de uma data, horário e texto que descreve o compromisso.
 
---
```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
int intervalo(int valor, int min, int maxi)
{
    return valor < min || valor > maxi;
}
int main()
{
    setlocale(LC_ALL, "Portuguese");
    struct ficha_agenda
    {
        int hr, min, seg, dia, mes, ano;
        char compromisso[100];
    };
    struct ficha_agenda agenda;
    printf("\n-----------------Agenda-----------------\n\n");
    printf("Tipo de Compromisso: ");
    fgets(agenda.compromisso, 200, stdin);
    printf("\n___Data do Compromisso___\n");
    printf("Dia: ");
    scanf("%d", &agenda.dia);
    printf("Mês (1 a 12): ");
    scanf("%d", &agenda.mes);
    printf("Ano: ");
    scanf("%d", &agenda.ano);
    printf("\n___Horário do Compromisso___\n");
    printf("Hora: ");
    scanf("%d", &agenda.hr);
    printf("Min: ");
    scanf("%d", &agenda.min);
    printf("Seg: ");
    scanf("%d", &agenda.seg);
    if (intervalo(agenda.mes, 1, 12) || intervalo(agenda.hr, 0, 23) ||
        intervalo(agenda.min, 0, 59) || intervalo(agenda.seg, 0, 59))
    {
        printf("\nERRO! Data ou hora inválida.\n");
    }
    else
    {
        printf("\n\n_____Compromisso Agendado_____\n");
        printf("Evento: %s", agenda.compromisso);
        printf("Data do Evento: %02d/%02d/%02d\n", agenda.dia, agenda.mes,
               agenda.ano);
        printf("Horário: %02d:%02d:%02d\n", agenda.hr, agenda.min, agenda.seg);
    }
    return 0;
}