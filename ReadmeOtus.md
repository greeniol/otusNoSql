# Clickhouse
1. Накатила Ubunta под windows
2. Зарегалась в облаке яндекса, создала clickhouse
3. Установила клиент. Скачала тестовый файл по примеру из презентации.
4. Подключила к своему clickhouse бобра. В нем создала таблицу (также взяла из презы) и попыталась через dbeaver же залить данные. Бобр закономерно умер. 
5. Проделала ту же историю в клиенте. Клиент грязно выругался при попытке заливки скачанного файла в таблицу.
6. В итоге взяла таблицы из https://clickhouse.com/docs/ru/getting-started/example-datasets/metrica/, прихватила сразу обе visits и hits чтоб не мелочиться. на этот раз через клиент все залилось нормально.
7. Сделала обеим таблам OPTIMIZE и COUNT (доступ к clickhouse выдала всем, поэтому по идее, приведенные ниже запросы должны отработать):

  clickhouse-client --host rc1c-kr2ewt26dcn6pkaz.mdb.yandexcloud.net --secure --user user1 --database db1 --port 9440 --password 12345678 --query "SELECT COUNT(*) FROM db1.visits_v1"
  
  clickhouse-client --host rc1c-kr2ewt26dcn6pkaz.mdb.yandexcloud.net --secure --user user1 --database db1 --port 9440 --password 12345678 --query "SELECT COUNT(*) FROM db1.hits_v1"
