# DIO-PROJETO-BIG-DATA-AWS


### Serviços utilizados nessa atividade prática
 - Amazon S3
 - Amazon Glue
 - Amazon Athena
 - Amazon QuickSight

### Etapas para desenvolvimento

### Criar bucket no Amazon S3

- Amazon S3 Console -> Buckets -> Create bucket -> Bucket name [nome_do bucket] - Create bucket
- Create folder (Criar uma pasta chamada ```/output``` e outra com o nome do seu conjunto de dados. Este nome irá definir o nome da tabela criada no Glue)
- Upload dos arquivos de dados localizados na pasta ```/data```

#### Criar Glue Crawler

- Amazon Glue Console -> Crawlers -> Add Crawler
- Source type [Data Stores] -> Crawl all folders
- Data store [S3] -> Include path [caminho do diretório dos dados de entrada]
- Create IAM Role
- Frequency [Run on demand]
- Database name [seu_nome_de_db]
- Group behavior [Create a single schema for each S3 path]
- Finish
- Databases -> Tables -> Visualizar dados das tabelas criadas
![image](https://user-images.githubusercontent.com/33034037/200661029-05445bd0-1e49-4ba2-9bc1-58381dd64433.png)
![image](https://user-images.githubusercontent.com/33034037/200661124-eb860a31-42d9-4c96-b5d0-9f0c344e41ab.png)


### Criar aplicação no Amazon Athena

- Query editor -> Settings -> Manage settings -> Query result location and encryption -> Browse S3 -> selecionar o bucket criado
- Selecionar Database -> criar queries (exemplos na pasta ```/src```)
- Verificar queries não salvas no bucket criado no S3
- Salavar queries -> Executar novamente -> Verificar no bucket criado no S3
-![image](https://user-images.githubusercontent.com/33034037/200660750-736bf4de-cf45-4045-8f9a-700aa0c25df4.png)

![image](https://user-images.githubusercontent.com/33034037/200661368-4d2ca169-42e7-4394-8743-cb15431a4db3.png)

#### Criando nova tabela

- Generate table DDL
- Copiar a query gerada
- Selecionar o DB e criar a nova tabela em uma nova query
![image](https://user-images.githubusercontent.com/33034037/200661245-fb725797-9033-40a8-9956-c4ba6dc4b7f0.png)

### Visualizar dados no Amazon QuickSight

- Signup (caso não tenha conta) -> Escolher [Standard]
- Datasets -> Create new dataset -> Athena -> Name [NomeDoDataSet] -> Create
- Select database -> select table -> Edit or preview -> Save & visualize
- Criar visualizações selecionando colunas, criando filtros e parâmetros e selecionando Visual types para gráficos.
![image](https://user-images.githubusercontent.com/33034037/200661435-333cbec6-e2b4-48cb-8a75-7a55a4777e2c.png)

### Eliminar recursos
 - Exluir os elementos criados

