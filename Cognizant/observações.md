## Consegui realizar a atividade de duas formas diferentes:


### Método 1 -

No script python disponibilizado, tem duas tarefas principais, contar as palavras e depois classificar a contagem.

Como o pacote botocore está depreciado, por isso, o scritp não conseguia executar a "segunda" tarefa e finaliza com erro.

Para concluir o exercício com as duas etapas, tive que criar um cluster EMR manualmente e passar o cluster-id como parâmetro.

Comando de entrada:

python3 dio-live-wordcount-test_2.py -r emr -c /home/ubuntu/environments/mrjob.conf --cluster-id "j-10IBSZ6FUKTHH" s3://estudo-dio/data/sherlock.txt --output-dir=s3://estudo-dio/output/log-01 --cloud-tmp-dir=s3://estudo-dio/temp/



### Método 2 - 
Como o próprio professor informa nas aulas, o script python está apresentando erro quando tentar classificar a contagem, nesse caso deve-se apagar/ comentar a seguinte linha de comando do arquivo .py

MRStep(mapper = self.mapper_make_counts_key, reducer = self.reducer_output_words)


Para executar apenas uma tarefa, não precisa criar o cluster EMR manualmente.

Comando de entrada:

python3 dio-live-wordcount-test_1.py -r emr -c /home/ubuntu/environments/mrjob.conf s3://estudo-dio/data/sherlock.txt --output-dir=s3://estudo-dio/output/log-02 --cloud-tmp-dir=s3://estudo-dio/temp/


