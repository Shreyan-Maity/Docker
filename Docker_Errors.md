This is error while installing docker in an **EC2 Instances** via the command
```
sudo apt install docker.io
```
Then
```
docker ps
```
OutPut:
```
ubuntu@ip-172-31-21-223:~$ docker -v
Docker version 24.0.7, build 24.0.7-0ubuntu4.1
ubuntu@ip-172-31-21-223:~$ docker ps
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied
```
----------------------------------------------------------------------------
**RUN The Below to give docker the permission:**
```
sudo chmod 777 /var/run/docker.sock
```
OutPut:
```
ubuntu@ip-172-31-21-223:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```
