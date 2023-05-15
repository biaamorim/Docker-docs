# TUTORIAL DE COMO INSTALAR O DOCKER
Repositório para documentar a instalação do docker. A base utilizada como mentoria foi a partir da documentação e das aulas de redes do 7 período.

# Detalhes iniciais

1 - Instalação do docker descktop;
2 - Instalação do Ubunto.


#Configurando o repositorio

*[Comando para atualizar os pacotes]*


```console 
biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get update
```

`biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get update
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
Reading package lists... Done`

*[Comando para instalar as dependências necessárias]*

`sudo apt-get install ca-certificates curl gnupg`
`biaamorim@DESKTOP-25QGOKG:~$ sudo apt-get install ca-certificates curl gnupg
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
ca-certificates is already the newest version (20211016ubuntu0.22.04.1).
ca-certificates set to manually installed.
curl is already the newest version (7.81.0-1ubuntu1.10).
curl set to manually installed.
gnupg is already the newest version (2.2.27-3ubuntu2.1).
gnupg set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 23 not upgraded.`








