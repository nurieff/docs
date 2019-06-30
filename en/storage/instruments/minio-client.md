# MinIO Client (mc)

[MinIO Client (mc)](https://github.com/minio/mc) provides a modern alternative to UNIX commands like ls, cat, cp, mirror, diff, find etc. It supports filesystems and Amazon S3 compatible cloud storage service.
The general [procedure for running commands](https://github.com/minio/mc/blob/master/docs/minio-client-complete-guide.md) can be found in the official MinIO Client documentation

## Before you start {#preparations}

[!INCLUDE [storage-s3-http-api-preps](../_includes_service/storage-s3-http-api-preps.md)]

## Installation {#installation}

To install MinIO Client, follow the [instructions](https://github.com/minio/mc/blob/master/docs/minio-client-complete-guide.md#1--download-minio-client) in the project repository.

## Setup {#setup}

To configure MinIO Client, use the `mc config` command. We will need:

1. `Access Key` — the ID of the key that you received when generating the static key.
1. `Secret Key` — the secret key that you received when generating the static key.

```
mc config host add yandex-cloud [!KEYREF s3-storage-host] <Access Key> <Secret Key>
```

The `mc config` command saves the settings to a `~/.mc/config.json` file

If necessary, you can change these settings directly in the file

## Operation examples {#mc-examples}

### Create a bucket

   ```bash
   mc mb yandex-cloud/<bucket> 
   ```
   
> [!NOTE]
>
> When creating a bucket, follow the [naming guidelines](../concepts/bucket.md#naming).

### Uploading an object

```
mc cp local_file yandex-cloud/<bucket>
```

### Getting a list of objects

```bash
mc ls yandex-cloud/<bucket>
```

### Retrieve an object

```bash
mc cp yandex-cloud/<bucket>/object local_file
```

### Deleting an object

```bash
mc rm yandex-cloud/<bucket>/object
```


### Synchronize contents

```bash
mc mirror localdir/ yandex-cloud/<bucket>/dir/
```
