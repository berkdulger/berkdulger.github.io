---
title:  "Algorithm Analysis, Java vs C++"
date:   2017-03-10 10:16:01 -0600
categories:
  - Tech
  - Algorithms
  - Java
  - C++
  - Performance Analysis
  - Code Complexity
header:
    image: bokeh-cup-tea-splash.jpg
---

Birkaç ay önce gelen bir mail'da, yurtdışı merkezli oldukça bilinen bir firmanın ilk aşama olarak düzenlediği "Coding Challenge"a bir davetiye bulunuyordu. Böyle bir hedefim olmamasına rağmen, daha önce deneyimlemediğim bir şey olduğundan katılmak istedim.
 
Katılanlar bileceklerdir, bu gibi aktiviteler genellikle LeetCode, HackerRank, Gist gibi kodlama platformları üzerinden gerçekleştiriliyor. Ancak paylaşmak istediğim bu coding challenge'ın kendisinden ziyade, programlama dillerinin performansı ile ilgili bir durum.
 
>"Bu arada merak edenler için, zorlu bir challenge olduğunu belirtmek isterim :)"

Geçmişte, ünlü firmaların (Google, Amazon, Uber vb.) mülakatlarında sorduğu kodlama sorularına bu platformlar üzerinden kolayca erişilebiliyor. Ben de challenge'a katılmadan önce biraz pasımı atmak için çeşitli algoritmik ve veri yapısal problemleri çözmek istedim. Esasen online bir "Cracking the Code Interview" ortamı sağlıyorlar size. (Zaman zaman girmenizi kesinlikle tavsiye ederim)

En basitinden, en karmaşığına birçok problemle ilgili kodlama yapmanız mümkün. Bunu yaparken çok farklı programlama dillerini de kullanabiliyorsunuz. Siz çözümünüzü submit ettiğinizde, bunun geçerli bir çözüm olup olmadığını inceleyerek, bir performans analizi ile sonuçları size iletiyorlar. Zira, yurtdışındaki firmalar tarafından en çok önemsenen kriterlerden biri de çözümünüzün verimliliği (Big O Notation).

Uzun süredir Java'yı ağırlıklı olarak kullandığım için, Java'da karar kılarak alıştırmalarıma başladım. Bir süre sonra algoritma analizlerinde fark ettiğim bir durum beni oldukça şaşırttı. Zira o zamana kadar edindiğim ezberlere zıt bir görüntü oluşturuyordu. 

<b>Algorithms</b>

Örneğin bir array içerisindeki hangi iki sayının toplamının belirtilen sayıyı verdiğini çözen bir algoritma için durum bu şekildeydi. Benim Java'da kodladığım çözüm, Java çözümleri arasında ortalama bir performansa sahipti. Ancak enteresan olan C++ ile yapılan kodlamaların Java çözümler karşısında büyük bir üstünlüğünün bulunmamasıydı. Hatta zamana yayılmış çözümleri incelediğimde bazılarının performans açısından oldukça kötü olduğunu gözlemledim.

![Istatistik1](https://berkdulger.github.io/images/istatistik1.png "Istatistik1")
Elbette tüm problemler için durum bu şekilde değil. Örneğin iki list içerisindeki sayıların toplanmasını ele alan bir problemde;

![Istatistik2](https://berkdulger.github.io/images/istatistik2.png "Istatistik2")

bazı C++ çözümlerinin Java çözümlerinden daha iyi iken, bazılarının daha kötü olduğunu görebiliyoruz. Yani çok daha fazla bir standart sapmaya sahip C++ çözümleri.

Başka problemlere ait çözümleri incelediğinizde benzer durumlarla karşılaşırken, bazılarında C++ üstünlüğünü görmeniz de oldukça mümkün. Esas olarak kafamı karıştıran ise "Native bir dilin, nasıl Managed bir dilden daha yavaş olabileceği" sorusu idi.

Bunun üzerine biraz düşündükten ve araştırdıktan sonra, sorunun yazılımı geliştirenlerden kaynaklandığına ikna olmaya başladım. C, C++ gibi dillerde teorik olarak çok daha performanslı yazılım geliştirmeniz mümkünken, gerçek hayatta maalesef böyle olamıyor. Zira, nerdeyse hiçbir zaman HashMap kadar optimize bir veri yapısı kodlayamıyoruz. Ya da aslında tahmin ettiğimiz kadar iyi yönetemiyoruz memory'yi. Kısacası, eğer yaptığımızdan gerçekten emin değilsek proven teknolojilere güvenmek daha doğru bir çözüm olacak gibi görünüyor.

Bu nedenle karşımıza çıkan herhangi bir business case'i, "Bu sorun .Net veya Java ile çözülemez" demeden önce bahsedilen fenomeni göz önüne almamız oldukça mantıklı olabilir!

Umarım, ileride üniversitelerde bu konulara değinen ve bilimsel analizlerle öğrencilerine aktaran öğretim üyelerinin sayısı artar.

Kod örnekleri için ["Gist Repository"](https://gist.github.com/berkdulger) 

