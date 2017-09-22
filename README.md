#include <stdio.h>
#include <stdlib.h>

	FILE *file;
	char sair;
	char texto[10];
	int opcao;
	double codCli = 1200;


	struct cadCliente
	{
		double codigoCli;
		char nome[20];
		char sobrenome[20];
		double rg;
		float cpf;
		char endereco[100];
		double numero;
		int dtnasc;
		int msnasc;
		int anonasc;
		double cartHab;
		int msVcHab;
		int anoVcHab;
	};
	
	struct cadAuto
	{
		double codigoAuto;
		char marca[10];
		char modelo[25];
		int ano;
		int modeloCar;
		char codClass;
	};
	
	struct codClass //falta codigo, descrição//
	{
		float basico;
		float intermediario;
		float executivo;
	};
	
	struct os
	{
		double codigoOS;
		struct cadCliente;
		struct cadAuto;
	};
	
//corrigir mudar struct cadAuto codClass para int//
//tirar struct de classificação de autos//


void cadastroAuto (struct cadAuto cadastroauto) {

cadastroauto.codigoAuto = ("%d", rand () );

printf ("Digite a marca do veiculo\n");
scanf  ("%s", &cadastroauto.marca);
printf ("Digite o modelo do veiculo\n");
scanf  ("%s", &cadastroauto.modelo);
printf ("Digite o ano do veiculo\n");
scanf  ("%s", &cadastroauto.ano);
printf ("Digite o modelo (ano) do veiculo\n");
scanf  ("%d", &cadastroauto.modeloCar);
printf ("     Qual a categoria do veiculo?\n");
printf ("[1]Basico [2]Intermediario [3]Avançado\n");
/*scanf  ("%d", &opcao)
	if (opcao = 1) {
		cadastroauto.codigoClass = basico;
			}
	if (opcao = 2) {
		cadastroauto.codigoClass = intermediario;
			}
	if (opcao = 3) {
		cadastroauto.codigoClass = executivo;
			}
	else 		{
		printf ("Digite uma opção valida");
			}*/
system ("cls");

printf ("Codigo: %d\nMarca: %s\nModelo: %s\nAno/Modelo: %d/%d\nCategoria: %d", cadastroauto.codigoAuto, cadastroauto.marca, 
cadastroauto.modelo, cadastroauto.ano, cadastroauto.modeloCar,cadastroauto.codClass);
sprintf (texto, "%d", cadastroauto.codigoAuto);
file = fopen (texto, "w+t");
fprintf (file, "%d\n%s\n%s\n%d\n%d\n%d", cadastroauto.codigoAuto, cadastroauto.marca, 
cadastroauto.modelo, cadastroauto.ano, cadastroauto.modeloCar/*cadastroauto.codClass*/);
fclose (file);

}

void consultaCliente(struct cadCliente consulcliente){
		printf ("Digite o codigo do Cliente\n");
		scanf ("%d", &consulcliente.codigoCli);
		consulcliente.codigoCli = atoi(texto);
		file = fopen (texto, "r");
		fscanf (file, "%d\n%s\n%s\n%d\n%f\n%s\n%d\n%d\n%d\n%d\n%d\n%d\n%d\n", &consulcliente.codigoCli, &consulcliente.nome, &consulcliente.sobrenome, &consulcliente.rg, &consulcliente.cpf, 
               &consulcliente.endereco, &consulcliente.numero, &consulcliente.dtnasc, &consulcliente.msnasc, 
				&consulcliente.anonasc, &consulcliente.cartHab, &consulcliente.msVcHab, &consulcliente.anoVcHab);
		printf ("%s\n%s\n%s\n%d\n%f\n%s\n%d\n%d\n%d\n%d\n%d\n%d\n%d\n", texto, consulcliente.nome, consulcliente.sobrenome, consulcliente.rg, consulcliente.cpf, 
                consulcliente.endereco, consulcliente.numero, consulcliente.dtnasc, consulcliente.msnasc, 
				consulcliente.anonasc, consulcliente.cartHab, consulcliente.msVcHab, consulcliente.anoVcHab);
		fclose (file);
	}	
	
void cadastroCliente(struct cadCliente cliente){
		printf ("Codigo\n");
		scanf ("%d", &cliente.codigoCli);
		printf ("Nome\n");
		scanf ("%s", &cliente.nome);
		printf("Sobrenome\n");
		scanf("%s", &cliente.sobrenome);
		printf("R.G.\n");
		scanf("%d", &cliente.rg);
		printf("C.P.F.\n");
		scanf("%f", &cliente.cpf);
		printf("Endereco (sem rua, av., e etc)\n");
		scanf("%s", &cliente.endereco);
		printf("Numero\n");
		scanf("%d", &cliente.numero);
		printf("Dia de Nascimento\n");
		scanf("%d", &cliente.dtnasc);
		printf("Mes de Nascimento\n");
		scanf("%d", &cliente.msnasc);
		printf("Ano de Nascimento\n");
		scanf("%d", &cliente.anonasc);
		printf("Carteira de Habilitacao\n");
		scanf("%d", &cliente.cartHab);
		printf("Mes de Vencimento da Habilitacao\n");
		scanf("%d", &cliente.msVcHab);
		printf("Ano de Vencimento da Habilitacao\n");
		scanf("%d", &cliente.anoVcHab);
		system ("cls");
		printf ("Codigo do Cliente: %d\nNome: %s %s\nR.G.: %d\nC.P.F.: %f\nEndereco: %s, %d\nData de Nascimento: %d / %d / %d\n"
		"Carteira de Habilitação: %d\nVencimnto da Habilitacao: %d / %d\n", cliente.codigoCli, cliente.nome, cliente.sobrenome, cliente.rg, cliente.cpf, 
                cliente.endereco, cliente.numero, cliente.dtnasc, cliente.msnasc, 
				cliente.anonasc, cliente.cartHab, cliente.msVcHab, cliente.anoVcHab);
		sprintf (texto, "%d", cliente.codigoCli);	// Converte Double/Int pra Char/String
		file = fopen (texto, "w+t");
		fprintf (file, "%s\n%s\n%s\n%d\n%f\n%s\n%d\n%d\n%d\n%d\n%d\n%d\n%d\n", texto, cliente.nome, cliente.sobrenome, cliente.rg, cliente.cpf, 
                cliente.endereco, cliente.numero, cliente.dtnasc, cliente.msnasc, 
				cliente.anonasc, cliente.cartHab, cliente.msVcHab, cliente.anoVcHab );
		fclose (file);
	}

int main(int argc, char *argv[]) {
	
	while (sair = 'sair'){
		
		printf("\n\n---------------------Teste de Cadastro de Clientes---------------------\n\n\n");
		printf("====================Veic Loc - Locadora de Veiculos====================\n");
		printf("=============[1] Cliente [2] Automoveis [3] Ordem de Servico===========\n");
		scanf ("%d", &opcao);
		
			switch (opcao){
						  
				case 1:
				
					printf ("======================[1] Cadastrar [2] Consultar======================\n\n");
						scanf ("%d", &opcao);
						if (opcao == 1){
					
								struct cadCliente clientes;
								cadastroCliente(clientes);
						} else {
										
								struct cadCliente consulcliente;
								consultaCliente (consulcliente);
								
							  }
					
				break;
				case 2:
					{
					struct cadAuto autos;
					cadastroAuto(autos);
					}
				
				break;	
				case 3:
				
					printf ("Teste caso 3\n\n");
					exit (1);
				
				break;
						  }			
		
						 }
		
	
	return 0;
}
