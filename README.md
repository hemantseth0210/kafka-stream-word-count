# kafka-stream-word-count

## Create Topics
kafka-topics --zookeeper 127.0.0.1:2181 --create --topic word-count-input --partitions 2 --replication-factor 1

kafka-topics --zookeeper 127.0.0.1:2181 --create --topic word-count-output --partitions 2 --replication-factor 1

## Create Consumer
kafka-console-consumer --bootstrap-server 127.0.0.1:9092 \
--topic word-count-output \
--from-beginning \
--formatter kafka.tools.DefaultMessageFormatter \
--property print.key=true \
--property print.value=true \
--property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer \
--property value.deserializer=org.apache.kafka.common.serialization.LongDeserializer

## Create Producer
kafka-console-producer --bootstrap-server 127.0.0.1:9092 --topic word-count-input

Type following sentences:

kafka streams is working
hemant is kafka level awesome
working working workin
