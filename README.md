## Проект для демонстрации работы Kafka Connect

Для запуска использовать Docker-Compose

- docker-compose-debezium.yaml - коннектор на основе Debezium
- или
- docker-compose-jdbc-source.yaml - коннектор на основе драйвера JDBC

### В результате разварчиваются сервисы:

- postgres - БД с тестовой базой (docker-entrypoint-initdb.d/example db employees.sql) 
- adminer - админка для БД 
- zookeeper - сервер конфигураций
- kafka - брокер кафка куда сливаются сообщения
- kafka-connector - Kafka Connector, который синхронизирует данные из БД в Kafka топики