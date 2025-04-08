
# docker #

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu (lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

```
sudo usermod -aG docker $USER
sudo docker login --username=<????> registry.cn-hangzhou.aliyuncs.com
sudo nano /etc/docker/daemon.json
  :
  {
      "registry-mirrors": ["https://<????>.mirror.aliyuncs.com"]
  }
  :

sudo systemctl restart docker
sudo systemctl status docker
docker pull ubuntu:22.04
```

```
docker run \
  --name=tc-dev \
  -v /home/user/code:/home/tc \
  --network=host \
  --privileged \
  -it \
  -d \
  ubuntu:22.04

docker exec -it tc-dev bash
docker start tc-dev 
```


# mt #

```
docker run \
  --name tc-dev \
  -v /home/tc/code:/home/tc/code \
  -v /dev/shm/tc/dist-mem:/dist-mem \
  --network=host \
  --privileged \
  -it \
  -d \
  sh-harbor.mthreads.com/mcc-flow/base/ubuntu:22.04
```