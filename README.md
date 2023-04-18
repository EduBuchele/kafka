# kafka
Estudando kafka via wsl2 no Windows:

- Subir o docker no wsl:

service docker start;

- Subir kafka via docker-compose:

docker-compose up -d

- validar se aplicação subiu:
docker ps;
docker logs kafka_kafka_1;

- Acessar kafka:
docker exec -it kafka_kafka_1 bash

Kafka linha de comando: 
- kafka-topics (help)
- Criando topic 
kafka-topics --create --topic=teste --bootstrap-server=localhost:9092 --partitions=3

- Apresentando topic criado
kafka-topics --list --bootstrap-server=localhost:9092

- Detalhando o topic
kafka-topics --bootstrap-server=localhost:9092 --topic=teste --describe

kafka-consumer-groups (help)
- Consumir mensagens
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste

Abrindo novo console cmd:
- produzindo mensagens
kafka-console-producer --bootstrap-server=localhost:9092 --topic=teste


//Produzir varios mensagens, caso o consumer pare.
- consultar / lembrando que vai aparecer fora de ordem, pois foram enviadas as mensagens e salvas em partições diferentes.
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --from-beginning

- Criar um consumer group
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --group=x

- Detalhando o group
kafka-consumer-groups --bootstrap-server=localhost:9092 --group=x --describe


- Consultar via control-center
http://localhost:9021/
# kafka
