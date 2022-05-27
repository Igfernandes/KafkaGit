## KAFKA INSTALAÇÃO:

- Baixar a versão binária mais recente do Kafka. 
- Modificar o caminho de logs no kafka dentro de "Kafka/config/server.properties". Alterar variavel: log.dirs= 
- Modificar o caminho do zookeeper no kafka dentro de "Kafka/config/zookeeper.properties". Alterar variavel: dataDir= 
- O kafka só interpreta até duas paths de profundidade seguindo o disco como ponto de partida.

*Instalando Zookeeper*
@Comand Line: .\bin\windows\zookeeper-server-start.bat config\zookeeper.properties
-> Ele sozinho irá criar a pasta "zookeeper"


- Abra um novo terminal e agora execute a linha de comando para fazer o kafka iniciar.
*Configurando o Kafka*
@Comand Line: .\bin\windows\kafka-server-start.bat .\config\server.properties
-> Ele sozinho irá criar a pasta "Kafka-logs"



## KAFKA ATALHOS:
@repositorie: <https://github.com/bstashchuk/apache-kafka-course>


-> .\bin\windows\kafka-topics.bat [ Trazer as opções disponíveis no kafka]


-> .\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --topic cities.
$Obers: Você pode utilizar o "--bootstrap-server" para executar algo pelo kafka ou o "--zookeeper" para executar pelo próprio zookeeper.
$Obser¹: Após o host é informado o que você deseja criar. 
$Obser²: A ação da linha de comando sempre vem posteriormente ao caminho do arquivo raiz, igual ao "--create" ;


-> bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092

$Obser: Server para listar os topicos.



-> bin\windows\kafka-topics.bat --describe --bootstrap-server localhost:9092 --topic <topico_nome>

$Obser: Server para listar as propriedades desse topico.



-> bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic <topico_nome>

$Obser: Server para armazenar informações dentro dos topicos e criar automaticamente os brokers.



-> bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092

$Obser: Serve para testar a solicitação de um tópico, que estará escutando em tempo real.



-> bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic cities --from-beginning

$Obser: Lista as informações do tópico que foram consumidas.



-> bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092

$Obser: Serve para testar a solicitação de um tópico, que estará escutando em tempo real.



-> bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic cities --from-beginning

$Obser: Lista as informações do tópico que foram consumidas.





===================================================================================================
===================================================================================================

## ERRORS:


$ ERROR Fatal error during KafkaServer startup. Prepare to shutdown (kafka.server.KafkaServer)

(Solução*): Apague tudo dentro da pasta do "kafka-log" e do "zookeeper\version-2"


---//----------------------//---------------//----------------


$  zookeeper is not a recognized option

(Solução*): Ele não está reconhecendo o comando. Utilize o "--bootstrap-server" no lugar.
(Explicação): Versões mais recentes (2.2 e acima) do Kafka não requerem mais a string de conexão do ZooKeeper, ou seja, --zookeeper localhost:2181 e lançam Exception no thread "main". <font:https://codedaily.in/zookeeper-is-not-a-recognized-option/>