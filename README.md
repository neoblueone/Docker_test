# Docker_test
Docker build test v2.0

# nowage/pyspark-tensorflow-notebook
pyspark+tensorflow notebook, This image supports the sudo command which is not available in Jupyter/pyspark-notebook and supports commands such as pyspark and spark-submit.
(본 이미지는 Jupyter/pyspark-notebook에서는 안되는 sudo 명령을 지원하며 pyspark과 spark-submit과 같은 명령을 지원합니다.)

# Building & Running
Copy the sources to your docker host and build the container, and to run.
```
	docker build --rm -t neoblueone/pyspark-tensorflow-notebook .
	docker rm -f st
	docker run                   \
		--name=st             \
		--rm                  \
		-P -it                \
		-p 8888:8888          \
		-p 6006:6006          \
		-v ~/df:/notebooks/df \
		neoblueone/pyspark-tensorflow-notebook
```
Get the port that the container is listening on:

```
# docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ad2ad96e4b2f        neoblueone/pyspark-tensorflow-notebook "/bin/bash"         7 seconds ago       Up 6 seconds                            st
```

To test, 
```
	sudo su -
```
To Rollback
```
    docker rm st -f
    docker rmi neoblueone/pyspark-tensorflow-notebook
```
