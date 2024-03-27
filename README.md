
# 🏦Churn Analysis - Bank Customer Churn Dataset

Neste projeto será realizado o processo de EDA (Exploratory Data Analysis) com foco na análise de Churn a partir do datas ser Bank Customer Churn Dataset, que pode ser encontrado no [Kaggle](https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset) e disponibilizado por [Gaurav Topre](https://www.kaggle.com/gauravtopre).

### 🛠️ Ferramentas utilizadas
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## 1.1. Os dados, o problema e os objetivos
### O que é Churn?

Churn pode ser traduzido de maneira livre, como a taxa de perda de clientes ao longo do tempo. É uma métrica importante para setores onde a rentabilidade depende da recorrência da compra de produtos ou renovação de serviços, como em imobiliárias focadas em aluguel, planos de assinatura em geral, entre outros. No setor bancário está perda de clientes pode ser considerada a partir de vários aspectos além do encerramento da conta como:

- Inatividade alongada;
- Redução das atividades;
- Portabilidade do crédito para outros bancos.

Portando é importante entender o que está levando os consumidores a deixar o seu serviço, para corrigir estes pontos e aumentar a retenção. Em um setor com alta concorrência e uma variedade infidável de opções como o bancário, especialmente após a explosão das fintechs, ter este controle e processos de melhoria constante da prestação de serviços é uma das chaves para a longevidade. 

### Estrutura do dataset
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

### Objetivos
Portando meu objetivo nesta análise será:
- Entender o perfil dos clientes do Banco ABC;
- Buscar entender quem está deixando o banco e o porque. 

## 1.2. Importação das bibliotecas e carregamento dos dados
A bibliotecas utilizadas foram o pandas, numpy, matplotlib, seaborn e plotly.

# 🧱2. Entendendo os dados 
Aqui busquei através do métodos shape, head(), tail(), e info() para entender a estrutura dos dados. 
# 🧹3. Limpeza e manipulação dos dados
## 3.1. Verificação de nulos e duplicados
Verificação através dos métodos isna() e duplicated(). E constado que não seriam necessários outros processos de limpeza e manipulação.

# 🔍4. Análise Exploratória de Dados
## 4.1. Os clientes
### Perfil demográfico
![Imagem1](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_1.png?raw=true)
![Imagem2](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_2.png?raw=true)
![Imagem3](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_3.png?raw=true)
- Metade dos clientes do Banco ABC são residentes da França, o restante está dividido entre Alemanha e Espanha.
- Mais da metade dos clientes são homens.
- Os clientes tem idades variando entre 18 e 90 anos de idade, a grande massa está entre 20 e 50 anos.
### Perfil financeiro
![Imagem4](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_4.png?raw=true)
![Imagem5](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_5.png?raw=true)
![Imagem6](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_6.png?raw=true)
- O banco tem diversos clientes com altos valores de score de crédito, é importante checar se estes estão entre aqueles que encerraram o relacionamento. Pessoas com crédito alto tem potencial de contratar produtos de valor elevado como empréstimos de grandes valores, financiamentos imobiliários e outros investimentos.
- Existe uma quantidade elevada de pessoas com contas zeradas, é necessário investigar a relação entre estes e o Churn.
- O salário estimado não parece ser confiável, já que existem pessoas com altos saldos em conta e salário estimado incompatível.
### Relacionamento com o banco
![Imagem7](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_7.png?raw=true)
![Imagem8](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_8.png?raw=true)
![Imagem9](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_9.png?raw=true)
![Imagem10](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_10.png?raw=true)
- A grande massa dos clientes está entre 2 à 6 anos contando com os serviços do Banco ABC.
- Entre eles poucos tem mais de 2 serviços contratados, o que deve ser melhorado e pode estar ligado ao Churn.
- 70% deles tem o serviço de cartão de crédito contratado.
- 20% dos clientes deixaram o banco, é uma taxa altíssima e a seguir vamos buscar investigar o perfil destes clientes.
## 4.2. Quem está deixando o Banco ABC?
![Imagem11](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_11.png?raw=true)
![Imagem12](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_12.png?raw=true)
- O maior número de clientes que deixaram o banco está na Alemanha, que corresponde somente a cerca de 25% da base clientes. França é onde está metade da base de clientes, é esperado que boa parte dos número venham de lá mas precisamos buscar soluções para diminuir o Churn em relação à alemães.
- Apesar de mais da metade dos clientes do banco serem do sexo masculino, são mulheres quem mais abandonou o banco é necessário investigar as razões para isso.

![Imagem13](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_13.png?raw=true)
![Imagem14](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_14.png?raw=true)
![Imagem15](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_15.png?raw=true)
![Imagem16](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_16.png?raw=true)
![Imagem17](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_17.png?raw=true)
- Pessoas que estão deixando o banco tem uma média maior de dinheiro em conta, isso é preocupanete pois além de maior saldo estes clientes tem bom score de crédito ou seja, tem potencial parar contratar produtos e realizar investimento de alto valor.
- Estes clientes também tem uma média de idade e de tempo de relacionamento com o banco maiores, o que direciona o problema para o atendimento à pessoas mais velhas.
- A margem de clientes com zero dinheiro em conta que abandonou a empresa é baixa, estes devem também ser trabalhados para trazer seu dinheiro para o Banco ABC e contratar seus produtos.
![Imagem18](https://github.com/datalopes1/bankabc_churn/blob/main/data/img/plot_18.png?raw=true)
O fator de correlação mais forte de acordo com a matriz, é a idade apontando novamente a necessidade de atenção com clientes mais velhos.

# ✅5. Conclusões
![Image](https://images.unsplash.com/photo-1509470475192-4516c145f8a1?q=80&w=2071&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)

**N**o setor bancário medir a taxa de perda de clientes, também é medir a saúde do negócio. Bancos dependem da movimentação financeira constante e da confiança de seus clientes, com tantas opções e facilidades de abertura de contas existem pequenos detalhes como uma instabilidade no aplicativo do banco ou demora em um atendimento, levam pessoas a buscarem outras instituições. Com a digitalização cada vez maior do mercado financeiro, o surgimento das fintechs e outras mudanças, algumas pessoas não necessariamente irão conseguir acompanhar este ritmo. Nesta análise conseguir extrair os seguintes insights e pontos de melhora:

- Os clientes de idade avançada, com maior saldo em conta e mais tempo de relacionamento estão entre aqueles que mais estão abandonando os serviços do Banco ABC, o fator idade é o mais importante e portando é necessário buscar melhorar o atendimento aos mais velhos;
- Mulheres são a maioria entre estes clientes então melhorar o atendimento a esse público também é de suma importância;
- É preciso também buscar as razões para a taxa ser tão alta entre os alemães, buscar entender se fatores culturais na forma de atendimento e prestação de serviços é onde o Banco ABC está falhando;
- Acredito que o setor de marketing e gestão de relacionamento deve procurar meios de incentivar clientes com saldo em conta zerado a trazerem seu dinheiro para o Banco ABC;
- A forma como os salários são estimados deve ser melhorada para análises futuras.