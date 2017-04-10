---
title:  "Docker for Beginners, Part I"
date:   2017-01-19 10:16:01 -0600
categories:
  - Tech
  - DevOps
  - Docker
header:
    image: whales-underwater-darrenjew-whale-02b.jpg
---

DevOps uygulamalarının en popülerlerinden biri Docker. Zira büyük bir hızla Virtual Machine’lerin yerini alıyor.

Docker temel olarak, bir süredir Linux çekirdeğinde bulunan container kavramının kullanılabilmesine imkan vermeye başladı. Bu sayede VM’lere göre inanılmaz hızlı ve taşınabilir container'ları kullanabilmeye başladık.

Klasik olarak bir VM imajı üzerinde uygulama sunucularınızı ayağa kaldırdığınızda, bu yapının çalışması için alt tarafta hem host, hem de guest işletim sistemi seviyesinde komutların işlenmesi gerekmekte. Bu da özetle, uzun süredir deneyimlediğimiz VM tabanlı uygulamalardaki performans sorunlarına neden olmakta.

Docker’ın containerization teknolojisi ile ikinci bir (guest) işletim sistemine gerek kalmadan, host işletim sistemi üzerinde birbirinden bağımsız konteyner yapılarının çalışması sayesinde, uygulamaların çok daha yüksek performans ve izolasyon ile çalışması mümkün olabiliyor.

![Docker Architecture](https://berkdulger.github.io/images/docker-architecture.png)

Uygulamalar için sağladığı performans iyileştirmelerine ek olarak, devreye alımda da büyük bir hızlanma söz konusu. Konteynerler sayesinde çok daha fazla ortamın kısa süreler içerisinde oluşturulması mümkün olabilmekte.

Bir diğer avantajı ise, Infrastructure-as-Code yaklaşımı ile kurulumların hataya daha az açık hale gelmesi ve tekrarlanabilirliklerinin artması. Bu sayede herhangi bir sorunla karşılaşıldığında, SVN, GIT, TFS gibi repository’ler ile kaynak kod için yapılan versiyonlama benzeri (aslında tamamlayıcı) bir yaklaşım ile istenilen konfigürasyona dönülmesi mümkün olabiliyor. Bu sayede, örneğin canlıda karşılaşılan hataların Test ve UAT ortamlarında tüm komponentleri ile tekrar oluşturulabilmesinin önü açılıyor.

Tüm bu esneklik, IT dünyasındaki yeni 'Trend-Topic' olan Microservices mimarisinin gerçek olabilmesine imkan tanıyor. Gerçek anlamda bağımsız ve yönetilen microservisler için neredeyse mutlak olarak bir container desteği gerekli olmakta.

Docker Ubuntu 16.10 Kurulumu

    #sources.list dosyasının içine repository'yi ekleyin (deb ile başlayan)
      sudo nano /etc/apt/sources.list
      deb https://apt.dockerproject.org/repo ubuntu-xenial main
    
    ﻿
    #repository için key'leri tanımlayın
      sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 
    ﻿  --recv-keys ﻿58118E89F3A912897C070ADBF76221572C52609D
    ﻿
    
    #sertifikaları yükleyin
      sudo apt install apt-transport-https ca-certificates
    
    
    #repository tanımlarını güncelleyin
      sudo apt update
    
    
    #repository'den docker engine'i indirin
      sudo apt-get install docker-engine
      
Docker Deamon Check

    #daemon kontrol
    systemctl status docker
    
    
    #boot daemon autostart
    sudo systemctl enable docker


Docker Run, Hello-World

Docker container'ını çalıştırıyoruz. Yaptığı tek işlem ekrana hello-world mesajını yazarak kendini sonlandırmak.

    sudo docker run hello-world