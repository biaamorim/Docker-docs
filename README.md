# TUTORIAL DE COMO INSTALAR O DOCKER
Repositório para documentar a instalação do docker. A base utilizada como mentoria foi a partir da documentação e das aulas de redes do 7 período.

# Detalhes iniciais

1 - Instalação do docker descktop;
2 - Instalação do Ubunto.


# Configurando o repositorio

* Comando para atualizar os pacotes


```console 
biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get update
```

``` console
Hit:1 http://archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:3 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:4 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]
Get:5 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [363 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [605 kB]
Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [169 kB]
Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [271 kB]
Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/restricted Translation-en [41.3 kB]
Get:10 http://security.ubuntu.com/ubuntu jammy-security/main amd64 c-n-f Metadata [9732 B]
Get:11 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [887 kB]
Get:12 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [709 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/universe Translation-en [182 kB]
Fetched 3574 kB in 21s (169 kB/s)
Reading package lists... Done
```

* Comando para instalar as dependências necessárias

``` console 
biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get install ca-certificates curl gnupg
```

``` console
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
ca-certificates is already the newest version (20211016ubuntu0.22.04.1).
ca-certificates set to manually installed.
curl is already the newest version (7.81.0-1ubuntu1.10).
curl set to manually installed.
gnupg is already the newest version (2.2.27-3ubuntu2.1).
gnupg set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 23 not upgraded.
```
# Configurações da chave GPG
* Comando para criar o diretório da chave GPG
``` console
sudo install -m 0755 -d /etc/apt/keyrings
```
* Comando para adicionar a chave GPG oficial do docker ao diretório de chave
``` console
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
 ```
 * Comando para liberar a leitura para todos os usuários do sistema
 ``` console
 sudo chmod a+r /etc/apt/keyrings/docker.gpg
 ```
 
 * Comando para adicionar o repositório oficial do Docker para Ubuntu ao arquivo /etc/apt/sources.list.d/docker.list
``` console 
 echo \
 "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
 "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
 sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

* Comando para atualizar os pacotes 
``` console
sudo apt-get update
```

# Instalando o docker
``` console
biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  dbus-user-session docker-ce-rootless-extras libltdl7 libslirp0 pigz slirp4netns
Suggested packages:
  aufs-tools cgroupfs-mount | cgroup-lite
The following NEW packages will be installed:
  containerd.io dbus-user-session docker-buildx-plugin docker-ce docker-ce-cli docker-ce-rootless-extras docker-compose-plugin libltdl7 libslirp0 pigz
  slirp4netns
0 upgraded, 11 newly installed, 0 to remove and 23 not upgraded.
Need to get 109 MB of archives.
After this operation, 396 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
```

* Comando para verificar se a instalação ocorreu bem
``` console
sudo docker run hello-world
```
**se ocorrer tudo bem aparecerá**
``` console
biaamorim@DESKTOP-25QGOKG:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
719385e32844: Pull complete
Digest: sha256:fc6cf906cbfa013e80938cdf0bb199fbdbb86d6e3e013783e5a766f50f5dbce0
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

# Previlegio para rodar o docker sem o sudo

``` console
sudo groupadd docker
```
``` console
sudo usermod -aG docker $USER
```

#Containerizar uma aplicação

* Comando para clonar o repositório 

``` console 
git clone https://github.com/docker/getting-started.git
```

*  Comando para entrar na pasta app 

``` console
cd getting-started/app
```

* Comando para abrir um editor de texto no ubunto 
  !você está criando um novo arquivo chamado "Dockerfile" e abrindo-o no editor Nano para que você possa editá-lo e adicionar o conteúdo necessário para criar sua imagem Docker.!
  
``` console
sudo nano Dockerfile
```
  !Para salvar as alterações: **Ctrl+O** e para salvar e sair do editor **Ctrl+X**
  
* Comando para buildar o a imagem 
  ``` console
   docker build -t getting-started .
  ```
  
* Comando para rodar o docker 

  ``` console 
  docker run -dp 3000:3000 getting-started
  ```
  
  Se ocorre tudo bem esse comando vai gerar um ID do container e logo poderá acessar o localhost com a porta determina lá em cima.
  








