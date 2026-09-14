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

## 5. Verificar problemas na base a fim de realizar a transformação dos dados
Os dados foram transformados e adequados conforme orientações do desafio. Abaixo descrição resumida do que foi realizado:
1 - Todos os cabeçalhos foram revisados, alterando o tipo de dados quando necessário. Os monetários foram alterados para decimal;
2 - As horas dos projetos foram validadas e colunas complexas foram separadas para facilitar a leitura e modelagem;
3 - Os valores nulos na coluna Super_ssn foram analisados e devidamente tratados como os gerentes da empresa.
4 - Foi feita a checagem cruzada para garantir que nenhum departamento ficasse sem um gerente atribuído. Algumas linhas foram preenchidas pois estavam em branco;
5 - As colunas de "Nome" e "Sobrenome" foram concatenadas em uma única coluna para melhorar a apresentação visual no relatório;
6 - A tabela employee foi mesclada com a tabela department (usando employee como base no Left Join). Também realizamos a junção (Self-Join) para trazer o nome do gerente de cada colaborador em uma nova coluna. Colunas redundantes geradas nestes processos foram eliminadas.
7 - Os dados foram agrupados para gerar a contagem exata de colaboradores subordinados a cada gerente;
8 - No contexto de trazer os nomes dos gerentes ou departamentos para a tabela de colaboradores, foi utilizado a função Mesclar (Merge) porque era preciso cruzar os dados horizontalmente (adicionar novas colunas/atributos baseadas em uma chave comum, como o ID). A função "Acrescentar" (Append) não serviria aqui, pois ela empilha os dados verticalmente (adicionando novas linhas);
9 - Todas as colunas remanescentes que não tem utilidade nos visuais ou nas medidas do relatório foram excluídas de todas as tabelas.
