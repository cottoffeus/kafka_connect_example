## Проект для демонстрации работы Kafka Connect

ВАЖНО: Сейчас при первом запуске Debezium коннектора нужно подменить файл конфигурации в volume на postgres_data/pg_hba.conf. Нужно для разрешения репликации (указан хост подключения Кафка Коннектора)

Для запуска использовать Docker-Compose
- docker-compose-debezium.yaml - коннектор на основе Debezium
- или
- docker-compose-jdbc-source.yaml - коннектор на основе драйвера JDBC
Чтобы запустить коннектор требуется отправить конфигурацию POST запросом на адрес http://localhost:9090/connectors
- Конфигурацию взять из connectors/configs

### В результате разварчиваются сервисы:

- postgres - БД с тестовой базой (docker-entrypoint-initdb.d/example db employees.sql) 
- adminer - админка для БД 
- zookeeper - сервер конфигураций
- kafka - брокер кафка куда сливаются сообщения
- kafka-connector - Kafka Connector, который синхронизирует данные из БД в Kafka топики