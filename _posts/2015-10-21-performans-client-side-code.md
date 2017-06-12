---
title:  "Performans: Client-Side Code"
date:   2015-10-21 11:16:01 -0600	
categories:
  - Tech
  - Performance Engineering
  - Client-Side Code
header:
    image: cheetah_9-wallpaper-1920x1080.jpg
---
Performans test senaryolarının belirlenmesi ve test yükünün modellenmesinin ardından üçüncü adım olarak test scriptlerinin geliştirilmesine geliyor sıra. Bu aşama birçok araç tarafından desteklendiği için, genel olarak kişiler tarafından zorlanılmadan!! gerçekleştirilebiliyor. Ancak her ne kadar araçlar tarafından desteklense de, dikkat edilmesi gereken bazı noktalar da mevcut. Özellikle Web 2.0 teknolojilerinin gelişmesi ile web tabanlı uygulamaların bir kısmının istemci tarafına (Client-Side) geçmesi ile eski tasarımsal yaklaşımlar yeterli olmamaya başlıyor. İstemci tarafında bulunan Javascript, Flash, JQuery, Angular ve Ajax gibi kimi asenkron araçlarının varlığı, yeni uygulamaların klasik bir Web uygulamasına göre farklı bir mimaride çalışıyor olması anlamına geliyor özetle.

![Client-Side Code](https://berkdulger.github.io/images/clientside-code.jpg)

Her yıl daha da artan oranda istemci ağırlıklı (Node.js gibi teknolojilerin de gelişmesi ile) yapıların kurulması, yazılım performansı açısından daha kritik rol oynamaya başlıyor. Genel olarak, istemci tarafında artan kod miktarı ile sunucular üzerindeki yük azalmakta denilebilir. Bu sayede kapasite anlamında oldukça yüksek oranda verimlilik de elde edilmiş oluyor. Örneğin, Java kodu içerisinde gerçekleştirilen bir grafiksel gösterim x kadar kullanıcıya destek verebilirken, bu gerçekleştirimi JQuery tarafında yaparak 2x kullanıcıya 10’da 1 kapasite ile destek vermek mümkün olabiliyor.

Ancak böyle bir mimari ne kadar verimli olursa olsun, nihai olarak belirli bir kapasite sunabiliyor. Performans Mühendislerinin de bu kapasiteleri ölçümlemesi ve akabinde iyileştirebilmesi için çeşitli aktiviteler gerçekleştirmesi gerekiyor (Performans iyileştirmeleri kendi başına oldukça geniş bir konu olduğu için daha sonra değinmenin uygun olacağını düşünüyorum). Testler esnasında, genel olarak, client-side kodların sunucu tarafına yük getirmediğini düşünmek ve tasarımı bu göre dizayn etmek mümkün. Ancak Ajax gibi client-side ve asenkron teknolojiler işin içine girdiğinde durum değişmeye başlıyor. Çünkü bu uygulamalar çalıştıkları süre içerisinde sayfa istemi gerçekleştirmiyor olsalar da, sunucu ile sürekli olarak haberleşiyor oluyorlar.

Bu noktada durumu kotarmak için gerçekleştirilebilecek üç farklı aktivite bulunuyor. İlk seçenek olarak, client-side kodları da simule edebilen “True-Client” gibi teknolojilere sahip araçların kullanılması akla geliyor. İkincil olarak, Selenium Webdriver gibi tamamen user experience’ı simule edebilecek ve browser üzerinden uygulamaya erişen otomasyon araçlarını kullanmak mümkün (Ancak bu yaklaşım gerçekleştirilmek isteniyorsa oldukça iyi bir tasarım gerçekleştirilerek, bazı ödünlerin verilmesi gerekecektir). Üçüncü ve son olarak da, standart performans araçları içerisine bu aktivitelerin kodlanmasını belirtebiliriz.

Kişisel olarak maliyet, zaman ve kalite kriterleri total olarak değerlendirildiğinde, tercihimin 3, 2 ve 1 şeklinde olacağını söyleyebilirim. Bu şekilde kesinlikle daha fazla emek ve tecrübe gerekirken, oldukça yüksek miktarda parasal tasarruf yapılabilecektir.

Referans: http://www.keytorc.com/yazilim-performans-testleri/