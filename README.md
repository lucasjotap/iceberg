#### Pyspark & Iceberg with Docker compose

### This is a solution to test PySpark with Iceberg and Polaris catalog on Docker

```bash
~$ docker compose up -d --build
```


```bash
~$ docker ps
~$ docker exec -it [CONTAINER_NAME] bash
```

Once you find the container ID with *docker ps* you can run:

```bash
docker-container:~$ pyspark
```

Then try:

```python

spark.catalog.listDatabases()
```

This simple line should list you the catalog schema; from here you are free to hack it you way.

- The Polaris server will be exposed at some port number, this will be explicitly shown to stdout.
