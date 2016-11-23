---

[header-image-post]: pexels-photo-213078.jpg

title: Behavior-Driven Development, Concept
date: 2016-11-01 00:00:00 Z
categories:
- blog
tags:
- Behavior-Driven Development
- " Agile"
- " DevOps"
layout: single
---

Yazılım projelerinde analiz dokümanlarının güncel tutulamaması en bilinen sorunlardan. Sürekli değişen isteklere ayak uydururken, bir yandan bu istekleri yazılı hale dönüştürebilmek büyük bir özveri gerektiriyor. Nitekim birçoğumuzda bu özveriyi göster(e)miyoruz. Ve günün sonunda elimizdeki en güncel kaynak, kodun kendisi oluveriyor.

BDD (Behavior-Driven Development) dokümantasyon güncelliği ve benzeri sorunlara kesin çözümler üretmese de, hafifletmek adına bize oldukça yardımcı oluyor.

> BDD görece olarak oldukça yeni bir kavram. Dan North'un 2006 yılında yayınladığı bir makale ile konuşulmaya başlıyor ve sonrasında geliştirdikleri JBehave ve RSpec ile hayat buluyor.

Temel olarak BDD yaklaşımı ile sağlanılmak istenilen, yazılımdan beklenilen davranışları modelleyerek, paydaşlar arasında bir iletişim kanalı oluşturabilmek (Fowler's Business Readable, Domain Specific Language Blog Post). Aynı zamanda yaşayan bir dokümantasyon sağlayarak, test otomasyonuna destek verebilmek. Elbette eş zamanlı olarak bakım maliyetlerini ve ek eforları minimize ederek bu hedefi gerçekleştirebilmek.

BDD üzerine kurgulandığı Test-Driven Development'ın aksine, kod parçalarını birbirinden bağımsız parçalar olarak test etmek yerine, tüm akışı uçtan uca test edebilme olanağı sağlamakta. Peki nasıl?

Aslına bakılırsa BDD’nin oldukça basit bir mantığı var. BDD ile yazılım davranışı, Gherkin formatında (i.e Gherkin for Cucumber) düz metinler halinde ifade ediliyor. Hatta ilgili story ile eşleştirilerek artifactlerin çok daha traceable olması sağlanabiliyor.

```
 Feature: Some terse yet descriptive text of what is desired
   Textual description of the business value ofthis feature
   Business rules that govern the scope of the feature
   Any additional information that will make the feature easier to understand

   Scenario: Some determinable business situation
    Given some precondition
       And some other precondition
    When some action by the actor
      And some other action
      And yet another action
    Then some testable outcome is achieved
      And something else we can check happens too
```

Gherkin dilinde hazırlanan senaryolar tercih edilen BDD framework'u ile kullanılan test otomasyon aracına mapleniyor. Bunlardan en meşhur olanları Cucumber, JBehave, Specflow, RSpec/Capybara ve Calabash denilebilir.

Özetle, Behavior-Driven Development kullanımının,

- Tasarım bakış açısı ile oluşturulan ve gerçek hayatı modelleyen isterler (Design Thinking)
- Belirlenen akışlara göre hazırlanan back-end ve test edilebilir kodlar
- İş birimlerince kurgulanabilen otomatize test senaryoları
- Güncel, yaşayan dokümantasyon
- Proje paydaşları arası etkin iletişim
- Uçtan-uca testlerin okunabilirliği ve dolaylı olarak değişiklikler sonrasında artırılmış güven

faydalarını beraberinde getireceğini söylebiliriz.

BDD'nin nasıl en doğru şekilde uygulanabileceğini öğrenmek için Gojko Adzic'in "Specification by Example" kitabını tavsiye ederim.