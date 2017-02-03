---
title:  "Performans: Scalability Sorunlarının Tespiti"
date:   2015-12-21 11:16:01 -0600	
header:
    image: cheetah_9-wallpaper-1920x1080.jpg
---
Gerçekleştirdiğim yazılım performans danışmanlık projelerinin birçoğunda en çok duyduğum şikayetlerin “Uygulamamızın performansı yeterli değil” ya da “Müşterilerimiz uygulama performansından memnun değiller” olduğunu söyleyebilirim. Hatta neredeyse tüm projeler bu yada buna benzer nedenlerle tetiklenmiş oluyor. Bu tarz bir ifade, son kullanıcı bakış açısıyla oldukça tutarlı ve mantıklı olsa da, yazılımcı gözüyle bakıldığında aslında pek de bir anlam ifade etmiyor oluyor. Esas sorulması gereken soru ise;

“Sistem, minimal kullanım anında dahi yeterince performanslı çalışmıyor mu? Yoksa belirli bir kullanıcı sayısı üzerinde çeşitli performans sorunları mı ortaya çıkmaya başlıyor?” Semptomları benzer olsa da, aslında bu soruların iki farklı sorunu adresledikleri söyleyebiliriz; Performans ve Ölçeklenebilirlik (Scalability). Bu yüzden performans sorunları hakkında tartışırken (her zaman çok kolay olmasa da, nitekim birbirlerini etkileyebilmektedirler) bu ikisinin birbirinden ayrıştırılması gerekmektedir.
şeklinde olmalıdır. Bu yada benzer sorular sorulmadan daha fazla donanım eklenerek performans/kapasite sorunlarının çözülmeye çalışıldığına çokça şahit oluyoruz. Bazı durumlarda “pahalı” bir çözüm olarak işe yarıyor olsa da, birçok zaman da total sistem performansına fazla bir katkı sağlayamıyor oluyor. (Yazının sonlarına doğru nedenlerinden bahsedeceğim) 

Performansın Tanımı ve Ölçümlenmesi

Uygulama durumu, gelen requestlerin nasıl işlendiğini belirlemektedir. Mevcut yük, request karmaşıklığı ve diğer faktörlerin (CPU, Network vb.) tümü uygulama performansını doğal olarak etkilemektedir. Performans ölçümlenmesi için en çok kullanım üç metrik;

Response Time: Gönderilen bir request’in işlenmesi ve geri iletilmesi için gereken süreyi belirtmektedir. Yaygın olarak kullanılan, direkt ve önemli bir performans metriğidir.

Throughput: Belirli bir zaman dilimi içerisinde (örneğin 1 saniyede) sistemin işleyebileceği maksimum request sayısını belirtir. Özellikle web uygulamalarının ölçümlenmesinde gerekli bir metriktir.

System Availability: Sistemin erişilebilir olduğu sürenin, yüzdesel gösterimidir.

Metafor kullanacak olursak; tek bir requestin response time’ı otoyolda giden bir aracın hızı ise, aynı anda yolda gidebilecek araç sayısı ise throughput’u belirtmektedir. Benzer bir durum internet bağlantı hızlarında da söz konusu. Aslında throughput’unu belirten Mbps hız olarak algılanırken, hızı belirten latency süresinden bahsedilmemektedir. Zira, latecy sürelerini arttırmak throughput’u arttırmak kadar kolay olmamaktadır.
Scalability (Ölçeklenebilirlik)

Performans limitlerinin ötesine geçmek için mevcut yapıya daha fazla kaynak eklenmesine “Scaling” (Ölçekleme) denilmektedir.  Facebook gibi bazı firmalarda ise bu iş “Capacity Planning” olarak isimlendirilmektedir.

Esas olarak ne kadar kaynağa sahip olunursa olsun, belirli bir noktadan sonra yüksek average response time, yada düşük throughput gibi performans sorunları ile karşılaşılmaktadır. Bu noktada, daha fazla donanım eklenerek (scaling), sorunlar çözümlenebiliyorsa bu yaklaşım uygulanmalıdır. Eğer çözümlenemiyor ise, ölçeklenme sorunları yaşandığı söylenebilir.

