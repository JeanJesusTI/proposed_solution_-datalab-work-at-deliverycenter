# Proposta de Solução | Delivery Center 


   O presente documento tem por objetivo a resolução do teste disponiblizado pela DeliveryCenter. A proposta é realizar uma abordagem dos pontos passados no enunciado para resolver e propor soluções a fim de de agregar valores a empresa. O documento está dividido em 4 partes, sendo elas:<br>

- Arquitetura e Engenharia de dados
- Análise e Business Intelligence
- Ciência e Modelagem de dados
- Machine Learning

## Arquitetura e Engenharia de Dados


   Com base nas informações obtidas baseadas no enunciado, iremos utilizar uma abordagem baseada numa arquitetura de dados fundamentadanos conceitos de **Data Lake** e cubos **Data Marts**, utilizando como ferramenta de migração de dados a ferramenta **SAP Data Services**.
Para entendermos melhor a utilização desta abordagem, iremos definir o conceito básico de cada uma delas.

<br/>

![SAP](https://user-images.githubusercontent.com/31626353/130627197-d0419285-dc2c-402f-a69c-b1fb460d3a9f.jpg)


**SAP Data Services:** É uma ferramenta de integração e transformação de dados, que nos permite desenvolver fluxos que executam jobs capazes de realizar a captura de dados provenientes de diversas fontes. A optação por essa ferramenta foi baseada na necessidade da empresa na utilização do streaming de dados. O SAP Data Services permite a utilização de micro-batch para realizar o carregamento dos dados, onde podemos definir o tempo de execução de cada Job para um período mais curto, para que as cargas sejam executadas em tempo real com alta performance.

<br/>

![data-lake2](https://user-images.githubusercontent.com/31626353/130624767-89ec6b9e-894f-427f-92bb-d1849c6214c0.jpg)



    

<br/>
<br/>

**Data Lake:** O Data Lake pode ser definido como um espaço centralizador, o qual possui grande poder de armazenamento de dados provenientes de fontes **estruturadas** e **não estruturadas**. Essa abordagem é interessante neste caso devido a necessidade de uma estrutura que permita a escalabilidade; já que, um dos problemas apresentados pelo enunciado é o aumento exponencial do volume de dados. Com essa estrutura, além de termos uma escalabilidade maior,podemos obter dados de fontes variadas, o que é imprescindível para empresa, visto que a mesta está se baseando no conceito de Data Driven, para esse caso fictício, iremos utilizar o Banco de Dados Oracle 19c.
A optação pela utilização de **Data Lake** e não um **DataWarehouse**, foi baseada na limitação que um Datawarehouse possui, devido o mesmo ser limitado ao armazenamento de dados já tratados e padronizados; essa limitação poderia afetar de forma negativa a empresa, visto que, o armazenamento de dados não-estruturados seria um grande problema.
Além disso, a adoção de um DataLake pode trazer vários benefícios, como por exemplo:

- Possibilidade de Acessos Simultâneos.
- Disponibilidade de Dados.
- Grande poer de Armazenamento.
- Possibilidade de acesso aos dados por plataformas de análise de dados.
- Compatibilidade com variadas fontes de dados.


Como um DataLake é baseado em variadas fontes de dados, os mesmos devem ser organizados para que um analista de negócio consiga realizar análises seguimentadas, sejam por setores, ou qualquer outro parâmetro de sua escolha, e por isso, faremos a adoção da utilização de cubos OLAP.


<br/>

![OLAP](https://user-images.githubusercontent.com/31626353/130625604-690e41d8-77ea-43dd-aaa6-64f6d88cfc2a.jpg)




<br/>

**Cubo OLAP:** Um cubo OLAP pode ser definido como uma estrutura composta por dimensões e uma tabela fato. Basicamente, as *dimensões* são os eixos do cubo, que podem ser definidas como diferentes angulos de se verificar uma métrica. Já a **fato**, é uma tabela composta por medidas centralizadas, as quais serão apresentadas dentro de um determinado domínio de análise.

  Com os cubos criados (camada de datamart), poderemos então aplicar técnicas de Business Intelligence/ Analytics e Data Science utilizando diversas ferramentas, possibilitando a aplicação de análises, sejam elas: *Descritivas*, *Prescritivas*, *Preditivas* e outras. Para isso, poderemos contar com ferramentas como: Power BI, Linguagem R (R-Studio), Microsoft Azure e Jupyter Notebook.
Com as informações citadas acimas, chegamos a seguinte solução como arquitetura de dados:  

<br/>

  
  
  
  ![Arquitetura de Dados](https://user-images.githubusercontent.com/31626353/130517522-9c3108f6-9694-4ca0-96d2-56a244af0d92.png)


  
   
   
   
## Análise e Business Intelligence

  Como solução para segunda etapa proposta, iremos utilizar uma abordagem baseada em um modelo de dados Star-Schema, tendo em vista que esse modelo consiste na diminuição das junções de tabelas e centralização dos dados que irá aprimorar a performance. Podemos ter uma noção do modelo de dados conforme imagem abaixo:
    
    
   ![_Modelagem de dados](https://user-images.githubusercontent.com/31626353/130518688-9c6cc8a9-de21-4a58-a0a8-b6d341b2decc.png)





<br/>

  Como proposta para a etapa de Business Intelligence, foi optado pela utilização da ferramenta Power BI, para melhor demonstrar os indicadores (KPIs) extraídos dos dados disponibilizados. A optação por essa ferramenta, foi baseada na sua eficácia e também no crescimento da sua utilização nos ultimos anos no mercado; também, a ferramenta é denominada Self-Service BI, que possibilita aos usuários finais a manipulação e criação de relatórios sem necessidade de um conhecimento avançado na área da tecnologia; essa possibilidade ajuda a reduzir a sobrecarga dos profissionais de T.I, tendo em vista que o desenvolvimento e a criação de relatório pode ser feita por usuários finais.
Conforme informado acima, chegamos seguinte solução:
  
<br/>
<br/> 
 
![RELATORIO_BUSINESS__](https://user-images.githubusercontent.com/31626353/130523440-47d3a80c-3898-4a3c-9b9c-334ef484db6d.png)

  
  
<br/>  
<br/>
  
  
### Especificação de Relatório:
  
  
  
| Item               |  Descrição          |  Importância        |
| ------------------- | ------------------- | ------------------- |
|  1°                 |  Filtro             |  Permite a análise dos dados por meios de visões diferentes, podendo aplicar os seguintes filtros:  <br/> •	Filtro por Centro de Distribuição <br/> • Filtro por Canais de Venda <br/> • Filtro por Tipode Entregador|
|  2°    |  Qtd. Pedidos  |  Permite ter o Controle geral de todos os pedidos registrados. |
|  3°  |  Qtd. Entregadores  |  Permite saber a quantidade geral de entregadores, permitindo ao analista verificar se há necessidade da contratação de pessoal em decorrência do número de pedidos e outras causas. |
|  4°                 |  Qtd. Pedidos Cancelados |  Permite ter o controle dos pedidos cancelados, a fim de identificar possíveis falhas ou melhorias a serem implementadas. |
|  5°                 |  Qtd. Centros de Distribuição |  Permite saber a quantidade de centro de distribuições cadastradas, e através do filtro analisar o desempenho de cada uma. |
|  6°                 |   Qtd. Pedidos realizados |  Permite saber a quantidade de pedidos que foram efetuados com sucesso, funcionando assim (através dos filtros), como uma métrica de análise de desempenho. |
|  7°                 |  Proporção de Entregas por Cidades |  Permite obter uma visão geral das entregas realizadas por cidades. |
|  8°                 |  Comparação de Entregas por motoboy x Bikers |  Permite a verificação da quantidade de entregas efetuadas pelas duas categorias disponíveis. |
|  9°                 |  Ranking |  Permite a visualização de um Ranking dinâmico (ou seja, baseado nas seleções dos filtros desejados), possibilitando a visualização o desempenho dos centros baseados nas suas entregas realizadas. |
|  10°                 |  Centro de Distribuição / condicional de performance |  Permite saber o nome do Centro de distribuição, auxiliado com um indicador visual. A utilização desse indicador, permite que o analista encontre de maneira rápida, centros que estão com desempenho abaixo do esperado; a fim de implementar melhorias para melhorar sua performance. Os ícones são divididos em 3 categorias: <br/> <br/>Verde: Pedidos concluídos > 60% <br/>Amarelho: Pedidos Concluidos <=60% > 50% <br/> Vermelho: Pedidos concluídos < 50 |
|  11°                 |  Qtd. Pedidos Concluídos por Centro de Distribuição |  Permite saber a quantidade de pedidos concluídos baseados no centro de distribuição. |
|  12°                 |  Qtd. Pedidos Cancelados por Centro de Distribuição |  Permite saber a quantidade de pedidos Cancelados baseados no centro de distribuição. |
|  13°                 |  % de  Pedidos Concluidos por Centro de Distribuição |  Permite saber a proporção em percentagem dos pedidos concluídos por Centro de distribuição. |
|  14°                 |  % de  Pedidos Cancelados por Centro de Distribuição |  Permite saber a proporção em percentagem dos pedidos cancelados por Centro de distribuição. |

De modo geral, os indicadores abordados podem ajudar a empresa, dando a possibilidade de identificar / mitigar possíveis problemas de desempenho, fazendo com que seja possível a tomada de ações a fim de detectar e previnir problemas mais graves no futuro.

<br />
<br />

## Ciência e Modelagem de dados
<br />
Para realização das análises, foi utilizado o Jupyter notebook juntamente com a linguagem Python, a fim de entender melhor os dados, e entender padrões ocultos.
A primeira parte, consiste na análise do dataset Drivers. A análise completa pode ser vista clicando <a href = 'https://github.com/JeanJesusTI/proposed_solution_-datalab-work-at-deliverycenter/blob/main/An%C3%A1lise-de-Dados/Driver%20Analysis.ipynb'>aqui.<a/><br />
Para realizarmos a análise seguimos os seguintes passos:
<br />

##### 1° Importação das bibliotecas

   
   Como o dataset não possui informações tão complexas, iremos utilizar apenas duas bibliotecas para extrair insumos dos mesmos.
<br/>
   
![image](https://user-images.githubusercontent.com/31626353/130535657-9a11d31c-2331-41c5-ab33-18e8cfb8f1cb.png)

<br/>

##### 2° Leitura e visualização prévia dos dados

Utilizamos o pandas para realizar a leitura do arquivo de dados, como uma funcionalidade integrada da ferramenta, os arquivos lidos são transformados em dataframes, o que nos dá uma série de possibilidades de visualização e manipulação dos dados.
 <br/>
   
![image](https://user-images.githubusercontent.com/31626353/130535923-23a4d9c4-0786-446e-ac60-da6c2310f6c3.png)
   
 
<br/>

##### 3° Análisando a proporcionalidade em porcentagem de cada tipo de entregador
Ao realizarmos os calculos, chegamos a conclusão que:<br />
   - A quantidade de Motociclistas, equivalem a **66.79%** do total de entregadores
   - A quantidade de Bikers, equivalem a **33.21%** do total de entregadores.
   
   
<br/>  
   
 ![image](https://user-images.githubusercontent.com/31626353/130546986-a61cc849-1d07-4a79-a5cf-d740f92be4d6.png)

   

<br/> 
 Podemos confirmar o calculo efetuado, utilizando uma opção visual do seaborn chamada countplot, e nele é possível ver que, o numero de motoboys é bem maior que o numero de bikers, conforme imagem abaixo:
   
<br/> 
<br/>
   
![image](https://user-images.githubusercontent.com/31626353/130547583-91b8a061-fde9-41b8-a161-be934687b994.png)




<br/>

##### 4° Análisando a proporcionalidade em porcentagem do tipo de entregador, baseado em sua categoria
   Após a realização da análise e dos calculos, chegamos a seguinte informação:
   
|   ENTREGADOR |  TIPO                |  PROPORÇÃO|
| :---         |:---                  |   :---:   |
| BIKER       | Freelancer            | 99.94%    |
| BIKER       | Logistic Operator     | 0.06%     |
| MOTOBOY     | Freelancer            | 72.56%    |
| MOTOBOY     | Logistic Operator     | 27.44%    |
   
   
   
   
<br/>
   
## Machine Learning
   
<br/>
   
   - A fim de agregar mais valor as análises realizadas, foi desenvolvido um algoritimo de machinne learning utilizando algumas técnicas estatisticas e de amostragem para realizar previsão da situação dos pedidos, ou seja, se eles serão entregues ou cancelados; como a análise e o desenvolvimento são um pouco extenso, você pode acessa-lo clicando <a href = "https://github.com/JeanJesusTI/proposed_solution_-datalab-work-at-deliverycenter/blob/main/An%C3%A1lise-de-Dados/Machine%20Learning%20-%20Orders.ipynb">aqui</a>.

<br/>   
   
### Observações:
   
<br/>
   
   - Para realização da análise e desenvolvimento, foi selecionado o algoritimo *DecisionTreeClassifier*, visto que se trata de um problema de classificação. O objetivo principal seria criar um algoritimo que conseguisse prever com um bom nivel de acuracidade a situação das entregas dos pedidos, por tanto, não foram utilizadas otimizações de hiper-parâmetros, visto que o algoritimo conseguiu um excelente resultado com suas configurações padrão.
   
<br/>
   
   - Para as técnicas de amostragem **OverSampling** e **UnderSampling**, foram utilizadas as funções *SMOTE* e *TomekLinks* da biblioteca **imblearn**.
   
<br/> 
   
   - É importante frizar que, a acuracidade alta de um algoritimo pode ser sinal de overfitting que deve ser investigado, e / ou utilizar outras técnicas, como por exemplo validação cruzada e outros.
      
<br/> 
      
   - Correlação Não implica Causalidade.
      
<br/> 
   
   - A técnica de amostragem que obteve um melhor resultado, foi a técnica de UnderSampling, e baseado nela foram feitas algumas análises dos resultados, a fim de analisar onde o algoritimo mais errou.
 
<br/>
   
### Como resultado, obtivemos a seguinte conclusão:
   
   O algoritimo com a melhor performance obteve **99.10%** de Acuracidade, e, analisando mais a fundo, obtivemos a seguinte matriz de Confusão:
   
<div align='center'>
   
|   2157 |  12    |  
| :---   |:---    | 
| 8       | 55    | 
   
</div>

   
<br/>
   Baseado nessa informação, podemos calcular a porcentagem de acerto para cada opção de classificação do algoritimo, conforma imagem abaixo:<br/>
   
![image](https://user-images.githubusercontent.com/31626353/130551506-5cdc9a21-993d-4ea5-b62d-aa3253b13922.png)

   
<br/>

Com isso, podemos inferir a porcentagem de acerto para cada classe do algoritimo, e conforme tabela abaixo, podemos visualizar que o algoritimo tende a errar mais na classificação de pedidos cancelados:<br/>
  
<div align='center'>
   
|   ENTREGUES |  99.45 %   |  
| :---        |:---        | 
| CANCELADOS  | 87.30 %    |

   
</div>
   
<br/>
   
<div align='center'>
 
   ![LOGO_ICON_](https://user-images.githubusercontent.com/31626353/130553716-1a807231-675e-4004-a2c2-83622cbf51eb.png)

   
</div>






