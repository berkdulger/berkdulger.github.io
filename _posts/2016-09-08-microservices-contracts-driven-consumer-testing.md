---
title:  "Microservices, Contracts-Driven Consumer Testing"
date:   2016-09-08 10:16:01 -0600
categories:
  - Microservices
  - Testing
  - Integration
header:
    image: galaxy-wallpaper-11.jpg
---
Microservices mimarisinin adaptasyonu gittikçe hızlanıyor. Özellikle bu yıl katıldığımız konferans ve takip ettiğimiz blog’larda bu yapıya evirilen firmaların süreçlerinden edindikleri deneyimlerin yanında, keşke yapmasaydık dedikleri noktaları da öğrenme şansımız oldu.

Aslında birçok kavram gibi microservices de kendi avantaj ve dezavantajlarını beraberinde getiriyor. Bağımsız ekipler, farklı teknolojilerin kullanımı, devreye alım ve ölçekleme esnekliği ilk akla gelen avantajlardan olurken, farklılaşan teknoloji altyapıları, ekipler arası iletişim ve servisler arası entegrasyon sorunları dezavantajları arasında sayılabilir.

Aslına bakılırsa servisler arası entegrasyon sorunu göründüğünden çok daha karmaşık. Zira monolith uygulamalarda oldukça az olan entegrasyon sayısı, yeni yaklaşımla n*(n-1) gibi exponential şekilde büyüme gösteriyor. Onlarca,  yüzlerce hatta binlerce(bunun için oldukça büyük ölçekte bir yapı gerekecektir) microservice’in olduğu bir uygulama için tüm bu entegrasyonları test etmek kolaylıkla bir kabusa dönüşebilir.

Elbette, microservices yaklaşımının esas motivasyonlarından biri olan esneklik(resilience) için yüksek sayıda verification/validation işlemi gerekli olacaktır. Ancak değişen bir servisin kendisine entegre olan diğer tüm servisleri etkileyeceğini düşündüğümüzde, bu değişiklikleri doğrulamak oldukça zorlu bir süreç haline gelmekte.

Bu sorunla başa çıkmak için geleneksel test piramidine yeni bir katman eklenmesi işlerin yönetilebilirliği açısından oldukça faydalı olacaktır.

![Test Automation Pyramid](https://berkdulger.github.io/images/mike-cohn-test-automation-pyramid.png)


Consumer-Driven Contracts Testing

Consumer’lara sağlanan API üzerinde herhangi değişiklik yapıldığında, bu servisi kullanan tüm consumer’ların API release’lerini takip ederek kendilerini güncelliyor olması gerekecektir. Veya API tarafının entegrasyonlarda sorun oluşmaması için önceki versiyon(ları) da desteklemeye devam etmesi zorunlu olacaktır.

Consumer-Driven Contracts, kullanılan (provider) ve kullanıcı (consumer) servisleri arasındaki entegrasyonun bir kontrat üzerinden tasarlandığı ve yönetildiği yaklaşım olarak düşünülebilir.

![API](https://berkdulger.github.io/images/api1.png)

Validasyon sorunu ile başa çıkma için, API’lar üzerinde yapılacak değişikliklerin validasyonu için bir kontrat mekanizması kurulabilir. Bu durumda servisi kullanacak olan tüm consumer’lar kendi kontratlarını hazırlayarak provider’ın erişimine açacaktır. Bu yaklaşımdaki önemli fayda, provider’ın hangi fonksiyonlarının nasıl kullanıldığını bilmesi ve bu sayede yapılacak önemli bir değişiklikte hangi kullanıcıların etkileneceğini öngörebilmesi ya da erişim noktalarını sabit tutarak kodun içyapısını değiştirebilmesidir.

![API](https://berkdulger.github.io/images/api2.png)

Pact, Consumer-Driven Contracts Testing için kullanılabilecek popüler open-source araçlardan. Ruby, JVM, .Net, Go gibi ortamları destekleyerek kontratlarınızı hazırlamanıza olanak sağlıyor. Daha fazla bilgi ve dokümantasyon için;

https://github.com/DiUS/pact-jvm

http://dius.com.au/2014/05/19/simplifying-micro-service-testing-with-pacts/