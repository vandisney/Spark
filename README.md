<img src="https://github.com/vandisney/Spark/blob/main/imagens/spark_logo.jpg" width="200"/>

#### Exercícios utilizando o Jupyter Notebook

#### ✍️ 1- Criar o arquivo do notebook com o nome teste_spark.ipynb .
  * Na tela do localhost:8889, vai no menu new e clicar em pyspark, já vem com a sessão e o contexto do spark criado, para renomear basta clicar em cima do title(untitled2).
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao.png"/> </p>
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao2.png"/>

#### ✍️ 2- Obter as informações da sessão de spark.
Para isso digite spark + (chift+enter), ele executa a celula e cria uma nova célula em baixo, nesta sessão tem um contexto, tem a interface gráfica, qual a versão e modo que está rodando.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao3.png"/>

#### ✍️ 3- Obter as informações do contexto do spark (sc).
Para isso digite sc + (ctrl+enter), a célula é executada, porém não é criado nova célula abaixo.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao4.png"/>

#### ✍️ 4- Setar o log como INFO.
Faz parte da sessão do spark, para isso digita spark.(+ tab).
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao5.png"/>

#### ✍️ 5 - Visualizar todos os banco de dados com o catalog.
Realizado através do comando: `spark.catalog.listDatabases()`, presiona tecla ctrl+enter.
Conforme a imagem, foi possível notar a configuração do hdfs em **locationUri**, ou seja, quando é salvo uma tabela no hive, automaticamente é salvo no hdfs também, por isso a importância de estar mapeado no catalog, e na hora de ler um dado também estará neste local.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao6.png"/>

#### ✍️ 6- Ler os dados "hdfs://namenode:8020/user/rodrigo/data/juros_selic/juros_selic.json“ com uso de Dataframe.
Para isso foi utilizado os comandos:
`leitura_juros = spark.read.json("hdfs://namenode:8020/user/vandisney/data/juros_selic/juros_selic.json")` </br>
`leitura_juros.show(5)`
 
 Como foi relatado na questão anterior que o caminho do hdfs já foi configurado,dessa forma, o hdfs já foi especificado como namenode usando a porta 8020, então posso retirar esse trecho `namenode:8020` do comando sem perda alguma de informação: `("hdfs:///user/vandisney/data/juros_selic/juros_selic.json")` bem como sem a palavra **hdfs** em:  `("/user/vandisney/data/juros_selic/juros_selic.json")`
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao7.png"/>

#### ✍️ 7- Salvar o Dataframe como juros no formato de tabela Hive.
Usado o comando `leitura_juros.write.saveAsTable("juros")`
 <img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao8.png"/>

#### ✍️ 8- Visualizar todas as tabelas com o catalog.
Criado através do comando: `spark.catalog.listTables()`
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao9.png"/>

#### ✍️ 9- Visualizar no hdfs o formato e compressão que está a tabela juros do Hive.
Executado através do comando: `!hdfs dfs -ls /user/hive/warehouse/juros`
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao10.png"/>

#### ✍️ 10- Ler e visualizar os dados da tabela juros, com uso de Dataframe no formato de Tabela Hive.
Visualizado através do comando: `spark.read.table("juros").show(5)`
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao11.png"/>

#### ✍️ 11- Ler e visualizar os dados da tabela juros , com uso de Dataframe no formato Parquet.
Para o formato Parquet é necessário fazer referência a todo o diretório sob o comando: `spark.read.parquet("/user/hive/warehouse/juros/").show(5)`
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao12.png"/>

