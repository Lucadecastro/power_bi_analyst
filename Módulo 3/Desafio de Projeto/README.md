README: Transformações e Integração Power BI com MySQL no Azure

Introdução

Este projeto foi desenvolvido como parte de um desafio, cujo objetivo era criar relatórios no Power BI a partir de uma base de dados armazenada em um servidor MySQL no Azure. Ao longo deste processo, foram realizadas diversas transformações e modelagens de dados para preparar a base para visualizações eficazes. O foco dos relatórios foi na análise de departamentos e projetos, permitindo insights sobre a gestão e operações da empresa.

Descrição do Projeto

Este desafio teve como objetivo integrar o Power BI com um banco de dados MySQL hospedado na Azure para criar relatórios que ofereçam insights relevantes para a gestão da empresa.

Ferramentas Utilizadas

Azure: Para criar e hospedar o banco de dados MySQL.
MySQL Workbench: Para gerenciar e manipular a base de dados no Azure.
Power BI: Para a criação de relatórios e visualizações baseadas nos dados extraídos do MySQL.

PASSO 1 - Criação de uma instância na Azure para MySQL
PASSO 2 - Criar o Banco de Dados com Base Disponível no GitHub
PASSO 3 - Integração do Power BI com MySQL no Azure
PASSO 4 - Verificar Problemas na Base a Fim de Realizar a Transformação dos Dados

Script:

Instancia Azure - MySQL

Processo de ativar a instância

1º Criar conta na Azure com meu e-mail corporativo da Microsoft

2º Assinar assinatura gratuita e criar instância na Azure de servidor MySQL.

3º Após criar a instância com permissão a acesso público de qualquer serviço, copiar hostname e password para uso posterior.

4º Tentei realizar criação do banco de dados seguindo o script do curso na Azure CLI, porém não tive sucesso.

5º Realizei todas as fases do script no Mysql Workbench após conectar no Workbench usando o hostname da instância da Azure, realizei a criação do banco e a inserção de dados também, testando as demais queries para me certificar de que estava tudo criado corretamente.

7º Integrei Power BI com MySQL via "Obter Dados -> Banco de Dados MySQL" e informando o hostname e o nome do banco criados na Azure.

8º - Transformando os dados

1ª ação: Verifiquei os cabeçalhos e tipos de dados. Não alterei os nomes das colunas pois achei que estavam intuitivas o suficiente, e vi que os tipos já estavam corretos.

2ª ação: Verifique a existência dos nulos, acrescentei Super_ssn a um funcionário que estava como nulo colocando o ssn do supervisor do departamento dele, e acrescentei um super_ssn a um supervisor cujo ssn era o dele próprio, visto que ele era o gerente. Realizei a remoção de colunas desnecessárias com prefixo azure_company.tabela, e depois disso realizei as mesclagens conforme orientação.

3ª Não havia departamento sem gerente

4ª Eliminei a linha de horas que continha 0 horas trabalhadas, pois ela não fazia sentido, mesmo com o ssn sendo o do gerente.

5ª Explicando porque ao mesclar nomes de departamento e localização, obtendo combinação única, podemos apenas utilizar o mesclar e não o atribuir:
Mesclar: Combina dados de duas tabelas com base em colunas comuns, adicionando informações complementares. No projeto, mesclamos departament e dept_locations para garantir combinações únicas de departamento e localização.

Atribuir: Une dados de duas tabelas com a mesma estrutura, empilhando registros semelhantes. Como as tabelas departament e dept_locations possuem dados diferentes, utilizamos mesclar, não atribuir.

Passei então para a fase de criação de relatório aonde criei uma única página.

Conclusão:

Este desafio proporcionou uma grande oportunidade para aprofundar o conhecimento na integração do Power BI com bancos de dados em nuvem, além de desenvolver habilidades em transformação de dados. Durante o processo, enfrentei muitos desafios, mas consegui superá-los com pesquisas e práticas.