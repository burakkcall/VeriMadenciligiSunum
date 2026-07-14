# Veri Madenciliği Dönem Ödevi

* **17/05/2022** Veri Madenciliği dersi - Dr. Öğr. Üyesi Caner ERDEN
* Burak Talha YILMAZ - G180102058
* Burak ÇALIŞKAN - G170102001
* Abdul Rahman KASEM - G180102055
* *Dinlediğiniz için teşekkürler...*

---

### Konu:
* **Veri Setine Göre Suyun İçilip İçilememesi Üzerine Makine Öğrenmesi Uygulaması**

---

## İÇİNDEKİLER

1. **[1- Problemin Açıklanması](#1--problemin-açıklanması)**
2. **[2- Veri Setinin Tanımlanması](#2--veri-setinin-tanımlanması)**
   * [2.1- Kütüphanelerin Tanımlanması](#21--kütüphanelerin-tanımlanması)
   * [2.2- Veri Setinin tanımlanması](#22--veri-setinin-tanımlanması)
3. **[3- Veri Manipülasyonu](#3--veri-manipülasyonu)**
   * [3.1- Aykırı Veri Tespiti ve İşleme](#31--aykırı-veri-tespiti-ve-işleme)
   * [3.2- Aykırı Verilerden Arınmış Veri Setinin Korelasyon tablosu](#32--aykırı-verilerden-arınmış-veri-setinin-korelasyon-tablosu)
4. **[4- Karar Ağacı Yöntemiyle Makine Öğrenmesi Uygulaması](#4--karar-ağacı-yöntemiyle-makine-öğrenmesi-uygulaması)**
   * [4.1- Karar Ağacı Uygulaması ile Makine Öğrenmesi Sonuçları](#41--karar-ağacı-uygulaması-ile-makine-öğrenmesi-sonuçları)

---

## 1- Problemin Açıklanması

Güvenli içme suyuna erişim, sağlık için esastır, temel bir insan hakkıdır ve sağlığın korunmasına yönelik etkili politikaların bir bileşenidir. Bu, ulusal, bölgesel ve yerel düzeyde bir sağlık ve kalkınma sorunu olarak önemlidir. Bazı bölgelerde, su temini ve sanitasyona yapılan yatırımların, olumsuz sağlık etkilerindeki ve sağlık bakım maliyetlerindeki azalmalar, müdahaleleri üstlenme maliyetlerinden daha ağır bastığı için net bir ekonomik fayda sağlayabileceği gösterilmiştir.

### 1.1- pH:
pH, suyun asit-baz dengesini değerlendirmede önemli bir parametredir. Aynı zamanda su durumunun asidik veya alkali durumunun göstergesidir. DSÖ, izin verilen maksimum pH sınırını 6,5 ila 8,5 arasında tavsiye etmiştir. Mevcut araştırma aralıkları, WHO standartları aralığında olan 6.52–6.83'tür.

### 1.2- Sertlik (Hardness):
Sertlik esas olarak kalsiyum ve magnezyum tuzlarından kaynaklanır. Bu tuzlar, suyun içinden geçtiği jeolojik tortulardan çözülür. Suyun sertlik üreten malzeme ile temas ettiği süre, ham suda ne kadar sertlik olduğunu belirlemeye yardımcı olur. Sertlik başlangıçta suyun Kalsiyum ve Magnezyum tarafından oluşturulan sabunu çökeltme kapasitesi olarak tanımlanıyordu.

### 1.3- Katılar (Solids):
Su; potasyum, kalsiyum, sodyum, bikarbonatlar, klorürler, magnezyum, sülfatlar vb. gibi çok çeşitli inorganik ve bazı organik mineralleri veya tuzları çözme yeteneğine sahiptir. Bu mineraller, suyun görünümünde istenmeyen tat ve seyreltik renk üretirler. Bu, su kullanımı için önemli bir parametredir. 

TDS değeri yüksek olan su, suyun yüksek oranda mineralize olduğunu gösterir. TDS için istenilen limit **500 mg/l**, maksimum limit ise içme amaçlı **1000 mg/l**'dir.

### 1.4- Kloraminler (Chloramines):
Klor ve kloramin, kamu su sistemlerinde kullanılan başlıca dezenfektanlardır. Kloraminler en yaygın olarak, içme suyunu arıtmak için klora amonyak eklendiğinde oluşur. Litre başına **4 miligrama kadar** (mg/l veya milyonda 4 kısım (ppm)) klor seviyeleri içme suyunda güvenli kabul edilir.

### 1.5- Sülfat (Sulfate):
Sülfatlar; minerallerde, toprakta ve kayalarda bulunan, doğal olarak oluşan maddelerdir. Ortam havasında, yeraltı suyunda, bitkilerde ve yiyeceklerde bulunurlar. Sülfatın başlıca ticari kullanımı kimya endüstrisindedir. 

Deniz suyundaki sülfat konsantrasyonu litre başına yaklaşık **2.700 miligramdır (mg/L)**. Bazı coğrafi bölgelerde çok daha yüksek konsantrasyonlar (1000 mg/L) bulunmasına rağmen, çoğu tatlı su kaynağında **3 ila 30 mg/L** arasında değişir.

### 1.6- İletkenlik (Conductivity):
Saf su, iyi bir elektrik akımı iletkeni değil, iyi bir yalıtkandır. İyon konsantrasyonundaki artış suyun elektriksel iletkenliğini artırır. Genel olarak, sudaki çözünmüş katıların miktarı elektriksel iletkenliği belirler. 

Elektriksel İletkenlik (EC), aslında akımı iletmesini sağlayan bir çözeltinin iyonik sürecini ölçer. WHO standartlarına göre EC değeri **400 μS/cm**'yi geçmemelidir.

### 1.7- Organik Karbon (Organic_Carbon):
Kaynak sularındaki Toplam Organik Karbon (TOC), sentetik kaynakların yanı sıra çürüyen doğal organik maddelerden (NOM) gelir. TOC, saf sudaki organik bileşiklerdeki toplam karbon miktarının bir ölçüsüdür. US EPA'ya göre TOC olarak arıtılmış / içme suyunda **< 2 mg/L** ve arıtma için kullanılan kaynak suyunda **< 4 mg/Lit** olmalıdır.

### 1.8- Trihalometanlar (Trihalomethanes):
THM'ler, klor ile işlenmiş suda bulunabilen kimyasallardır. İçme suyundaki THM konsantrasyonu; sudaki organik madde düzeyine, suyu arıtmak için gereken klor miktarına ve arıtılan suyun sıcaklığına göre değişir. **80 ppm**'ye kadar olan THM seviyeleri içme suyunda güvenli kabul edilir.

### 1.9- Bulanıklık (Turbidity):
Suyun bulanıklığı, askıda halde bulunan katı madde miktarına bağlıdır. Suyun ışık yayma özelliklerinin bir ölçüsüdür ve test, kolloidal maddeye göre atık deşarjının kalitesini belirtmek için kullanılır. Mondo Genet Kampüsü (**0.98 NTU**) için elde edilen ortalama bulanıklık değeri, WHO tarafından tavsiye edilen **5.00 NTU** değerinden düşüktür.

### 1.10- İçilebilirlik (Potability):
Suyun insan tüketimi için güvenli olup olmadığını gösterir; burada **1** içilebilir ve **0** içilmez anlamına gelir.

---

## Kaynaklar
* **Veri Seti Kaynak:** [Kaggle - Water Potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability)
* **Görsel Kaynak:** [Outlook India](https://images.outlookindia.com/public/uploads/articles/2021/3/20/world-water-day-702x336.jpg)
