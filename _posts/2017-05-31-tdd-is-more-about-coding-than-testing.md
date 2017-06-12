---
title:  "TDD is more about Coding than Testing"
date:   2017-05-31 10:16:01 -0600
categories:
  - Test-Driven Development
  - Software Development
  - Software Engineering
  - Software Craftsmanship
header:
    image: work-731198_1920-1.jpg
---

..TDD veya temel olarak Unit Testler, yazılımdaki herhangi bir değişiklik sonrasında oluşabilecek regresyon etkisini tespit etmede düşündüğümüz kadar etkili olmayabilir! Zira, Unit Test'ler dış etkenlerden bağımsız olarak, metotların işlevini doğruladıkları için diğer modüllerle bütün olarak doğru çalışıp çalışmama konusunda yeterince bilgi sağlayamazlar. Ancak değiştirilen metodun eski işlevini hala yerine getirdiğinden emin olmamızı sağlayabilirler. İşin kötü kısmı çoğu zaman var olan metotları yeniden tasarlamak yerine, yenilerini yazmayı tercih etmemiz (Bu ayrı bir yazı konusu). Bu durumda unit testlerin regresyon hatalarının tespiti tarafındaki faydası daha da azaltmakta.

<b>TDD vs Unit Testing</b>

TDD ve Unit Test'i birebir olarak karşılaştırmak çok da doğru değil. TDD bir yazılım geliştirme aktivitesi iken, Unit Testler'in sürecin (TDD veya TFA) çıktısı olarak değerlendirilebilir.

<c>Test-Driven Development = Test First Approach + Refactoring</b>

TDD'yi refactoring olmadan düşünmemiz yanlış olacaktır. TDD birincil hedef olarak, yazılımcının kodlamaya başlamadan önce tasarıma odaklanmasını sağlayarak, daha yalın, rafine (SOLID Principle) ve en sonunda refactor edilmiş kodlar üretmesini desteklemektedir. Sürecin çıktısı olarak üretilen testler ise ikincil hedef kapsamında regresyon kontrolleri için kullanılabilir.

>"The act of writing a unit test is more an act of design than verification" (Robert C Martin, author of Agile Software Development, Principles, Patterns, and Practices)"

<b>Legacy Code Unit Testing</b>

Bu konudaki en önemli sorunlardan birinin de "hali hazırda canlıda hizmet vermekte olan bir yazılıma unit test yazılıp, yazılmaması kararı" olduğunu söyleyebiliriz. Bu durumda unit testleri yazmaya karar veren birçok yazılımcının kısa bir süre içerisinde bundan vazgeçtiklerini gözlemlemişsinizdir. Yarım bırakılan her iş de olduğu gibi, önemli bir motivasyon kaybına neden olmaktadır. Aslına bakılırsa, kişisel olarak bu yarım bırakma durumun o kadar da büyük bir başarısızlık göstergesi olmadığı kanısındayım.

Bu düşüncenin temel dayanağı ise, devreye alınmış bir sistemin artık belirli bir olgunluğa erişmiş ve temel modüllerinin değişim frekansının oldukça azalmış olması. Yani kullanımda olan bir uygulamanın metotlarının artık çok fazla değişmiyor oluşu. Yeni eklenen metotların doğru çalıştığının kontrolünün ise Entegrasyon ve Sistem Testleri ile mümkün olması. Bu nedenle canlıda olan bir yazılıma, sonradan unit test'lerin yazılmaya başlanması(mevcut kodlar için) fayda/maliyet dönüşünü çok sonra gerçekleştirmekte veya hiç gerçekleştirememektedir.

Canlıda olan bir yazılıma unit testler eklemek isterseniz, ki bunu tavsiye ederim, yeni kodladığınız kısımlar için gerçekleştirmeniz faydalı olacaktır. TDD ile de taçlandırabilirsiniz! Bu sayede oldukça iyi bir denge oluşturmuş olacaksınız.

Sonuç olarak, unit testler birçok nedenden ötürü sıfırdan geliştirilen projeler için çok daha verimli sonuçlar üretirken, legacy kod için bu durum tersi bir niteliğe sahip.

Konu ile ilgili faydalı olabilecek, önemli kitaplar;

Kent Beck, Test Driven Development: By Example. 2002.
Gojko Adzic, Specification by Example: How Successful Teams Deliver the Right Software, 2011
Scott W. Ambler, Disciplined Agile Delivery, 2012
LikeTDD is more about Coding than TestingCommentShareShare TDD is more about Coding than Testing




