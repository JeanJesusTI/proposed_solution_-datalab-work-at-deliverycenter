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
Com as informações citadas acimas, chegamos a seguinte solução como arquitetura de dados:  

  
  
  
  ![Arquitetura de Dados](https://user-images.githubusercontent.com/31626353/130517522-9c3108f6-9694-4ca0-96d2-56a244af0d92.png)


  
   
   
   
## Análise e Business Intelligence

  Como solução para segunda etapa proposta, iremos utilizar uma abordagem baseada em um modelo de dados Star-Schema, tendo em vista que esse modelo consiste na diminuição das junções de tabelas e centralização dos dados que irá aprimorar a performance. Podemos ter uma noção do modelo de dados conforme imagem abaixo:
    
    
   ![_Modelagem de dados](https://user-images.githubusercontent.com/31626353/130518688-9c6cc8a9-de21-4a58-a0a8-b6d341b2decc.png)






  
  
Como proposta para a etapa de Business Intelligence, foi optado pela utilização da ferramenta Power BI, para melhor demonstrar os indicadores (KPIs) extraídos dos dados disponibilizados. A optação por essa ferramenta, foi baseada na sua eficácia e também no crescimento da sua utilização nos ultimos anos no mercado; também, a ferramenta é denominada Self-Service BI, que possibilita aos usuários finais a manipulação e criação de relatórios sem necessidade de um conhecimento avançado na área da tecnologia; essa possibilidade ajuda a reduzir a sobrecarga dos profissionais de T.I, tendo em vista que o desenvolvimento e a criação de relatório pode ser feita por usuários finais.
Conforme informado acima, chegamos seguinte solução:
  
  
![RELATORIO_BUSINESS__](https://user-images.githubusercontent.com/31626353/130523440-47d3a80c-3898-4a3c-9b9c-334ef484db6d.png)











