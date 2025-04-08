
# dev machine #

```
ssh user@192.168.5.234

```


# install #

```
sudo apt update --fix-missing
sudo apt install -y \
  \
  curl \
  fio \
  git \
  openssh-server \
  \
  cmake \
  clang \
  clangd \
  \
  python3 \
  python3-pip \
  python3-venv \
  python3-distutils \
  pybind11-dev \
  \

```


# go #

```
# install go #

rm -rf /usr/local/go
tar -C /usr/local -xzf go1.24.1.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
export GOPROXY=https://goproxy.cn,direct
export GOSUMDB=sum.golang.google.cn  # 校验库的国内镜像

```


# docker #

```
sudo usermod -aG docker ${USER}
sudo docker login \
  --username=<????> \
  registry.cn-hangzhou.aliyuncs.com

sudo nano /etc/docker/daemon.json
  {
      "registry-mirrors": ["https://<????>.mirror.aliyuncs.com"]
  }

sudo systemctl restart docker
sudo systemctl status docker
docker pull ubuntu:22.04

```


# user #

```
sudo adduser -m tc
sudo usermod -aG sudo tc
sudo visudo
    tc ALL=(ALL) NOPASSWD:ALL
sudo chsh -s /usr/bin/bash tc

su - tc

chmod 400 ~/.ssh/id_rsa

```


# ssh #

```
~/.ssh/config:

Host *
  ServerAliveInterval 30
  ServerAliveCountMax 10
  GSSAPIAuthentication yes
  GSSAPIDelegateCredentials no
  StrictHostKeyChecking no
  HostKeyAlgorithms +ssh-rsa
  PubkeyAcceptedKeyTypes +ssh-rsa

```


# cmake #

```
cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=1 build

```


# core dump #

```
ls /var/lib/apport/coredump/

```
