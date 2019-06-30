# MinIO Client (mc)

[MinIO Client (mc)](https://github.com/minio/mc) предоставляет современную альтернативу командам UNIX, таким как ls, cat, cp, mirror, diff и т. д.
Он поддерживает файловые системы и совместимый с Amazon S3 облачный сервис хранения данных.
Общий [порядок вызова команд](https://github.com/minio/mc/blob/master/docs/minio-client-complete-guide.md) смотрите в официальной документации MinIO Client.

## Подготовка к работе {#preparations}

[!INCLUDE [storage-s3-http-api-preps](../_includes_service/storage-s3-http-api-preps.md)]

## Установка {#installation}

Для установки MinIO Client воспользуйтесь [инструкцией](https://github.com/minio/mc/blob/master/docs/minio-client-complete-guide.md#1--download-minio-client) в репозитории проекта.

## Настройка {#setup}

Для настройки MinIO Client используйте команду `mc config`. Нам нужны будут:

1. `Access Key` — идентификатор ключа, который вы получили при генерации статического ключа.
1. `Secret Key` — секретный ключ, который вы получили при генерации статического ключа.

```
mc config host add yandex-cloud [!KEYREF s3-storage-host] <Access Key> <Secret Key>
```

Команда `mc config` сохранит настройки в файле `~/.mc/config.json`

При необходимости эти настройки можно изменить напрямую в файле.

## Примеры операций {#mc-examples}

### Создать бакет

   ```bash
   mc mb yandex-cloud/<bucket> 
   ```
   
> [!NOTE]
>
> При создании бакета помните об [ограничениях на имя](../concepts/bucket.md#naming).

### Загрузить объект

```
mc cp local_file yandex-cloud/<bucket>
```

### Получить список объектов

```bash
mc ls yandex-cloud/<bucket>
```

### Получить объект

```bash
mc cp yandex-cloud/<bucket>/object local_file
```

### Удалить объект

```bash
mc rm yandex-cloud/<bucket>/object
```


### Синхронизация

```bash
mc mirror localdir/ yandex-cloud/<bucket>/dir/
```
