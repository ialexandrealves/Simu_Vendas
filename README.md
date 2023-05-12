#include <stdio.h>
#include <string.h>
float valortotal, valorfrete, valorcelular;


int cksenha(char * pwd1, char *pwd2)
{
	
	//strcmp para devolver um valor inteiro que indica o relacionamento entre pwd1 e pwd2, ou seja se as senhas são diferentes ou iguais
	
	if(strcmp(pwd1, pwd2))
	return 0;                                
	else
	return 1;                               
}

int EscolhaDoAparelho()
{

int aparelho;
 
   // A cada modelo inserido pelo usuário será apresentado uma tela com as devidas informaões
   
   printf("Qual Iphone deseja?\n");
   
   printf("\nDigite o numero do modelo: 11,12,13 e 14.\n");
   scanf("%d", &aparelho);
  
   switch(aparelho)
   {
        
   case 11:
        printf("\nAssinatura - IPHONE 11 64GB\n 3.254,00 ou 12x de 271,16\n");
        valorcelular=3254,00;
        break;
  
   case 12:
        printf("\nAssinatura - IPHONE 12 64GB\n 3.858,00 ou 12x de 321,50\n");
        valorcelular=3858,00;
		break;
        
   case 13:
        printf("\nAssinatura - IPHONE 13 128GB\n 4.799,00 ou 12x de 399,91\n");
        valorcelular=4799,00;
		break;
    
   case 14:
        printf("\n Assinatura - IPHONE 14 128GB\n R$7.067,07 ou 12x de 588,91\n");
        valorcelular=7067,00;
		break;    
        
   default:
        printf("\nnenhum resultado encontrado\n");
        break;
}
return 0;
}

int FormaDePag()
{
   // A cada forma de pagamento inserido pelo usuário será apresentado uma tela com as devidas informaões
   
   int pagamento;
 
   printf("qual a forma de pagamento?\n");
   
   printf("\ncartao de credito(digite 1) | boleto bancario(digite 2) | Pix(digite 3)\n");
   scanf("%d", &pagamento);
  
   switch(pagamento)
   {
   
   case 1:
        printf("pagamento efetuado com cartao de credito\n\n");
        break;
  
   case 2:
        printf("pagamento efetuado com Boleto bancario\n\n");
        break;
	
	case 3:
        printf("pagamento efetuado com pix\n\n");
        break;
   
     default:
        printf("\nnumero invalido\n");
        break;    
}
return 0;
}

int Frete(){

    /* Atribuição de valores para frete (End, CEP, etc), e tipo de entrega, que dependendo da escolha, com o switch
	resultará numa apresentação do tipo de entrega inserido
	*/
	
	int entrega;
    char endereco[50], num{30}, cep[10];
        
    printf("\n\n---------------------------------\n\n");
    printf("Preencha os dados para receber a sua compra");
    printf("\n\n---------------------------------\n\n");
    
    printf("Digite o seu endereco\n");
    scanf("%s", &endereco);
    
    printf("Digite o seu numero\n");
    scanf("%d", &num);
    
    printf("Digite o seu CEP\n\n");
    scanf("%d", &cep);
        
    printf("\n\n---------------------------------\n\n");
    printf("Escolha o tipo de entrega");
    printf("\n\n---------------------------------\n\n");
    
    printf("Economica - gratis - ate 7 dias uteis (digite 1)\n Expressa - R$ 10,96 - ate 3 dias uteis (digite 2)\n Receba amanha - R$ 14,99 - ate 1 dia util (digite 3)\n");
    scanf("%d", &entrega);
    
switch(entrega){

    case 1: 
    printf("CONFIRMADA Entrega economica - gratis - ate 7 dias uteis");
    valorfrete=0;
    break;
    
    case 2: 
    printf("CONFIRMADA Expressa - R$ 10,96 - ate 3 dias uteis");
    valorfrete=10,96;
    break;
    
    case 3: 
    printf("CONFIRMADA Receba amanha - R$ 14,99 - ate 1 dia util");
    valorfrete=14,99;
    break;
    
    default:
    printf("opcao invalida");
    break;
}
     return 0;
}

int Avaliacao(){
	
	// É atribuido um valor para avaliação e depois apresentado na tela para o usuário
	
     int avaliacao;
     printf ("\n agradecemos pela compra \n\n");
     printf ("\n Poderia nos ajudar com um feedback da sua experiencia de compra?\n");
     printf ("\n Mais tarde(digite 1)\nRuim (digite 2)\nBom (digite 3)\ Otimo (digite 4))");
     scanf("%d", &avaliacao);
     printf("\n\nRecebemos o seu feedback, obrigado!");
     printf("avaliacao e %d\n", avaliacao);
return 0;
}

float calculototal(){
	
	// Calculo do valor total ( valor do celular + valor frete )
	
	valortotal= valorcelular+valorfrete;
	printf ("\n\nvalor total a pagar: %.2f\n\n", valortotal);
	return 0;
}




int main()
{

    // declaração de variaveis
    char senha[5] [30], Nome[50], Sobrenome[50];
	int tam1, tam2, tam3, rc1, rc2;
	int ano, dia, mes;
	
    printf("Bem-vindo ao AIPHONE BR\n\n");
	
	//Chamada de rotina
	EscolhaDoAparelho();
	
	//Apresentação inicial
	
	printf("\n\nBem vindo faca seu cadastro!");
	
    printf("Informe seus dados\n\n");

    printf("Primeiro nome \n\n");
    scanf("%s", &Nome);

    printf("\nSobrenome\n\n");
    scanf("%s", &Sobrenome);

    printf("\nData de nascimento\n\n");
    
    printf("\nDia\n\n");
    scanf("%d", &dia);
    
     printf("\nMes\n\n");
    scanf("%d", &mes);

    printf("\nAno\n\n");
    scanf("%d", &ano);

   // Foi utilizado um if-else para identificar se o usuário é menor de idade, no caso de ser menor é apresentado uma mensagem indicando que o usuário peça ajuda a um responsável

    if(ano>2004){
	printf("\npeca ajuda a um responsavel");    	
	} 
    
    
	
	printf("\ndigite uma senha\n");
	scanf("%s", &senha[1]);
	
	printf("\nconfirme sua senha\n ");
	scanf("%s", &senha[2]);
	
	// Nesse if, com o strlen é possivel ler a quantidade de caracteres existentes e assim controlar a quantidade de caracters inseridos(min 8 caracter)s
	
	if(strlen(senha[1]) <8) {
		printf("sua senha precisa conter mais de 8 caracteres\n");
		return 1;
	}
	if(strlen(senha[2]) < 8 ) {
		printf("senha de confirmacao esta errada\n");
		return 1;
	}
	
	/* rc1 variavel usada para chamar a rotina cksenha, onde são passados por parametros, as senhas inseridas anteriormente pelo usuário, 
	onde é feita uma comparação entre ambas e posteriormente entregando um valor interio, tal como a resposta se são diferentes ou iguais
	*/
	
   rc1=cksenha(senha[1], senha[2]);                                                                                 
   if(rc1 == 0){
	printf("as senhas estao diferentes\n");
	return 1;

   }  
	
   printf("\nCadastro concluido!\n\n");

   // Chamadas de rotinas indicadas no topo do cód

   FormaDePag();
   Frete();
   calculototal();
   Avaliacao();

return 0;
}
