---
title:  "Performans Test Terminolojisi"
date:   2015-09-21 11:16:01 -0600	
header:
    image: lion_27-wallpaper-1920x1080.jpg
---
Fonksiyonel olmayan yazılım gereksinimlerinden biri olan “Performans” , bir sisteminin normal şartlar altında, beklenen en yüksek kullanım anında ve bunun ötesinde verdiği tepkiler olarak tanımlanabilir. Bu nedenle analiz safhasında fonksiyonel gereksinimlere ek olarak, performans gibi fonksiyonel olmayan gereksinimlerin de belirlenmesi önem taşımaktadır. Bu sayede üretilen yazılımın hangi performans kriterleri (Performance SLA) ile devreye alınacağı da net olarak belirlenebilir.

Bu kriterlerin sağlanıp sağlanamadığının kontrol edilmesi de Performans, Yük ya da Stres testleri ile mümkün olabilmektedir.

Terminolojik olarak;

Performans Testi: Sistemin normal şartlar altında (Örneğin ortalama bir kullanım anında) hangi performans kriterleri ile hizmet sunduğunun ölçümlenmesi.

Yük Testi: Sistemin beklenen maksimum kullanım koşulları altında (Kotarılması beklenen en yüksek kullanım miktarı – Peak Point) hangi servis düzeyinde hizmet verildiğinin ölçümlenmesi.

Stres Testi: Sistemin, limitlerinin ötesinde yüklenilmesi ile oluşabilecek hata ve tepkilerinin gözlemlenmesidir.

Bu testlerin gerçekleştiriminde birçok commercial (HP Performance Center, IBM Rational Performance Tester, Visual Studio Load Test vb.) ya da open-source (JMeter, OpenSTA vb.) aracın kullanılması mümkün olmakla beraber esas olan, kullanılacak aracın, testleri gerçekleştirilecek yazılıma (System Under Test) olan teknolojik uyumu olmaktadır. Örneğin bir IPTV projesi için kullanılan teknolojinin, test aracı tarafından destekleniyor olması gerekmekte, aksi halde uzun süren geliştirme maliyetleri, hatta testleri gerçekleştirememe ihtimali ile karşı karşıya kalınabilmektedir.

Proje başlangıcında ilk olarak, testlerin geliştirimi ve koşumundan önce, performans senaryolarının belirlenmesi ve yeterli test verisinin oluşturulması gerekmektedir. Senaryoların temel olarak;

- Kullanıcılar tarafından en fazla tekrar edilen
- Sistem üzerinde en fazla yük oluşturan

akışlardan seçilmesi önem taşımaktadır. Nitekim performans açısından en kritik senaryolar büyük oranda bu kapsamda görülmektedir (Ürün Risk Analizi).

İkincil olarak da, oluşturulacak yükün modellenmesi gerekmektedir. Bu modelleme için, eğer öncesinde kullanılan referans (Legacy) bir ortam bulunuyor ise, Google Analytics gibi bir ortamdan istatistiki bilgilerin yorumlanması oldukça faydalı olacaktır. Böyle bir referans bulunmuyor ise de, iş birimleri ve analiz ekipleri ile konunun yorumlanması, akabinde de hedeflerin ortaya konulması gerekmektedir.

Yük modellemesi aşamasında dikkat edilmesi gereken bir diğer konu ise doğru hedeflerin konulması olmaktadır. Özellikle “Simultenous” ve “Concurrent” ifadelerinin hatalı bir şekilde bir birleri yerine (Büyük ihtimalle ikisinin de Türkçe’ye "Eşzamanlı" olarak çeviriminden kaynaklan) kullanımı ile çok sık karşılaşılabilmektedir. Aslen, “Concurrent” ile zaman içerisinde çakışan (overlapping in duration), “Simultaneously” ile de tam aynı anda (at the same instant) işlem yapan kullanıcıların kast ediliyor olunması gerekmektedir.

Bu sebeple Analytics raporlarında görülen eş zamanlı kullanıcı sayısını referans almak yerine, bu kullanıcıların oturum açtıkları süre boyunca yaptıkları işlemlere dikkat ediyor olmak gerekmektedir. Bu yöntemle kullanıcı işlemlerinin daha kısa sürelere ölçeklenmesi ile (Örneğin, 4’de 1 iyi bir ölçeklendirme olabilir) çok daha az sayıda sanal kullanıcı ile testlerin gerçeğe yakın olarak gerçekleştirilebilmesi mümkün olabilmektedir. Ancak bu tarz bir ölçeklendirme ne kadar mantıklı görünse de, “Memory Leakage” gibi toplam session sayısına bağlı metriklerde doğru sonuç vermeyecektir.