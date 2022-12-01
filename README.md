# Makine Öğrenmesine Giriş Dersi Ödev Raporu

## İçindekiler
* Denetimli Öğrenme
    - Sınıflandırma
* Destek Vektör Makineleri
    - DVM Tarihi
    - DVM Nedir?
    - DVM Çalışma Mantığı Nedir?
        - Hiperdüzlem ve Destek Vektörleri
        - Keskin Kenar Payı Yaklaşımı
        - Esnek Kenar Payı Yaklaşımı
        - Çok Sınıflı Verinin DVM İle Sınıflandırılması
    - Avantajları Ve Dezavantajları
* Doğrusal Ve Doğrusal Olmayan DVM
    - Doğrusal DVM
    - Doğrusal Olmayan DVM
    - Çekirdek Fonksiyonları
    - Çekirdek Hilesi
* Kullanım Alanları Ve Örnekleri
* Kaynakça

## Denetimli Öğrenme
Denetimli öğrenme, makine öğrenme uygulamalarında çok sık kullanılan yöntemlerden birisidir. Giriş-çıkış verileri arasında kesin bir bağıntının olduğu veriler için yaygın olarak kullanılan yöntemlerdendir. Bu yöntemde kullanılan verilerin tümünün etiketli veri olması gerekmektedir. Eğitim aşamasında, bu etiketli verilerin büyük bir kısmı sistemi eğitmek, diğerleri de test etmek için kullanılır. Denetimli öğrenme modelleri, temel olarak sınıflandırma ve regresyon uygulamalarında kullanılmaktadır.

### Sınıflandırma
Genel olarak veri setindeki verileri, önceden belirlenen etiketlere uygun olarak ayrılması işlemine sınıflandırma denilmektedir. Destek vektör makineleri de sınıflandırma algoritmalarından biridir.

## Destek Vektör Makineleri

### Tarihi
1963 yılında Vladimir Vapnik ve Alexey Chervonenkis tarafından temelleri atılan “Destek Vektör Makineleri (DVM)” istatiksel öğrenme teorisine dayalı bir gözetimli öğrenme algoritmasıdır. Her ne kadar temelleri 60'lı yıllara dayansada 1995 yılında Vladir Vapnik, Berhard Boser ve Isabelle Guyon tarafından geliştirilmiştir.

### Destek Vektör Makineleri Nedir?
Destek vektör makineleri genellikle sınıflandırma problemlerinde kullanılan gözetimli öğrenme yöntemlerinden biridir. Hem doğrusal hem de doğrusal olmayan sınıflandırma işlemlerini gerçekleştirilebilmektedir. Destek vektör makinesi, eğitim verilerindeki herhangi bir noktadan en uzak olan iki sınıf arasında bir karar sınırı bulan vektör uzayı tabanlı makine öğrenme yöntemi olarak tanımlanabilir.

### Destek Vektör Makinelerinin Çalışma Mantığı Nedir?
DVM algoritmasının amacı, gelecekte yeni veri noktasını doğru kategoriye kolayca yerleştirebilmemiz için n-boyutlu uzayı sınıflara ayırabilecek en iyi çizgiyi veya karar sınırını oluşturmaktır.

