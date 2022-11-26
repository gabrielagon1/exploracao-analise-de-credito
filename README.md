 # EXPLORAÇÃO E ANÁLISE DE DADOS DE CRÉDITOS COM SQL
Este notebook faz parte do projeto desenvolvido no curso SQL para analise de dados da Escola Britânica de Artes Criativas & Tecnologia. O projeto foi realizado a partir das aulas sobre SQL que foram ministradas por Mariane Neiva.
Para a realização da presente análise, utilizamos o conjunto de dados disponibilizado no Github de André Perez. Como a tabela possuia mais de 10.000 linhas e nós utilizamos os serviços da AWS para criação da tabela, serviço este que tem um limite para utilização sem que seja necessário realizar algum pagamento.


# Dados utilizados:

Os dados apresentados são de clientes de um banco e apresentam as seguintes tabelas:

* idade = idade do cliente
* sexo = sexo do cliente (F ou M)
* dependentes = número de dependentes do cliente
* escolaridade = nível de escolaridade do clientes
* salario_anual = faixa salarial do cliente
* tipo_cartao = tipo de cartao do cliente
* qtd_produtos = quantidade de produtos comprados nos últimos 12 meses
* iteracoes_12m = quantidade de iterações/transacoes nos ultimos 12 meses
* meses_inativo_12m = quantidade de meses que o cliente ficou inativo
* limite_credito = limite de credito do cliente
* valor_transacoes_12m = valor das transações dos ultimos 12 meses
* qtd_transacoes_12m = quantidade de transacoes dos ultimos 12 meses

>A tabela foi criada no AWS Athena junto com o S3 Bucket com uma versão dos dados disponibilizados em: https://github.com/andre-marcos-perez/ebac-course-utils/tree/main/dataset


**Para começar, iremos descobrir qual é a quantidade de informações que estamos explorando base de dados:**

> Query: SELECT COUNT (*) as linhas FROM credito

![image.png](attachment:af53696c-fab7-47dc-a9ad-5782a697d6ea.png)

> É possível analisar que a resposta foi 2564 linhas, porém na base de dados que pode ser encontrada no link indicado, são econtrados mais linhas do que na resposta, já que não foram usadas todas, em razão de limites financeiros e computacionais.


**Como são os dados?**
> Query: SELECT * FROM credito LIMIT 7;

![image.png](attachment:3cf78c9a-30b6-46b7-ab90-e21197990fe3.png)
> Podemos observar que alguns dados ficaram nulos(na), vamos nos aprofundar.

**Quais são os tipos de cada dados?**
> Query: Describe credito;

![image.png](attachment:cbfdf229-df4e-49f9-b572-13beb59d02c1.png)
> Uma forma mais detalhada de visualizar quais são os tipos de dados que vamos analisar.

**Quais são os tipos de escolaridade disponíveis no dataset?**
> Query: SELECT DISTINCT escolaridade FROM credito

![image.png](attachment:8557ba26-ee46-4539-8669-610fd3415cc4.png)

> Com a visualização do gráfico pizza criado no google sheets, podemos observar que existe nulo(na) nos valores de escolaridade.

**Quais são os tipos de salario_anual disponíveis no dataset?**
> Query: SELECT DISTINCT salario_anual FROM credito

![image.png](attachment:cba09206-79cb-47b7-9684-b470dbb51c62.png)

> No resultado da query é possível identificar valores nulos 

**Quais são os tipos cartões utilizados?**
> Query: SELECT DISTINCT tipo_cartao FROM credito

![image.png](attachment:2af8a4f8-8f81-4201-9d02-85cfb52e76ef.png)
> O resultado mostra os tipos de cartões que podem ser encontrados no banco.

**Quais são os tipos de estado_civil disponíveis no dataset?**
> Query: SELECT DISTINCT estado_civil FROM credito

![image.png](attachment:3bebd543-46c6-4253-838c-a1540b6b3e6c.png)

> Nos valores encontrados no estado civil dos clientes, é possível visualizar um valor nulo(na).
