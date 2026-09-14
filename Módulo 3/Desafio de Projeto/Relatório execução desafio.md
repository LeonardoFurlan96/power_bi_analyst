# RELATÓRIO DO DESAFIO Integrando Dados com MySQL Azure e Transformando com Power BI

## 1.	Descrevendo o desafio de projeto
O desafio se trata de adicionar um banco de dados MySQL na nuvem da Microsoft Azure, conectar ao Power BI e dentro do software realizar a transformação dos daos nas tabelas importadas.

## 2.	Criando uma instância do MySQL na Azure
Foi criado uma instânica dentro da plataforma Azure para um banco de dados MySQL. O processo foi simples, seguinto o fluxo estabelecido pela plataforma e fazendo as configurações da instância de forma mais simples, por
se tratar apenas de um teste.

## 3.	Criar o Banco de dados com base disponível no github
Foi criado um banco de dados na Azure dentro da instância MySQL criada. A criação foi feita através do poweshell no próprio navegador. Esta etapa foi executada de forma simples, seguindo o comando e o código disponibilizado para criação do banco e das tabelas.

Para popular as tabelas com o dados, foi utilizado o software Dbeaver. Precisei adicionar o seguinte comando no código para funcionar:
No inicio do código para desativar as chaves estrangeiras
SET FOREIGN_KEY_CHECKS = 0;
No fim do código para reativar:
SET FOREIGN_KEY_CHECKS = 1;

Após estas alterações, os dados foram populados nas tabelas.

## 4.	Integração do Power BI com MySQL no Azure 
Após alguns erros, tiver que reconfigurar o firewall na azure. Após esta ação consegui conectar o power BI a nuvem e carregar as tabelas. Esta etapa do desafio ocorreu sem outros problemas.

## 5. 
