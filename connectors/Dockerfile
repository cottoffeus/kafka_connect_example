#Образ для Kafka Connect JDBC Connector (Source and Sink) for Confluent Platform (https://docs.confluent.io/kafka-connectors/jdbc/current/index.html#jdbc-connector-source-and-sink-for-cp)
FROM confluentinc/cp-kafka-connect:latest
RUN   confluent-hub install --no-prompt confluentinc/kafka-connect-jdbc:10.6.0 \
      && confluent-hub install --no-prompt confluentinc/kafka-connect-datagen:latest