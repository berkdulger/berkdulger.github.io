---
title:  "Test Otomasyonu, Motivasyon ve Sahiplik"
date:   2016-03-01 16:16:01 -0600
categories:
  - Tech
  - Social
  - Test Automation
  - Code Maintenance
header:
    image: melbourne_2-wallpaper-1920x1080.jpg
---
Yer aldığım birçok test otomasyon projesinde en çok kafa karıştıran konuların başında, test otomasyonunun amacı ve bu işin kim tarafından sahiplenileceği çelişkisi olduğunu gördüm. Soruna doğru şekilde cevap verilebilmesi için, öncelikle doğru teşhis yapılabilmesi gerektiğini düşünüyorum.

Test otomasyonu bir yazılım geliştirme aktivitesidir.
Herhangi bir test otomasyon aktivitesine başlamadan önce ya da projenin herhangi bir safhasında bu mottoyu kesinlikle akıldan çıkarmamak gerekmekte. Aksi halde beklentiler, bir yazılım projesinin karşılayabileceğinin çok üzerine çıkabiliyor. Birçok kişinin, özellikle yöneticilerin, test otomasyonundan beklentileri o kadar yükselebiliyor ki, iş akışı sözel olarak dahi ifade edilemeyen süreçlerdeki sorunların bu sayede çözüleceği fikrine kapılabiliyorlar. Bu sebeple oldukça iyi ilerleme gösteren birçok test otomasyon projesinin başarısız olarak nitelendirildiğine şahit oluyoruz.

Özellikle regresyon testleri kapsamında geliştirilen test otomasyon projeleri için önerilen yaklaşım;

> Regresyon amaçlı test otomasyonu ile hata bulmak değil, yazılımın kalitesini ortaya koymak hedeflenmelidir.

Elbette otomatize testlerle hata yakalamak oldukça önemli bir kazanım. Ancak, regresyon testlerinde esas hedefin mevcut fonksiyonalitenin bozulmadan çalıştığının gözlemlenebilmesi olması sebebiyle, istenilen hata tespit sayılarına ulaşılamaması durumunda ekiplerin demotivasyonu kaçınılmaz olmakta.

Ayrıca test otomasyonundan beklentileri yüksek olan kişilerin neredeyse tümünde, otomasyonunun bir kez gerçekleştirilip, uzun bir süre boyunca her hangi bir bakım gerektirmeksizin kullanılabileceği düşüncesi bulunmakta. Ancak maalesef bu pek gerçekçi bir yaklaşım değil. 

Test otomasyon yazılımları, diğer tüm yazılımlar gibi belirli bir bakım eforuna ihtiyaç duymaktadır. Hatta birçok açıdan bu ihtiyaç diğerlerinde daha fazla olmaktadır. Bu durumun temel nedeni ise test otomasyon kodlarının (yazılımlarının) edilgen yapısıdır. Herhangi bir ürün kodu değiştirildiğinde buna karşılık yazılan test kodlarının re-factor edilmesi hatta çoğu zaman baştan yazılması gerekmektedir.

Metodoloji fark etmeksizin, en azından ülkemizde, zaman baskısı başta olmak üzere farklı sebeplerden dolayı test otomasyonunun bir süre sonra ikinci planı atıldığını hatta kimi zaman tamamen rafa kaldırıldığını görmek işten bile değil. Bunu engellemenin de en iyi yolu ise, görev tanımı test otomasyonu üzerine kurgulanmış kişi veya kişilerin sahipliğinde projelerin devam ettirilmesidir.

Motivasyon ve sahiplik anlamında başarılı test otomasyon projeleri için;

- Test otomasyonunun bir yazılım geliştirme aktivitesi olduğu, özel bilgi ve birikim gerektirdiği bilinci oluşturulmalıdır.
- Test otomasyonu projesinin motivasyonu ve hedefi belirlenmelidir.
- Test scriptleri için bakım maliyetleri göz ardı edilmemelidir.
- Test kodları, değişen ürün karşısında düzenli olarak re-factor edilmelidir.
- Test otomasyonu sürecinin bir sahibi olmalıdır.