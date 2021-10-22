# DIO-LiveCoding-AWS-BigData
Repositório de cógido do Dio Live Coding com AWS EMR e Python
Neste repositório há os arquivos de configuração e execução de análise de dados.

## Instruções

* Acessar S3: https://s3.console.aws.amazon.com/s3/ 
  * Criar estrutura de data lake : _dio-live-datalake_
  * Criar estrutura de pastas:
    * _data_
    * _output_
    * _temp_
* Acessar EMR: https://console.aws.amazon.com/elasticmapreduce/
    * O cluster será criado pelo MrJob e não pelo console
    * Infraestrutura como código 
* Criar chave SSH
    * Acessar  Console do EC2: https://console.aws.amazon.com/ec2/ -> Key Pairs -> Create Key Pair	
    * Download .pem file
* Obter Id e chave secreta AWS para configurar MrJob
   * Profile
   * My Security Credentials: https://console.aws.amazon.com/iam/home?region={region}#/security_credentials
   * Access Keys - Create new access key
   * Fazer download - única chance de visualizar
* Ambiente linux
   * Criar ambiente virtual python: _virtualenv --python=python3.6 venv_diolive_
   * Acessar com o vs code
* Instalar vscode no Ubuntu
   *  code .
* Criar algoritmo de análise de palavras
   * dio-live-wordcount-test.py
   * map-reduce-count : contar
   * Instalar boto3: _pip install boto3_
   * Instalar mrjob: _pip install mrjob_
* Acessar S3
   * Upload de arquivo para o bucket
* Ambiente virtual python: source venv_teste/bin/activate
  * _nano ~/.mrjob.conf_
  * _python3 dio-live-wordcount-test.py -r emr s3://{your_s3_bucket_name}/data/SherlockHolmes.txt --output-dir=s3://{your_s3_bucket_name}/output/logs1 --cloud-tmp-dir=s3://{your_s3_bucket_name}/temp/_





Resultado do processamento



python3 dio-live-wordcount-test.py -r emr s3://dio-live-datalake-ademar/data/SherlockHolmes.txt --output-dir=s3://dio-live-datalake-ademar/output/logs1 --cloud-tmp-dir=s3://dio-live-datalake-ademar/temp/
Using configs in /home/lacan/.mrjob.conf
Creating temp directory /tmp/dio-live-wordcount-test.lacan.20211022.195547.480219
uploading working dir files to s3://dio-live-datalake-ademar/temp/dio-live-wordcount-test.lacan.20211022.195547.480219/files/wd...
Copying other local files to s3://dio-live-datalake-ademar/temp/dio-live-wordcount-test.lacan.20211022.195547.480219/files/
Created new cluster j-31851IXBDOSRJ
Added EMR tags to cluster j-31851IXBDOSRJ: __mrjob_label=dio-live-wordcount-test, __mrjob_owner=lacan, __mrjob_version=0.7.4
Waiting for Step 1 of 2 (s-2WQFWTWZQUAEP) to complete...
  PENDING (cluster is STARTING)
  PENDING (cluster is STARTING)
  PENDING (cluster is STARTING)
  PENDING (cluster is STARTING: Configuring cluster software)
  PENDING (cluster is STARTING: Configuring cluster software)
  PENDING (cluster is STARTING: Configuring cluster software)
  PENDING (cluster is STARTING: Configuring cluster software)
  PENDING (cluster is STARTING: Configuring cluster software)
  master node is ec2-15-228-37-183.sa-east-1.compute.amazonaws.com
  Connect to resource manager at: http://localhost:40728/cluster
  PENDING (cluster is RUNNING: Running step)
  RUNNING for 0:00:51
  COMPLETED
Attempting to fetch counters from logs...
Looking for step log in /mnt/var/log/hadoop/steps/s-2WQFWTWZQUAEP on ec2-15-228-37-183.sa-east-1.compute.amazonaws.com...
Looking for step log in s3://dio-live-datalake-ademar/temp/logs/j-31851IXBDOSRJ/steps/s-2WQFWTWZQUAEP...
  Parsing step log: s3://dio-live-datalake-ademar/temp/logs/j-31851IXBDOSRJ/steps/s-2WQFWTWZQUAEP/syslog.gz
Counters: 60
        File Input Format Counters
                Bytes Read=634108
        File Output Format Counters
                Bytes Written=99128
        File System Counters
                FILE: Number of bytes read=128354
                FILE: Number of bytes written=4494509
                FILE: Number of large read operations=0
                FILE: Number of read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1260
                HDFS: Number of bytes read erasure-coded=0
                HDFS: Number of bytes written=99128
                HDFS: Number of large read operations=0
                HDFS: Number of read operations=49
                HDFS: Number of write operations=10
                S3: Number of bytes read=634108
                S3: Number of bytes written=0
                S3: Number of large read operations=0
                S3: Number of read operations=0
                S3: Number of write operations=0
        Job Counters
                Data-local map tasks=12
                Killed reduce tasks=1
                Launched map tasks=12
                Launched reduce tasks=5
                Total megabyte-milliseconds taken by all map tasks=533993472
                Total megabyte-milliseconds taken by all reduce tasks=111790080
                Total time spent by all map tasks (ms)=173826
                Total time spent by all maps in occupied slots (ms)=16687296
                Total time spent by all reduce tasks (ms)=18195
                Total time spent by all reduces in occupied slots (ms)=3493440
                Total vcore-milliseconds taken by all map tasks=173826
                Total vcore-milliseconds taken by all reduce tasks=18195
        Map-Reduce Framework
                CPU time spent (ms)=76620
                Combine input records=0
                Combine output records=0
                Failed Shuffles=0
                GC time elapsed (ms)=3826
                Input split bytes=1260
                Map input records=12303
                Map output bytes=993515
                Map output materialized bytes=253575
                Map output records=109168
                Merged Map outputs=60
                Peak Map Physical memory (bytes)=707395584
                Peak Map Virtual memory (bytes)=4492111872
                Peak Reduce Physical memory (bytes)=275038208
                Peak Reduce Virtual memory (bytes)=7096086528
                Physical memory (bytes) snapshot=8639803392
                Reduce input groups=8190
                Reduce input records=109168
                Reduce output records=8190
                Reduce shuffle bytes=253575
                Shuffled Maps =60
                Spilled Records=218336
                Total committed heap usage (bytes)=8392278016
                Virtual memory (bytes) snapshot=88978157568
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
Terminating cluster: j-31851IXBDOSRJ