![](https://miro.medium.com/max/640/1*OGs3M3e9zPDfRaVx2BRoPg.png)

Sınıflandırmayı yapabilmek için iki sınıfı ayıran bir doğru çizilir ve bu doğrunun ±1'i arasında kalan yeşil bölgeye Margin adı verilir. Margin ne kadar geniş ise iki veya daha fazla sınıf o kadar iyi ayrıştırılır.

#### Formül İle Gösterimi
![](https://miro.medium.com/max/640/1*vFJs39qUz-VIuanwxCqPcg.png)
> w; ağırlık vektörü
> x; girdi vektörü
> b; sapmadır 

#### DVM Algoritmasında Hiperdüzlem ve Destek Vektörleri:

**Hiperdüzlem :** n-boyutlu uzayda sınıfları ayırmak için birden fazla çizgi/karar sınırı olabilir. Ancak veri noktalarını sınıflandırmaya yardımcı olan en iyi karar sınırını bulmamız gerekir. Bu en iyi sınır, SVM'nin hiper düzlemi olarak bilinir. Her zaman, veri noktaları arasındaki maksimum mesafe anlamına gelen maksimum kenar boşluğuna sahip bir hiper düzlem oluştururuz. 

**Destek Vektörleri :** Hiper düzleme en yakın olan ve hiper düzlemin konumunu etkileyen veri noktaları veya vektörler, Destek Vektörü olarak adlandırılır. Bu vektörler hiperdüzlemi desteklediği için Destek vektörü olarak adlandırılır.

![](https://static.javatpoint.com/tutorial/machine-learning/images/support-vector-machine-algorithm.png)


#### Keskin Kenar Payı Yaklaşımı:
Keskin kenar payı yaklaşımı aykırı değerlere karşı çok duyarlıdır. 

#### Esnek Kenar Payı Yaklaşımı:
Esnek kenar payı yaklaşımı, keskin kenar payındaki gibi sıfır sınıflandırma hatası yerine bazı örneklerin karşı sınıfta yer almasına izin verme mantığına dayanır.Esnek kenar payı kullanılarak yapılan sınıflandırmada kenar payının çok artması hatalı sınıflandırılan örnek sayısını arttırır.En iyi sınıflandırmayı elde etmek için Esnek Sınır içinde kaç yanlış sınıflandırma ve gözleme izin verileceğini belirlemek için Cross Validation kullanılabilir.

![](https://miro.medium.com/max/640/1*yWtPGQrfiNDlcD0AJjdpiA.png)

#### Çok Sınıflı Verinin DVM İle Sınıflandırılması
Destek vektör makineleri daha çok iki sınıftan olusan (binary classification) veriyi ayırmada kullanılmaktadır. Buna karşın veriler bazen ikiden fazla sınıfa ait olabilirler bu gibi durumlarda temel DVM algoritması işlevsiz bir hale gelir.

**Bire çok yaklaşım :**  Genel anlamda sınıf sayısı kadar DVM'nin birbirine füzyonuyla elde edilir. Her DVM çıkan her bir sınıfı diğer sınıflarla karşılaştırarak bir sonuca ulaşır. Eğer N kadar sınıf varsa N sayıda DVM eğitilerek bu DVM'lerin birbiriyle kıyaslanarak hangi sınıf için en güvenilir sonucun çıktığına bakılarak sınıflandırma yapılır.

**Bire bir yaklaşım :** Bire bir yönteminde her bir sınıf ikilisi için farklı bir DVM eğitilir ve eğitilen DVM'lerden hangi sınıfın en çok "+1" olarak sınıflandırıldığına bakılır ve böylece sınıflandırma işlemi gerçekleştirilir. Bu yöntem bire çok yöntemine göre hesaplama gücü yönünden oldukça "pahalı" bir yöntemdir. Bunun sebebi, eğer N kadar sınıf varsa bu durumda  (N.(N-1))/2 sayıda DVM eğitilmesi gerekmesidir.

### DVM Avantajları
* Yüksek boyutlu uzaylarda etkilidir.
* Boyut sayısının örnek sayısından fazla olduğu durumlarda yine etkilidir.
* Karar fonksiyonunda (destek vektörleri olarak adlandırılır) eğitim noktalarının bir alt kümesini kullanır, dolayısıyla hafıza açısından da verimlidir.
* Çok yönlü: karar fonksiyonu için farklı Kernel fonksiyonları belirtilebilir. Ortak çekirdekler sağlanır, ancak özel çekirdekler belirlemek de mümkündür.

### DVM Dezavantajları
* Öznitelik sayısı örnek sayısından çok fazlaysa, Kernel fonksiyonlarını seçerken aşırı uydurmadan kaçının.
* DVM'ler doğrudan olasılık tahminleri sağlamaz, bunlar pahalı bir beş katlı çapraz doğrulama kullanılarak hesaplanır.

## Doğrusal Ve Doğrusal Olmayan DVM

## Doğrusal DVM
Doğrusal olarak ayrılabilen veriler için kullanılır.Bir veri kümesinin tek bir düz çizgi kullanılarak iki sınıfa ayrılabilmesidir.

## Doğrusal Olmayan DVM
Veriler doğrusal olarak düzenlenmişse düz bir çizgi kullanarak ayırabiliriz, ancak veri setleri her zaman bir doğru ile ayırabileceğimiz formatta olmayabilir. Eğer doğrusal olmayan veri setlerini daha yüksek bir uzayda temsil edebilirsek bir düzlem vasıtasıyla örneklerimizi birbirinden ayırarak sınıflandırma yapabiliriz.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200605170732/linearsep.png)

### Çekirdek Fonksiyonları
Veri kümesinin doğrusal olarak sınıflandırılması mümkün olmayan durumlarda, her bir verinin üst özellik uzayıyla eşlenmesi ve yine bu yeni uzayda bir hiper düzlem yardımıyla sınıflandırılması yöntemine verilen isimdir.
SVM algoritmaları, çekirdek olarak tanımlanan bir dizi matematiksel fonksiyon kullanır. Çekirdek fonksiyonları tüm zor işleri yapar. Sadece girdiyi vermeli ve uygun çekirdeği kullanmalıyız. 
* Hiper düzlemi daha yüksek boyutta oluşturmaya yardımcı olurlar.
* Karmaşık hesaplamalardan kaçınmak için kısayollar sağlarlar.
* SVM'deki overfitting problemini çözmek için kullanışlıdırlar.

![](https://vitalflux.com/wp-content/uploads/2020/07/Screenshot-2020-07-14-at-6.45.25-PM.png)

Farklı SVM algoritmaları, farklı türde çekirdek fonksiyonları kullanır.
1) Polynomial Kernel Function
* Polinom çekirdeği, birden fazla dereceye sahip çekirdeklerin genel bir temsilidir. Görüntü işleme için kullanışlıdır.
* Polinom çekirdeği, genellikle tüm eğitim verilerinin normalleştirildiği
problemler için uygundur.
* d parametresine sahiptir. d parametresi polinom derecesini ifade eder. Polinom çekirdeği, polinomun derecesi olan d'yi ayarlayarak boyutları sistematik olarak artırır.
>  $$(a x b + r)^d$$ 
2) Gaussian RBF Kernel Function
* RBF, radyal tabanlı fonksiyondur. Veriler hakkında önceden bilgi olmadığında kullanılır
* Radyal çekirdek, sonsuz boyutlarda destek vektör sınıflandırıcısını bulur.
* En yakın gözlemlerin yeni gözlemleri nasıl sınıflandıracağımız üzerinde çok fazla etkisi vardır ve daha uzaktaki gözlemlerin sınıflandırma üzerinde nispeten az etkisi vardır.
> K(xi,xj) = exp(-γ||xi – xj||)^2
3) Sigmoid Kernel Function
* Esas olarak sinir ağlarında kullanılır.
* Sigmoid çekirdek fonksiyonu birçok uygulamada iyi performans göstermektedir. Sigmoid çekirdeğinde α eğim ve c kesme sabiti olmak üzere iki ayarlanabilir parametresi vardır.
4) Linear Kernel Function
* Bu çekirdek tek boyutludur ve SVM'deki en temel çekirdek biçimidir.
5) Hyperbolic Tangent Kernel Function
* Sinir ağlarında kullanılır.
6) Graph Kernel Function
* Bu çekirdek, grafiklerin içini hesaplamak için kullanılır. Grafik çiftleri arasındaki benzerliği ölçerler. Biyoinformatik , kemoinformatik vb . alanlarda katkıda bulunurlar .
7) String Kernel Function
* Bu çekirdek, diziler temelinde çalışır. Daha çok metin sınıflandırma gibi alanlarda kullanılır . Metin madenciliğinde, genom analizinde vb. çok faydalıdırlar.
8) Tree Kernel Function
* Bu çekirdek daha çok ağaç yapısıyla ilişkilidir. Çekirdek, verileri ağaç formatına ayırmaya yardımcı olur ve SVM'nin bunlar arasında ayrım yapmasına yardımcı olur. Bu, dil sınıflandırmasında yardımcı olur ve NLP gibi alanlarda kullanılır.

