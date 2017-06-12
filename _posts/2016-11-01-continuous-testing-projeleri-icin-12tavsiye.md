---
title:  "Continuous Testing Projeleri için 12 Tavsiye"
date:   2016-11-01 16:16:01 -0600
categories:
  - Tech
  - Continuous Testing
  - Tips and Tricks
header:
    image: pexels-photo-213078.jpg
---
Klasik metodolojilerde test fazı proje sonunda ele alınarak, gerçekleştirilen tüm modüllerin hatasız ve istenilen şekilde çalışması beklenmekte. Özellikle entegrasyon noktası fazla ve kapsamlı iş bilgisi gerektiren projelerde bu durum oldukça riskli bir hâle gelebiliyor. Bunu engellemek için ise kullanılan Scrum, Kanban gibi Agile metodolojilerin DevOps pratikleri ile desteklenmesi gerekli oluyor. Test bakış açısıyla, Continuous Integration/Delivery/DevOps projeleri birer <b>“Continuous Testing”</b> projesi hâline geliyor.

<b>Continuous Testing Projeleri için Öneriler</b>

Continuous Testing projelerinin başarı ile yürütülebilmesi için ise dikkat edilmesi gereken bazı kritik noktalar bulunuyor. Bunlardan en temel olanlarını aşağıdaki gibi özetleyebiliriz:

- Yaygın olarak kullanılan ve halihazırda güçlü bir community desteği bulunan build server’lar tercih edilmelidir.
- Otomatize testler, release ve deployment süreçlerinin bir adımı haline getirilmelidir.
- Unit, Integration ve UI testlerinin birbirlerine göre farklı avantajlarının olduğu kabul edilerek, dengeli bir şekilde kullanılmalıdır.
- Test araçlarının seçiminde ilk yatırım maliyetinin yanında (CAPEX), operasyonel maliyetler (OPEX) de göz önüne alınmalıdır.
- Fonksiyonel testlerin yanında performans, güvenlik gibi fonksiyonel olmayan testler de otomatize edilerek, build sürecine entegre edilmelidir.
- Değişen teknolojilere hızla uyum sağlayabilmek için, bulut çözümlerinden mümkün olduğunca faydalanılmalıdır.
- Kod kalitesinin ölçümlenmesi için kullanılan statik kod analiz araçları da akışın bir parçası hâline getirilmelidir.
- Ekiplere hızlı geri bildirim yapılabilmesi için otomatize testler mümkün olduğunca paralelize edilmeli ve bunlar uygun bir donanım altyapısı ile desteklenmelidir.
- Build süreci boyunca gerçekleştirilen aktivitelerin her biri için SLA’ler tanımlanarak, yazılım ve test ekipleri durumdan haberdar edilmeli, hatta gerekli olduğu durumlarda ayrıntılı inceleme için tüm süreç durdurulmalıdır.
- Canlı ortama geçilmeden önce, tüm testler canlı ortamın birebir bir kopyası olan staging/pre-prod ortamlarında tekrar edilmelidir.
- A/B Testing ya da Canary Release gibi yöntemler ile yeni geliştirmeler kontrollü bir şekilde canlıya çıkılmalıdır.
- DevOps pratiklerinin uzun süredir tecrübe edilmediği ortamlarda, riski azaltmak adına tam otomatize süreçler yerine, manuel kontrollerin yapılabileceği, canlıya çıkıp çıkmama kararının verilebileceği yarı-otomatize süreçler kurgulanmalıdır.

Kaynak

Keytorc Blog: [DevOps Yaklaşımında Yazılım Testi](http://www.keytorc.com/blog/devops-yaklasiminda-yazilim-testi_3625/)