---
title:  "Agile Mühendislik Pratikleri - II"
date:   2015-12-23 11:16:01 -0600	
categories:
  - Tech
  - Agile
  - Engineering Practices
header:
    image: sunrise-at-vermillion3.jpg
---

Uzun süredir sektörde olmasam da danışman olarak şimdiye kadar telekomünikasyondan bankacılığa, sigortacılıktan elektronik ticarete birçok farklı alanda hizmet veren yirmiye yakın firma ve yüzlerce farklı kişiyle çalışma fırsatı buldum. Çalıştığım bu şirketlerin en az yarısının Agile yazılım geliştirme yöntemlerini uygulamaya çalıştıklarını rahatlıkla söyleyebilirim. Kalan yarısının da Agile metodolojileri uygulama konusunda kendilerini zorunda hissettikleri açıkça görülebiliyordu. Hatta bu zorunluluğun birçok zaman başarısız girişimlere sebep olduğunu da gözlemleme fırsatım oldu. Türkiye gibi hiyerarşik bir toplum yapısının olduğu ve desteklendiği ülkelerde Scrum gibi oldukça yatay bir yönetim biçiminin içselleştirilmesi de oldukça zor oluyor elbette.

Ancak beni asıl rahatsız eden konu, ülkemizdeki çevik dönüşüm projelerinin büyük ölçüde yönetimsel/kurgusal seviyede kalması. Birçok firma Scrum’ı ya da her ne metodolojiyi hedefliyor ise, kurguladıktan sonra daha işin mutfağına dokunmadan çok farklı beklentilere giriyor. Öyle ki bu firmaların bazılarında ne Git yada SVN gibi bir “Version Control” sistemi ne de Jenkins gibi “Build Server” bulunmuyor. Hal böyle olunca Continuous Delivery, DevOps gibi konulara sıra gelemiyor zaten.

En basit anlamıyla kullanılabilecek bir Version Control ve Build Server yardımı ile kurgulanması hedeflenen “Agile” ruhun yerleşmesinde oldukça avantaj sağlanabiliyor olacaktır aslında. Aksi halde, teorideki bilgiyi hayata geçirmeden, aslında sağlam bir biçimde uygulayabileceğimiz pratikleri de değersizleştirmiş oluyoruz. Öyle ki, çevik metodolojilere geçişteki en büyük itici güç olan sürekli geri bildirim, artırımsal ürün gelişimi gibi hedeflere ulaşmak da oldukça güç oluyor. Özellikle tekrar eden taskların otomatize edilmemesi (Kod Analizi, Test, Deployment, Release gibi) hem sistemleri hataya açık hale getirirken, hem de adımların yeterince hızlı gerçekleştirilememesi nedeniyle birçok çevik yazılım geliştirme prensibinin uygulanması mümkün olmuyor (Regression Testing, Continuous Integration/Deployment gibi).

Bu sorunları en aza indirmek için yazılım geliştirme sürecini bir boru hattı ( Birbirini izleyen ve tamamlayan adımlar bütünü) olarak görmek ve hattı oluşturan adımları mümkün olduğunca otomatize edilmesini sağlamak oldukça önem taşıyor. Bu hat da literatürde “Delivery Pipeline” olarak isimlendiriyor genel olarak. 

Kavramsal olarak ideal bir Delivery Pipeline’da bulunması gereken adımları aşağıdaki şekilde özetlemek mümkün. Kullanılabilecek ürün/teknolojilerin akışta bulunması yönlendirici olsa da, konuya ilk kez dahil olacaklar için faydalı olacağını düşünüyorum.

Konuyla ilgili kendini daha fazla geliştirmek isteyenler için de Jez Humble’ın “Continuous Delivery” isimli kitabı iyi bir kaynak olacaktır.

