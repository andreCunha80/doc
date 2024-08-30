
Executar os comandos que estão entre as linhas ===== de cada vez

Antes de iniciar, siga as instruções em Verifique as Permissões do Projeto.



++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

TASK 1 - 

======================================

bq mk lab_408

======================================

gsutil mb gs://qwiklabs-gcp-03-b883de343bb2-marking

======================================

gsutil cp gs://cloud-training/gsp323/lab.csv  .
gsutil cp gs://cloud-training/gsp323/lab.schema .
cat lab.schema

======================================

Copie o BigQuery Schema, somente entre colchetes, com colchetes inclusos.

Abra o BigQuery - clique nos 3 pontos ao lado do Dataset e clique em Create table.

Em Source -> Google Cloud Storage.
Abaixo, em Select file from GCS ... copie o caminho após Text Files on Cloud Storage to Big Query. 
Não inclua o gs://. O caminho deve ser cloud-training/gsp323/lab.csv
File format deve mudar para csv
Em Table, copiar o ultimo nome da tabela BigQuery output table. Exemplo: customers_876
Em Schema, selecionar Edit as text (mover o seletor para a diteita).
No campo de texto colar o Schema copiado anteriormente.
Clicar em Create Table

Abrir o DataFlow 

Clicar +Create Job From Templete

Job Name : Qualquer nome

Regional endpoint: Conforme o seu Lab.

Dataflow template: Text Files on Cloud Storage to BigQuery (Bach)

Preencher os campos Required Parameters conforme a tabela.

Clicar em Optional Parameters, rolar a página para baixo e desmarcar Use default machine type.

Em Series selecionar E2

Em Machine type e2 - standard 2

Clicar em Run Job

Esperar +/- 5 min

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

TASK 2

No Painel de navegação, ir para Dataproc.

Clique em +CREATE CLUSTER e depois selecione Cluster on Compute Engine

Deixe o nome padrão.
Escolher a região, conforme o seu lab.

Clique em Configure nodes a esquerda.

Selecione Series E2

Machine Type e2-standard 2

Primary disk size 100GB

Repetir para Woeker nodes

Número de Worker Nodes: 2

Desmarcar opção somente IP interno

Clique em CREATE a esquerda.

Aguarde o Status estar em Running.

Clique no cluster, e em seguida em VM INSTANCES.

Na instância Master, clique em SSH. (Espere habilitar).

Copie o comando hdfs que está no texto da task 2. Termina com data.txt

Clique em Jobs e submit a Job.

Preencha os dados com os valores da tabela da Task 2.

Clique em Submit

Aguarde o Status Succeeded


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Task 3 e 4

Criar uma API Key

1- No Console, clique Navigation menu > APIs & services > Credentials.

2 - Clique em  Create credentials.

3 - No menu drop down, selecione  API key.

4 -Copie a chave gerada no bloco de notas e Clique em Close.

5 - Preencha as variáveis abaixo.:

====================================================

export API_KEY=AIzaSyArHMwNjU6Y5Ax8WaWWDnp50R-qeOkPDmY

export BUCKET_TASK3=gs://qwiklabs-gcp-03-b883de343bb2-marking/task3-gcs-134.result

export BUCKET_TASK4=gs://qwiklabs-gcp-03-b883de343bb2-marking/task4-cnl-729.result

====================================================

6 - Crie o arquivo request.json: Confira o nome do arquivo FLAC
======================================================

cat > request.json <<EOF 
{
  "config": {
      "encoding":"FLAC",
      "languageCode": "en-US"
  },
  "audio": {
      "uri":"gs://cloud-training/gsp323/task3.flac"
  }
}
EOF

=======================================================


7- Envie a solicitação para a API

======================================================

curl -s -X POST -H "Content-Type: application/json" --data-binary @request.json \
"https://speech.googleapis.com/v1/speech:recognize?key=${API_KEY}"

=======================================================

8 - Verifique se há uma resposta válida.

9 - Salve a resposta num arquivo result.json

=======================================================

curl -s -X POST -H "Content-Type: application/json" --data-binary @request.json \
"https://speech.googleapis.com/v1/speech:recognize?key=${API_KEY}" > result.json

=======================================================

10 - Salve o arquivo no local especificado pela Task:

=======================================================

gsutil cp result.json $BUCKET_TASK3

======================================================

11-
======================================================

export GOOGLE_CLOUD_PROJECT=$(gcloud config get-value core/project)

======================================================

12-Criar uma conta para usar a API natural language
=========================================================

gcloud iam service-accounts create my-natlang-sa \
  --display-name "my natural language service account"

=========================================================

13-Cria as credenciais de acesso.

=========================================================

gcloud iam service-accounts keys create ~/key.json \
  --iam-account my-natlang-sa@${GOOGLE_CLOUD_PROJECT}.iam.gserviceaccount.com

================================================================

14- Remete a solicitação para a API

===================================================================

export GOOGLE_APPLICATION_CREDENTIALS="/home/USER/key.json"
gcloud auth activate-service-account my-natlang-sa@${GOOGLE_CLOUD_PROJECT}.iam.gserviceaccount.com --key-file=$GOOGLE_APPLICATION_CREDENTIALS
gcloud ml language analyze-entities --content="Old Norse texts portray Odin as one-eyed and long-bearded, frequently wielding a spear named Gungnir and wearing a cloak and a broad hat." > result.json
gcloud auth login --no-launch-browser

==================================================================

15- 	Quando solicitado clique y
	Clique no linque https:// 
	Na página do SDK, role para baixo e clique em Allow
	Clique em copy.
	Retorne ao shell e cole. Pressione enter.
===================================================================

16 - gsutil cp result.json $BUCKET_TASK4
===================================================================
	