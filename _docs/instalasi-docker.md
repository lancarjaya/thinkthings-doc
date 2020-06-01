---
title: Instalasi Docker
permalink: /docs/instalasi-docker/
---

# Instalasi Docker
sebelum kita dapat memulai instalasi The Things Stack, kita terlebih dahulu harus install Docker Engine dan Docker Compose, adapun langkah-langkah instalasinya adalah sebagai berikut:

> Langkah pada dokumentasi ini menggunakan OS Linux Ubuntu Server 18.04 LTS

## Installasi Docker Engine
Ada beberapa metode untuk dapat menginstall Docker Engine yaitu

 - Menambahkan repository Docker ke OS lalu menginstallnya melalui repository tersebut. langkah ini merupakan langkah yang direkomendasikan oleh Docker
 
 - mendownload paket .deb lalu menginstallnya secara manual
 
 - menggunakan convenience script

pada langkah dibawah ini kita akan menggunakkan metode repository.

### Menambahkan Repository

1. Update index repository:
```bash
$ sudo apt update
```
2. Install paket-paket pendukung:
```bash
$ sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
3. Tambah key GPG resmi Docker:
```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
4. Tambah repository Docker (branch stable):
```bash
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
### Menginstall Docker Engine
1. Update index repository:
```bash
$ sudo apt update
```
2. Install Docker-Engine:
```bash
$ sudo apt install docker-ce docker-ce-cli containerd.io
```
3. Verifikasi hasil installasi Docker dengan menjalankan image hello-world:
```bash
$ sudo docker run hello-world
```
Jika image hello-world berhasil dijalankan maka installasi Docker Engine telah berhasil.

## Installasi Docker Compose
sebelum kita dapat melakukan installasi Docker Compose, pastikan terlebih dahulu Docker Engine sudah berhasil terinstal dan berjalan dengan baik.

1. Download rilis stabil Docker Compose terbaru:
```bash
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
2. Tambahkan permission executable ke binary:
```bash
$ sudo chmod +x /usr/local/bin/docker-compose
```
3. Cek hasil installasi Docker Compose:
```bash
$ docker-compose --version
```
