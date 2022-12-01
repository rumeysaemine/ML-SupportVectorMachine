# Makine Öğrenmesine Giriş Dersi Ödev Raporu
## Destek Vektör Makineleri
## İçindekiler
* Destek Vektör Makineleri Nedir?
* Çalışma Mantığı Nedir?
* Kullanım Alanları
* Örnekleri

## Tarihi
1963 yılında Vladimir Vapnik ve Alexey Chervonenkis tarafından temelleri atılan “Destek Vektör Makineleri (DVM)” istatiksel öğrenme teorisine dayalı bir gözetimli öğrenme algoritmasıdır. Her ne kadar temelleri 60'lı yıllara dayansada 1995 yılında Vladir Vapnik, Berhard Boser ve Isabelle Guyon tarafından geliştirilmiştir.

## Destek Vektör Makineleri Nedir?
Destek vektör makineleri genellikle sınıflandırma problemlerinde kullanılan gözetimli öğrenme yöntemlerinden biridir. Hem doğrusal hem de doğrusal olmayan sınıflandırma işlemlerini gerçekleştirilebilmektedir. Destek vektör makinesi, eğitim verilerindeki herhangi bir noktadan en uzak olan iki sınıf arasında bir karar sınırı bulan vektör uzayı tabanlı makine öğrenme yöntemi olarak tanımlanabilir.

## Destek Vektör Makinelerinin Çalışma Mantığı Nedir?

### Keskin Kenar Payı Yaklaşımı:
Keskin kenar payı yaklaşımı aykırı değerlere karşı çok duyarlıdır. 

### Esnek Kenar Payı Yaklaşımı:
Esnek kenar payı yaklaşımı, keskin kenar payındaki gibi sıfır sınıflandırma hatası yerine bazı örneklerin karşı sınıfta yer almasına izin verme mantığına dayanır.Esnek kenar payı kullanılarak yapılan sınıflandırmada kenar payının çok artması hatalı sınıflandırılan örnek sayısını arttırır.En iyi sınıflandırmayı elde etmek için Esnek Sınır içinde kaç yanlış sınıflandırma ve gözleme izin verileceğini belirlemek için Cross Validation kullanılabilir.

## Doğrusal DVM
Doğrusal olarak ayrılabilen veriler için kullanılır.Bir veri kümesinin tek bir düz çizgi kullanılarak iki sınıfa ayrılabilmesidir.

## Doğrusal Olmayan DVM
Veriler doğrusal olarak düzenlenmişse düz bir çizgi kullanarak ayırabiliriz, ancak veri setleri her zaman bir doğru ile ayırabileceğimiz formatta olmayabilir. Eğer doğrusal olmayan veri setlerini daha yüksek bir uzayda temsil edebilirsek bir düzlem vasıtasıyla örneklerimizi birbirinden ayırarak sınıflandırma yapabiliriz.

### Çekirdek Fonksiyonları
Veri kümesinin doğrusal olarak sınıflandırılması mümkün olmayan durumlarda, her bir verinin üst özellik uzayıyla eşlenmesi ve yine bu yeni uzayda bir hiper düzlem yardımıyla sınıflandırılması yöntemine verilen isimdir.
SVM algoritmaları, çekirdek olarak tanımlanan bir dizi matematiksel fonksiyon kullanır. Çekirdek fonksiyonları tüm zor işleri yapar. Sadece girdiyi vermeli ve uygun çekirdeği kullanmalıyız. 
* Hiper düzlemi daha yüksek boyutta oluşturmaya yardımcı olurlar.
* Karmaşık hesaplamalardan kaçınmak için kısayollar sağlarlar.
* SVM'deki overfitting problemini çözmek için kullanışlıdırlar.

Farklı SVM algoritmaları, farklı türde çekirdek fonksiyonları kullanır.
1) Polynomial Kernel Function
2) Gaussian RBF Kernel Function
3) Sigmoid Kernel Function
4) Linear Kernel Function
5) Hyperbolic Tangent Kernel Function
6) Graph Kernel Function
7) String Kernel Function
8) Tree Kernel Function

