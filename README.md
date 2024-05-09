# Análise Exploratória de Dados - Bank Customer Churn Dataset 🏦

Neste projeto será realizada o processo de EDA (Exploratory Data Analysis) a partir do dataset Bank Customer Churn Dataset para identificar o perfil dos clientes que deixam o Banco ABC. Os dados podem sem encontrados no [Kaggle](https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset) e foram disponibilizados por [Gaurav Topre](https://www.kaggle.com/gauravtopre).

![img](https://camo.githubusercontent.com/f2876e4f08d9724a788438fe307745ca90c1701c464c5f1e7575837bd0e1837a/68747470733a2f2f696d616765732e756e73706c6173682e636f6d2f70686f746f2d313630373934343032343036302d3034353033383064646433333f713d383026773d31393332266175746f3d666f726d6174266669743d63726f702669786c69623d72622d342e302e3326697869643d4d3377784d6a4133664442384d48787761473930627931775957646c664878386647567566444238664878386641253344253344)

### Objetivos e resultados
O objetivo nessa análise é buscar o perfil dos clientes do Banco ABC que estão deixando seus serviços bancários. Consegui encontrar o perfil dos clientes a partir de fatores demográficos e financeiros.

### 🛠️ Ferramentas utilizadas
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
## Estrutura do Dataset
Os dados tratam de um banco que presta serviços internacionalmente em países europeus, e tem as seguintes colunas:
|Coluna|Descrição|
|-----|-----|
|**costumer_id**|ID do Cliente|
|**credit_score**|Score de crédito|
|**country**|País onde o cliente reside|
|**gender**|Gênero|
|**age**|Idade|
|**tenure**|Tempo de relacionamento com o banco|
|**balance**|Balanço em conta|
|**products_number**|Número de produtos contratados|
|**credit_card**|Possui cartão de crédito (booleano)|
|**active_member**|Cliente ativo (booleano)|
|**estimated_salary**|Salário estimado|
|**churn**|Churn (booleano)|

## Bibliotecas Python utilizadas
#### Manipulação de dados
- Pandas, Numpy.
#### EDA
- Seaborn, Matplotlib.
# Análise Exploratória de Dados
## Perfil dos clientes
### País
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot1.png?raw=true)
#### Sobre os país de residência
Cerca de 50% dos clientes são residentes da França, o restante esta dividida de forma bastante proporcional entre Alemanha e Espanha.
### Gênero
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot2.png?raw=true)
#### Sobre o genêro
Existe uma distribuição bastante equilibrada entre clientes homens e mulheres.
### Idade
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot3.png?raw=true)

![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot4.png?raw=true)
#### Sobre a Idade
A maior parcela de clientes do banco está entre seus 30 e 50 anos. Existe uma assimétria a direita na distribuição, causada pela existência de alguns clientes de idade mais avançada na base de dados.
### Score de crédito
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot5.png?raw=true)

![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot6.png?raw=true)
#### Sobre o Score de Crédito
Maioria dos clientes tem um score de crédito entre 500 e 800 o que mostra uma boa condição para aquisição de produtos bancários.

### Tempo de relacionamento
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot7.png?raw=true)

### Balanço em conta
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot8.png?raw=true)
#### Sobre o Balanço em Conta
Existe uma grande quantidade de clientes com balanço zero em conta, vamos isolar estes dados para buscar relações entre o balanço zero e a possibilidade ou não de churn. Vamos observar de maneira isolada somente os clientes com clientes de saldo positivo.

![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot9.png?raw=true)

Estes clientes tem um saldo consideravel em conta, a maioria com balanço entre 80.000 e 160.000. É uma distribuição muito próxima à normal.
### Produtos Contratados
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot10.png?raw=true)

#### Sobre os Produtos Contratados
Mais de 90% dos clientes tem somente dois produtos contratados, um deles o cartão de crédito, o qual vamos conferir na próxima etapa.
### Cartão de Crédito
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot11.png?raw=true)

