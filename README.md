# PROPOSTA DE SOLUÇÃO | Delivery Center 

O seguinte repositório tem por objetivo a resolução do teste disponibilizado pela Deliverycenter. A estrutura do projeto será dividido em 3 partes conforme estruturado no teste disponibilizado, sendo elas:

- Arquitetura e Engenharia de dados
- Análise e Business Intelligence
- Ciência e Modelagem de dados

## Arquitetura e Engenharia de Dados


Com base nas informações obtidas baseadas no enunciado, iremos utilizar uma abordagem baseada numa arquitetura de dados fundamentadanos conceitos de **Data Lake** e cubos **Data Marts**, utilizando como ferramenta de migração de dados a ferramenta **SAP Data Services**.
Para entendermos melhor a utilização desta abordagem, iremos definir o conceito básico de cada uma delas.

**SAP Data Services:** É uma ferramenta de integração e transformação de dados, que nos permite desenvolver fluxos que executam jobs capazes de realizar a captura de dados provenientes de diversas fontes. A optação por essa ferramenta foi baseada na necessidade da empresa na utilização do streaming de dados. O SAP Data Services permite a utilização de micro-batch para realizar o carregamento dos dados, onde podemos definir o tempo de execução de cada Job para um período mais curto, para que as cargas sejam carregadas em tempo real com alta performance.

**Data Lake:** O Data Lake pode ser definido como um espaço centralizador, o qual possui grande poder de armazenamento de dados provenientes de fontes **estruturadas** e **não estruturadas**. Essa abordagem é interessante neste caso devido a necessidade de uma estrutura que permita a escalabilidade; já que, um dos problemas apresentados pelo enunciado é o aumento exponencial do volume de dados. Com essa estrutura, além de termos uma escalabilidade maior,podemos obter dados de fontes variadas, o que é imprescindível para empresa, visto que a mesta está se baseando no conceito de Data Driven, para esse caso fictício, iremos utilizar o Banco de Dados Oracle 19c.
A optação pela utilização de **Data Lake** e não um **DataWarehouse**, foi baseada na limitação que um Datawarehouse possui, devido o mesmo ser limitado ao armazenamento de dados já tratados e padronizados; essa limitação poderia afetar de forma negativa a empresa, visto que, o armazenamento de dados não-estruturados seria um grande problema.
Além disso, a adoção de um DataLake pode trazer vários benefícios, como por exemplo:

- Possibilidade de Acessos Simultâneos.
- Disponibilidade de Dados.
- Grande poer de Armazenamento.
- Possibilidade de acesso aos dados por plataformas de análise de dados.
- Compatibilidade com variadas fontes de dados.


Como um DataLake é baseado em variadas fontes de dados, os mesmos devem ser organizados para que um analista de negócio consiga realizar análises seguimentadas, sejam por setores, ou qualquer outro parâmetro de sua escolha, e por isso, faremos a adoção da utilização de cubos OLAP.

**Cubo OLAP:** Um cubo OLAP pode ser definido como uma estrutura composta por dimensões e uma tabela fato. Basicamente, as *dimensões* são os eixos do cubo, que podem ser definidas como diferentes angulos de se verificar uma métrica. Já a **fato**, é uma tabela composta por medidas centralizadas, as quais serão apresentadas dentro de um determinado domínio de análise.

Com os cubos criados (camada de datamart), poderemos então aplicar técnicas de Business Intelligence/ Analytics e Data Science utilizando diversas ferramentas, possibilitando a aplicação de análises, sejam elas: *Descritivas*, *Prescritivas*, *Preditivas* e outras. Para isso, poderemos contar com ferramentas como: Power BI, Linguagem R (R-Studio), Microsoft Azure e Jupyter Notebook.
  
  
  ![Arquitetura de Dados](https://user-images.githubusercontent.com/31626353/130517522-9c3108f6-9694-4ca0-96d2-56a244af0d92.png)
















