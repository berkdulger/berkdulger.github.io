---
title:  "Scrumban: Hibrit Çeviklik Metodolojisi"
date:   2016-02-10 10:16:01 -0600
categories:
  - Scrum
  - Kanban
  - Agile
header:
    image: scrumban_paper.png
---
Agile denince aklımıza çoğunlukla Scrum geliyor. Hatta kimi zaman bu iki kelimeyi eş anlamlı olarak kullanıyoruz. Nedeni sanırım ilk sunulan ve en çok içselleşen metodoloji olması.

Çevik yazılım geliştirme yöntemlerinin hem yönetimsel, hem de mühendislik olarak iki başlık altında düşünülmesi gerekiyor. Yönetimsel (süreç) anlamında kullanılabilecek Kanban gibi başka yöntemler de var.

Kanban birçoğumuzun bildiği gibi Toyota, Japon meşeli bir olgu. Kelime olarak ‘Kart’ anlamına geliyor. Just-in-time üretimde (Yalınlığın alametifarikası), çalışanlara fazladan yük oluşturmadan en yüksek verimi elde etmeyi hedefliyor.  

Endüstri Mühendisi Taiichi Ohno’nun imalat sektörü için geliştirdiği bu devrimci yöntemin yazılım geliştirme için de kullanılması mümkün. Kanban orijinaline benzer şekilde, yazılım alanında bazı temel prensipler üzerine oturuyor. Bunlar;

- Görselleştirme (Visualize)
- İş Limitleri (Limit WIP)
- Akış Yönetimi (Manage Flow)
- Süreçlerin Şeffaflaştırılması (Make Process Policies Explicit)
- Geri Bildirim Kanalları (Implement Feedback Loops)
- Yardımlaşmanın Artırılması ve Evrimsel Olarak İlerlenmesi (Improve Collaboratively, Evolve Experimentally)

olarak özetlenebilir. Kısaca, bu pratikleri gerçekleştirdiğiniz de Kanban kullanıyor oluyorsunuz. Bu açıdan bakıldığında Kanban, Scrum’a göre çok daha az kural ve çıktı içeriyor. İki yöntemi karşılaştıracak olursak;

![Scrum-vs-Kanban](https://berkdulger.github.io/images/scrum-vs-kanban.png "Scrum vs Kanban")

Kanban’ın Scrum’a göre daha 'çevik' olduğunu söyleyebiliriz. Sprint’lerin sonunu beklemeden tamamlanan işlerin devreye alınması, Continuous Delivery / DevOps hedefleri ile daha iyi örtüşüyor izlenimi veriyor. Ancak avantajlarının yanında, dezavantajları da var elbette.

Sosyal medyadaki tartışma gruplarında Scrum’ın yeni ürün geliştirme, Kanban’ın ise mevcut ürüne yeni özellikler eklenmesi için daha uygun olduğu fikri ağır basıyor. Bunun nedeni ise mimari ve teknik kaygılara dayanmakta. Kişisel olarak haklılık payı olduğunu düşünüyorum, nitekim oldukça tartışmaya açık bir konu. Kanban’ın ikinci belirgin dezavantajı ise tanımlı aktivitelerinin olmaması ve geliştirme ekibine kimi zaman gereğinden fazla özgürlük tanıması! Bu nedenle Kanban uygulayan birçok takım, Scrum gibi metodolojilerin nesnelerinden faydalanıyor. Esas olarak, tam olmasa da (Sprints vs Continuous Flow), bu iki yöntemin tek bir pota da eritilmesi mümkün.

<b>Scrumban</b>, adında da anlaşılacağı gibi Scrum ve Kanban’ın birleşiminden oluşturulmuş hibrit bir metodoloji (Aslında iki metodolojinin belirli kurallar çerçevesinde birleşiyor olması o kadar hoşuma gitmiyor). Kanban’ın en önemli değeri olan WIP (Work in Process) limitlerini kabul ederken, ihtiyaç duyulduğu kadar gerçekleştirilen toplantılar (Planning, Review ve Retrospection) ile zamanı optimize kullanmayı hedefliyor. Tamamlanan (ve onaylanan) her geliştirmenin canlıya çıkması sayesinde DevOps/ Minimized Cycle Time hedefine bir adım daha yaklaşılıyor.

![Scrumban](https://berkdulger.github.io/images/scrumban.png "Scrumban")

Konuyla ilgili Boğaziçi Üniversitesi’nde E. Zafer Güney ile gerçekleştirdiğimiz sunumu eklemek istedim. Sunum Scrumban/DevOps dönüşümü için değer odaklı bir dönüşüm yöntemi olarak geliştirmeye başladığımız “DevOps Tactical Adoption Theory” ile ilgili ön bilgilere de yer veriyor.

<center>
<iframe src="//www.slideshare.net/slideshow/embed_code/key/9CaEeErPESPY9u" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/BerkDlger/lean-enterprise-a-definitive-approach-in-software-development-production-58116825" title="Lean Enterprise, A Definitive Approach in Software Development Production" target="_blank">Lean Enterprise, A Definitive Approach in Software Development Production</a> </strong> from <strong><a target="_blank" href="//www.slideshare.net/BerkDlger">Berk Dülger</a></strong> </div>
</center>