#### Sobre o Cartão de Crédito
Cerca de 70% dos clientes contam com serviço de cartão de crédito.
## Quem está abandonando os serviços do Banco ABC?
### Por país
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot12.png?raw=true)
#### Sobre o País de Residência
Apesar de conter apenas 25% da base de clientes a Alemanha conta com aproximadamente 40% dos clientes que estão em ponto de deixar os serviços do Banco ABC, é necessário investigar o que está acontecendo na prestação de serviços nas agências alemãs. França e Espanha mostra um padrão "normal" de acordo com a quantidade de contratantes em cada país mas precisam também de ações contudentes para diminuir o churn.
### Por Gênero
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot13.png?raw=true)

#### Sobre o Gênero
Apesar de homens serem a maioria na base de clientes (54%), mulheres são quase 56% dos casos de churn, vejo a necessidade de rever a qualidade do atendimento ao público feminino.
### Por Idade
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot14.png?raw=true)
#### Sobre a Idade
Os clientes em ponto de churn tem idade mais avançada, estão entre 40 e 50 anos de idade. Isso demonstra a necessidade também de melhora de atendimento.
### Por Score de Crédito
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot15.png?raw=true)
#### Sobre o Score de Crédito
Os clientes que estão em ponto de churn tem um bom score de crédito.
### Por Tempo de relacionamento
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot16.png?raw=true)
#### Sobre o Tempo de Relacionamento
Os clientes em ponto de churn estão tem entre 2 e 8 anos de relacionamento com o Banco ABC. Um ponto especial de atenção é o terceiro e quinto ano de relação.
### Por Balanço
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot17.png?raw=true)

Vamos remover a influência dos clientes com conta zerada.

![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot18.png?raw=true)

Entre os clientes com balanço positivo, os que estão em ponto de churn tem um bom saldo em conta.

![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot19.png?raw=true)

Já entre os clientes com saldo zerado 86% não estão em ponto de churn.

### Por Produtos Contratados
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot20.png?raw=true)
#### Sobre os Produtos Contratados
Cerca de 70% dos clientes em ponto de churn tem apenas um produto contratado, acredito que o cartão de crédito.
### A Matriz de Correlação
![img](https://github.com/datalopes1/bankabc_churn/blob/main/doc/img/plot21.png?raw=true)

## Conclusões
No setor bancário medir a taxa de perda de clientes, também é medir a saúde do negócio. Bancos dependem da movimentação financeira constante e da confiança de seus clientes, com tantas opções e facilidades de abertura de contas existem pequenos detalhes como uma instabilidade no aplicativo do banco ou demora em um atendimento, levam pessoas a buscarem outras instituições. Com a digitalização cada vez maior do mercado financeiro, o surgimento das fintechs e outras mudanças, algumas pessoas não necessariamente irão conseguir acompanhar este ritmo.

### Insights
- Os clientes de idade avançada, com maior saldo em conta e mais tempo de relacionamento estão entre aqueles que mais estão abandonando os serviços do Banco ABC, o fator idade é o mais importante e portando é necessário buscar melhorar o atendimento aos mais velhos;
- Mulheres são a maioria entre estes clientes então melhorar o atendimento a esse público também é de suma importância;
- É preciso também buscar as razões para a taxa ser tão alta entre os alemães, buscar entender se fatores culturais na forma de atendimento e prestação de serviços é onde o Banco ABC está falhando;
- Acredito que o setor de marketing e gestão de relacionamento deve procurar meios de incentivar clientes com saldo em conta zerado a trazerem seu dinheiro para o Banco ABC;
- A forma como os salários são estimados e a atividade é determinada deve ser melhorada para análises futuras.

![img](https://camo.githubusercontent.com/5b5768e14b6bf1a3b205e066c672d3e6920da1a566cc89e35a285b9c5e4ef38c/68747470733a2f2f696d616765732e756e73706c6173682e636f6d2f70686f746f2d313530393437303437353139322d3435313663313435663861313f713d383026773d32303731266175746f3d666f726d6174266669743d63726f702669786c69623d72622d342e302e3326697869643d4d3377784d6a4133664442384d48787761473930627931775957646c664878386647567566444238664878386641253344253344)
