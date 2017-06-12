---
title:  "Docker Part II, WordPress"
date:   2017-02-03 10:16:01 -0600
categories:
  - Tech
  - DevOps
  - Docker
header:
    image: whales-underwater-20150810_9351_darrenjew.jpg
---
Docker kurulumunu gerçekleştirip, "Hello World!" mesajını görmek doğru yolda olduğumuzun en önemli göstergesi. Ancak bu mesaj ironik bir şekilde o kadar da heyecan verici görünmüyor. Peki Docker'ı nasıl anlamlı bir şekilde kullanabiliriz? Aslına bakarsanız, aklınıza gelen nerdeyse tüm web uygulamalarını dockerize etmeniz mümkün. Bu açıdan basit bir örneğin başlangıç için faydalı olacağı fikrindeyim.

Bunun öncesinde terminoloji ve bazı temel Docker komutlarını bilmemiz fayda sağlayacaktır.

Docker Terminolojisi

Image - Cotainer'ların oluşturulacağı, önceden hazırlanmış "blue-print" öğeler. Local olarak bulunmayan image'ların pull işlemi ile yüklenmesi sağlanabiliyor.

Container - Image'lardan hayat bulan, çalışan kopya. Docker'ın alamet-i farikası! Class/Object arasındakine benzer bir ilişki olduğu söylenebilir.

Layer - Container'ın istenilen konfigürasyona getirilmesi için üzerinde çalıştırılan her bir komut grubunu sarmalayan yapı.

Registry/Hub - Image'ların tutulduğu merkezi depo.

Docker Compose - Birden fazla container'ı yönetmek için kullanılan docker uygulaması. Modern uygulamaların neredeyse tümü için gerekli .

Docker Setup ve Run Komutları

    #Build an image from Dockerfile 
    docker build -t myapp:1.0
     
    ﻿#Download an image
    docker pull image_name
    
    #List all docker images
    docker images
    
    #List all running containers
    docker ps
    
    #Start and stop the container
    docker [start|stop] container_name
    
    #Create and start container, run command
    docker run image_name
                          --name container_name #Name container
                          --p 3000:80           #Expose port
                          --it                  #Connect to container terminal
    
    #Kill all running containers
    docker kill $(docker ps -q)
    
    #Remove all stopped containers
    docker rm $(docker ps -a -q)
    
Docker Tutorial-Project / WordPress

En çok kullanılan blogging framework'u olan WordPress uygulamasını ayağa kaldırmak güzel bir egzersiz olacaktır.

> Bunun için Docker Compose'u yüklememiz gerekli, zira Wordpress için webserver ve database'ı taşıyacak iki farklı container'a ihtiyacımız var. Elbette bu ikisini aynı container içerisinde bulundurma imkanımız bulunuyor. Ancak bunun container'ların felsefe ve amacına uyacağı pek söylenemez. Quora ve   TechBeacon'da güzel birkaç yanıt verilmiş.

- Bir klasör oluşturun.
- Klasöre içerisine konfigürasyonun tutulacağı docker-compose.yml dosyasını oluşturun. Bu dosya birden çok container için istenilen konfigürasyonu belirtiyor.

Docker-compose.yml dosyasının içeriği,

    version: '2'
    
    services:
       wordpress:
         depends_on:
           - db
         image: wordpress:latest
         ports:
           - "8000:80"
         restart: always
         environment:
           WORDPRESS_DB_HOST: db:3306
           WORDPRESS_DB_PASSWORD: keytorcPassword
       db:
         image: mysql:5.7
         volumes:
           - db_data:/var/lib/mysql
         restart: always
         environment:
           MYSQL_ROOT_PASSWORD: keytorcPassword
           MYSQL_DATABASE: keytorcPassword
           MYSQL_USER: keytorcPassword
           MYSQL_PASSWORD: keytorcPassword
    volumes:
        db_data:
        
.yml dosyasını oluşturduktan sonra,

    docker-compose up -d﻿
    
komutu ile container'larımızı ayağa kaldırıyoruz. Sonrasında local 8000 portu üzerinden WordPress kurulum ekranına ulaşabilmemiz gerekiyor.


![WordPress Welcome](https://berkdulger.github.io/images/wordpress-welcome.png)

wordpress-welcome