Uygulama mimarisinde yapılan değişikliklere göre iki farklı scaling yöntemi bulunmaktadır; Vertical Scaling ve Horizontal Scaling.

Vertical Scaling (Single Node üzerinde kaynak arttırımı):

Mecutta var olan bir sunucuya daha fazla kaynak aktarılması ile gerçekleştirilmektedir. Bu yaklaşım genellikle sanallaştırılmış ortamlarda daha yaygın olarak kullanılabilmektedir. Sanallaştırma çözümleri üzerinde (Vmware, Hyper-V vb.) CPU, Memory gibi kaynakların arttırılması ile mümkün olmaktadır. En büyük avantajı, mevcut uygulama mimarisi üzerinde değişiklik gerektirmemesi iken, var olan baz donanım her zaman kısıtlayıcı bir unsur olmaktadır.

Horizontal Scaling (Node sayısının arttırımı):

Kullanıcılardan gelen isteklerin, farklı uygulama sunucularına yönlendirilmesinin var olan sunucuların kapasitesini arttırmaktan daha kolay olduğu durumlarda tercih edilmektedir. Özellikle cloud ortamlarda kolaylıkla gerçekleştirilebilmektedir. Ayrıca vertical scaling ile erişilebilecek maksimum bir kapasite olduğu için, bir noktadan sonra horizontal scaling yapılması zorunlu hale gelmektedir. Ayrıca, düşük maliyetli sunucular ile kapasitenin arttırımı ve availability açısından da avantaj sağlamaktadır. Ancak bu tarz bir yaklaşım için, uygulamanın uygun bir mimari ile geliştirilmiş olması gerekmektedir.

Scaling Performans Sorunlarını Çözebilir mi?

Temel olarak en basit çözüm, mevcut sunucu donanımının arttırılması (vertical scaling) ile kapasitenin yükseltilmesidir. Ancak bu yöntem belirli bir noktadan sonra oldukça pahalıya mal olmaya başlayacağı için, uygun bir mimari ile desteklenen yeni nodelara ihtiyaç duyulmaktadır.

Ancak çoğu zaman performans sorunları scale ile ilişkili olmamaktadır. Özellikle, yeterince yük altındaki iken sistem kaynaklarının tam olarak kullanılamaması senkronizasyon sorunlarına güzel bir örnek olmaktadır. Örneğin, ortak kullanımda olan bir I/O yada veri bu tarz sorunlara güzel birer örnek olmaktadır. Bu durumda, yeni donanım/kaynak eklenmesi sistemin performansını/kapasitesini maalesef ki arttıramayacaktır.

Vaka Analizi: Stok güncelleme işi yapan bir yazılım düşünelim. Eğer ki tüm stoğun eş zamanlı ve tutarlı olarak güncellenmesi isteniyor ise, herhangi bir anda en fazla bir process bu update işlemi için çalışabilecektir (syncronization).  Bu işlemin süresi, örneğin 200ms, uygulamanın performans limitlerini ortaya koyacaktır. Eklenecek kaynak ve donanımdan bağımsız, uygulama performans limiti saniyede beş işlem olacaktır. Eğer daha yüksek bir throughput değerine ulaşılmak isteniyor ise, scaling (donanım yada sunucu eklenmesi) yerine toplam performansın iyileştirilmesi gerekmektedir. Bu durumda, sql yada uygulama kodlarının optimizasyonu, hatta gerçek zamanlı tutarlılıktan vazgeçilmesi dahi gerekli olabilmektedir.
Referanslar:

Improving .Net Application Scalability – Architecture and Design Review of a .Net Application for Performance and Scalability, Microsoft

Dynatrace: Java Enterprise Performance Book

Oracle Java Tutorials: Syncronized Methods