### Çekirdek Hilesi
Dönüşüm gerçekleştirmeye gerek duymadan sadece girdi uzayındaki vektörlerin iç çarpımını kullanarak işlem yapılabilmektedir. Bu işlem kestirmeden bir sonuç sağladığı için çekirdek hilesi olarak ifade edilmektedir.Çekirdek hilesi, matematikten kaçınarak SVM için gereken hesaplama miktarını azaltır, verileri düşükten yüksek boyutlara dönüştürür.

## DVM Kullanım Alanları Ve Örnekleri
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
* https://iksadyayinevi.com/wp-content/uploads/2020/12/MAKINE-OGRENMESINDE-TEORIDEN-ORNEK-MATLAB-UYGULAMALARINA-KADAR-DESTEK-VEKTOR-MAKINELERI.pdf
* https://tr.wikipedia.org/wiki/Destek_vekt%C3%B6r_makinesi
* https://scikit-learn.org/stable/modules/svm.html
* https://medium.com/deep-learning-turkiye/nedir-bu-destek-vekt%C3%B6r-makineleri-makine-%C3%B6%C4%9Frenmesi-serisi-2-94e576e4223e
* https://www.youtube.com/watch?v=yW-lwgpqyIU
* https://www.youtube.com/watch?v=efR1C6CvhmE&t=12s
* https://techvidvan.com/tutorials/svm-kernel-functions/