### Çekirdek Hilesi
Dönüşüm gerçekleştirmeye gerek duymadan sadece girdi uzayındaki vektörlerin iç çarpımını kullanarak işlem yapılabilmektedir. Bu işlem kestirmeden bir sonuç sağladığı için çekirdek hilesi olarak ifade edilmektedir.Çekirdek hilesi, matematikten kaçınarak SVM için gereken hesaplama miktarını azaltır, verileri düşükten yüksek boyutlara dönüştürür.


## DVM Avantajları
•	Overfitting (aşırı öğrenme) sorunu olmaz
•	Yüksek doğruluk
•	Çok sayıda bağımsız değişkenler çalışabilir.
•	Karmaşık sınırları modelleme
•	Yüksek boyutlu uzaylarda etkilidirler.
•	Boyut sayısının, örneklem sayısından fazla olduğu durumlarda etkilidirler.
•	Karar fonksiyonunda bir takım eğitim noktaları kullanılır (“support vectors”). Dolayısıyla bellek verimli bir şekilde kullanılmış olur.
•	Çok yönlü: Karar fonksiyonu için çok farklı çekirdek fonksiyonları (“kernel functions”) kullanılabilmektedir.

## DVM Dezavantajları
• Sınıf olasılığı üretememe.
• Çekirdek fonksiyonları pozitif tanımlı sürekli fonksiyon olmalı.

## DVM Kullanım Alanları
### Yüz Algılama : 
Görüntünün bölümleri yüz ve yüz olmayan bölümler olarak sınıflandırılır. NxN boyutundaki bir görüntüde her bir piksel değeri yüz ve yüz olmayan bölümler olarak iki farklı etiketle etiketlenir. Bu veriler eğitim verilerini oluşturur. Sonrasında piksel parlaklığına göre yüzlerin etrafında bir karesel sınır oluşturulur ve her bir görüntü için aynı işlem tekrar edilerek, DVM ile sınıflandırma işlemleri gerçekleştirilir.
### Metin ve Köprü Metni Sınıflandırma : 
Metin ve köprü metinlerin sınıflandırılması DVM ile gerçekleştirilebilir. Bu işlem için ilk olarak metinleri; haber makaleleri, e-postalar ve web sayfaları gibi farklı kategorilerde sınıflandırmak için eğitim verileri kullanılır. Sonraki adımda her belge için bir puan hesaplanır. Hesaplanan değer önceden tanımlanmış bir eşik değeriyle karşılaştırılır. Bir metnin puanı belirlenen eşik değerini aştığında, metin belirli bir kategoride sınıflandırılır. Eşik değerini geçmezse, genel bir metin olarak değerlendirir. Her metin için puan hesaplanarak ve öğrenilen eşikle karşılaştırılarak yeni örneklerin sınıflandırılması gerçekleştirilir.
### Görüntülerin Sınıflandırılması:
DVM'ler, görüntüleri daha yüksek arama doğruluğu ile sınıflandırabilir. Doğruluğu, geleneksel sorgu tabanlı ayrıntılandırma şemalarından daha yüksektir. 
### Biyoinformatik:
Hesaplamalı biyoloji alanında, protein homoloji tespiti yaygın bir problemdir. Bu problemi çözmek için kullanılan en etkili yöntemlerden birisi de DVM yöntemidir. Bu yöntem, biyolojik diziler arasında tanımlama yapmak için yaygın olarak kullanılmaktadır.
### Protein kıvrımı ve uzaktan homoloji tespiti:
Protein uzaktan homoloji tespiti için SVM algoritmalarını uygulayın.
### El Yazısı Tanıma:
Literatürde belgeler üzerindeki imzaları ve elle yazılmış karakterleri tanımak için DVM yöntemleri kullanılmaktadır.
### Jeoleji ve Çevre Bilimleri:
DVM'ler coğrafi (mekansal) ve mekansal-zamansal çevresel veri
analizi ve modelleme işlemleri içinde kullanılmaktadır. Özellikle uydu görüntüleri üzerinden haritalama uygulamalarında da kullanılmaktadır. 

## Kaynakça




