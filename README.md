# TrabalhoMaromo
Avaliação P2 aula Linguagens de Programação
// Cesar Guimarães Cardoso Silva
// Ronald Manera
// Luiz Eduardo Gouvea
// João Marcelo Da Cunha Gomes
// Rafael Fernandes De Camargo

//Problema 03

#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
struct Cliente
{
char nome[256];
int cpf;
};
 
struct Conta
{
int numero_da_conta;
struct Cliente cliente;
float saldo;
 
};
int submenu()
{
printf(" MENU PRINCIPAL \n");
printf("===========================================\n\n");
printf("BEM VINDO.\n\nEscolha a opção desejada:\n\n");
printf("1 - Realizar um depósito.\n2 - Realizar um saque.\n3 - Consultar saldo.\n4 - Sair.\n");
}
int main()
{
 
 setlocale(LC_ALL, "portuguese");
struct Cliente registro;
printf("Digite o nome:\n");
scanf("%[^\n]",&registro.nome);
printf("Digite o cpf:\n");
scanf("%d",&registro.cpf);
 
 struct Conta cliente;
printf("Digite o numero da conta:\n");
scanf("%d",&cliente.numero_da_conta);
printf("Digite o saldo:\n");
scanf("%f",&cliente.saldo);
system("cls");
printf("\nConta:\n");
printf("Nome: %s\n", registro.nome);
printf("CPF: %d\n", registro.cpf);
printf("Conta: %d\n", cliente.numero_da_conta);
printf("Saldo: %f\n", cliente.saldo);
 
system("cls");
int opcao, op;
float valor_deposito=0, valor_saque=0;
submenu();
scanf("%d",&opcao);
switch(opcao)
{
case 1:
do{
 printf("Digite o valor a ser depositado:\n");
scanf("%f",&valor_deposito);
if(valor_deposito<0)
{
valor_deposito=0;
printf("Valor inválido.\n");
submenu();
 
 }
cliente.saldo+=valor_deposito;
printf("Depósito efetuado!\n");
printf("Saldo: %f\n",cliente.saldo);
printf("Deseja efetuar outra operação?\nDigite 1 para SIM ou 2 para NÃO:\n");
scanf("%d",&op);
}while(op==1);
 
return 0;
break;
 
 case 2:
do{
 printf("Digite o valor a ser sacado:\n");
scanf("%f",&valor_saque);
if(cliente.saldo<valor_saque)
{
printf("Você não possui o saldo desejado.\n");
}
cliente.saldo-=valor_saque;
printf("Saque efetuado!\n");
printf("Saldo: %f\n",cliente.saldo);
printf("Deseja efetuar outra operação?\nDigite 1 para SIM ou 2 para NÃO:\n");
scanf("%d",&op);
}while(op==1);
return 0;
break;
 
case 3:
system("cls");
printf("Saldo:%f\n", cliente.saldo);
break;
case 4:
 
 break;
}
}
