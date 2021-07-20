<img src="https://github.com/vandisney/Spark/blob/main/imagens/spark_logo.jpg" width="200"/>

Exercícios – Testar o Jupyter Notebook

1. Criar o arquivo do notebook com o nome teste_spark.ipynb

new, clicar em pyspark, já vem com a sessão(explicar) e o contexto de spark(explicar) criado.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao.png"/> </p>
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao2.png"/>

2. Obter as informações da sessão de spark (spark)

precionando spark + (chift+enter)do teclado, ele executa a celula e cria uma nova célula em baixo.
nessa sessão do spark tem um contexto, tem a interface grafica, qual a versão e modo que está rodando.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao3.png"/>

3. Obter as informações do contexto do spark (sc)
Digita sc + (ctrl+enter), executa porém não é criado nova célula.


4. Setar o log como INFO.
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao4.png"/>
faz parte da sessão do spark, para isso digita spark. (+ tab)
 <img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao5.png"/>

5. Visualizar todos os banco de dados com o catalog
realizado atrvés do comando: 'spark.catalog.listDatabases()', presiona tecla ctrl+enter.
Conforme a imagem, foi possível notar a configuração do hdfs em locationUri, ou seja, se é salvo uma tabela no hive automaticamente é salvo no hdfs também, por isso a importância de estar mapeado no catalog, e na hora de ler um dado gambém estará neste local
<img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao6.png"/>

6. Ler os dados "hdfs://namenode:8020/user/rodrigo/data/juros_selic/juros_selic.json“ com uso de Dataframe
 para isso usei o comando:
 'leitura_juros = spark.read.json("hdfs://namenode:2020/user/vandisney/data/juros_selic/juros_selic.json")'
 'leitura_juros.show(5)'
 
 Como foi relatado na questão anterior que o caminho do hdfs já foi configurado,dessa forma, o hdfs já foi especificado como namenode usando a porta 8020, então posso retirar esse trecho do comando sem perda alguma como em: '("hdfs:///user/vandisney/data/juros_selic/juros_selic.json")' ou sem a palavra hdfs ("/user/vandisney/data/juros_selic/juros_selic.json")'
 
 <img src="https://github.com/vandisney/Spark/blob/main/imagens/sessao7.png"/>


7. Salvar o Dataframe como juros no formato de tabela Hive

8. Visualizar todas as tabelas com o catalog

9. Visualizar no hdfs o formato e compressão que está a tabela juros do Hive

10. Ler e visualizar os dados da tabela juros, com uso de Dataframe no formato de Tabela Hive

11. Ler e visualizar os dados da tabela juros , com uso de Dataframe no formato Parquet

12. Clicar no botão de Enviar Tarefa, e enviar o texto: ok
