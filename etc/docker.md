
# docker #

```
CONTAINER_NAME=tc-dev

docker run \
  --name=${CONTAINER_NAME} \
  -v /home/${USER}/code:/home/tc/code \
  --network=host \
  --privileged \
  -it \
  -d \
  ubuntu:22.04

docker exec -it ${CONTAINER_NAME} bash
docker start ${CONTAINER_NAME}

```


# mt #

```
docker run \
  --name ${CONTAINER_NAME} \
  -v /home/${USER}/code:/home/tc/code \
  -v /dev/shm/${USER}/dist-mem:/dist-mem \
  --network=host \
  --privileged \
  -it \
  -d \
  sh-harbor.mthreads.com/mcc-flow/base/ubuntu:22.04

```
