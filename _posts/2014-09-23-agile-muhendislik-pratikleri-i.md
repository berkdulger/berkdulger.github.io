---
title:  "Agile Mühendislik Pratikleri - I"
date:   2014-09-23 11:16:01 -0600	
categories:
  - Tech
  - Agile
  - Engineering Practices
header:
    image: skyscrapers_blue_sky-wallpaper-1920x1080.jpg
---

IT, özellikle yazılım geliştirme dünyasındaki herkes hayatında en az bir kez “Agile” yada “Çevik” kelimesini duymuştur eminim ki. Hatta birçok kişi bu havalı! sözcüğün büyüsüne kapılıp, “Agile” olmak için kolları sıvamıştır. Scrum, XP gibi konuları araştırmış, eğitimlere katılmış, hatta denemeler yapmış olanlarımızın sayısı hiç de azımsanmayacak oranlardadır büyük ihtimalle.

2001'de Agile Manifesto ile ortaya konulmuş bu kavram ile süreç yaklaşımından, ürün yaklaşımına geçilerek gerçek manasıyla iş üretmeye odaklanılmak istenmiştir. Ya da moda tabiri ile bu yaklaşıma, çıktıdan çok sonuca odaklanmak da diyebiliriz (Outcomes over outputs). Bunu yaparken de ağır dokümantasyonlar, sözleşmeler ve uzun süreçler yerine mümkün olduğunca kısa süreli release’ler ile müşteri taleplerinin karşılanmaya çalışılması tavsiye edilmiştir. Konunun özeti aşağı yukarı bu şekilde olmakla birlikte büyük ihtimalle şimdiye kadar yapılmış en iyi Agile metodoloji tanımlaması da değildir.


Ancak, zaten amacım da Agile kavramını tanımlamaya çalışmakdan ziyade, Agile yaklaşımlar ile neden istenilen sonuçların alınamadığını yorumlamaya çalışmak. Bu noktada da biraz geriye giderek, Agile metodolojilerin temel öğelerinden bahsedeceğim.
İlerleyen yıllarda da Scrum, XP, Lean, Kanban gibi frameworkler ile bu prensiplere hayat verilmeye çalışılmıştır. Aslına baktığımızda safkan olarak “Agile” diyebileceğimiz bir pratikler bütünü bulunmamakta, Agile prensipleri uygulamak isteyenlerin var olan frameworklerden birini kullanması gerekmektedir.


Bu frameworklerin de “Management-Related” ve “Engineering-Related” olarak ikiye ayrılması oldukça uygun olacaktır. Öyle ki Scrum yönetimsel frameworklerin en popüler olanlarından biriyken, Xtreme Programming mühendislik frameworklerinin en bilinenlerindendir.

Hal böyle olunca, özellikle ülkemizde yaşadığımız “Yönetici Olma” eğilimi nedeniyle (Bu arada bir mühendis olarak, mühendislerin yönetici olma isteklerini oldukça iyi anlıyor ve pek çok açıdan katılıyorum) ya da belki de terazinin diğer tarafındaki unsurların pek iyi bilinmemesi nedeniyle, Agile denildiğinde herkesin aklına Scrum ya da son yıllarda popüler olan Lean, Kanban yaklaşımları geliyor. Çok kimsenin aklına ne “Continuous Integration”, ne “Version Control” ne de “Automated Provisioning” gibi kavramların gelmediğini danışmanlık verdiğim birçok projede bizzat tecrübe ettim.


Bu şekilde gerçekleştirilmeye çalışılan Agile dönüşüm projelerinde de, hal böyle olunca, kaçınılmaz olarak, nedeni ortak bir köke uzanan çok çeşitli sorunlar yaşanıyor.

![Delivery Pipeline](https://berkdulger.github.io/images/DeliveryPipeline.jpg)