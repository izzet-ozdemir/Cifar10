# Cifar10 Projesi

Bu çalışmada Aygaz sponsorluğunda Global AI Hub tarafından düzenlenen "Yapay Zekaya Giriş" bootcamp bitirme projemi bulacaksınız. Projemde bir CNN modeli oluşturdum ve TensorFlow/Keras ile eğitimini gerçekleştirdim. Veri seti olarak Cifar10 
kullanarak CNN modelimi inceledim. 

CIFAR-10 veri seti 32x32 boyutunda renkli küçük görüntülerden oluşmaktadır. Veri seti 10 sınıf içermektedir ve sınıf başına 6.000 olmak üzere toplamda 60.000 görüntüden oluşmaktadır. Bunların 50.000’i eğitim, 10.000’i test için kullanılmaktadır. CIFAR-10 Veri seti şu sınıfları içermektedir:
* Uçak
* Otomobil
* Kuş
* Kedi
* Geyik
* Köpek
* Kurbağa
* At
* Gemi
* Tır

Veri seti aşağıdaki işlemlere tabi tutumuştur:
* Gerekli olan kütüphanelerin yüklenmesi
* Veri ön işleme 
* Veri Görselleştirme
* Normalizasyon
* Model oluşturma
* Model eğitimi
* Model sonuçlarının tespiti
* RMSprop ve ADAM optimizer karşılaştırması
* Proje Değerlendirilmesi


Optimizasyon algoritmaları, modelin kayıp fonksiyonunu minimize ederek modelin daha iyi performans göstermesini sağlar. Bu çalışmada RMSprop ve ADAM optimizer ları karşılaştırılarak, aynı koşullarda hangisinin daha iyi sonuç verdiği incelenmiştir.
* Adam algoritması, eğitim boyunca öğrenme oranını ayarlar. Öğrenme oranı, model için optimal ağırlıkların ne kadar hızlı hesaplandığını belirler.
* RMSprop, her bir parametrenin öğrenme oranını ayarlamak için gradientlerin karelerini almak yerine karesel gradyanın hareketli ortalamasını kullanan bir optimizasyon algoritmasıdır. Bu sayede parametre değişimlerindeki dağılımların önüne geçilir ve bazı durumlarda da yakınsamayı oldukça iyileştirebilir.

RMSprop optimizer eğitimli test sonuçlarına baktığımızda loss ve acc olarak training ve validation sonuçlarının birbirine paralellik gösterdiğini ve dengeli ve aşarılı bir çalışma olduğu söyleyebiliriz.
Loss değerinin epoch sayısı arttıkça düştüğü görülmektedir. Buna karşılık acc değeri de düzenli bir şekilde artmaktadır. Epoch değeri 30 olarak test edilsede daha önce yapılan çalışmalarda epoch değeri 50 olarak test edilmiş ve daha iyi sonuçların alındığı gözlenmiştir.

Adam optimizer sonuçları incelendiğinde hem loss hemde acc değerlerinin traing ve validation sonuçlarının 15 ile 20 epoch arasında kesiştiği gözlenmiştir. Bu bir over-fitting durumu olarak nitelendirilmektedir. Bu nedenle eğitimin belirtilen epoch noktalarının uygun görülen kısmında durdurulmasında fayda vardır.


