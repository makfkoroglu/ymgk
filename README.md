# ymgk
Yazılım Mühendisliği Güncel Konular
# Hava Kalitesi Analizi

YMH418 Yazılım Mühendisliği Güncel Konular dersi için yaptığım veri analizi çalışması. 

## Aşama 1 - Veri Toplama

#### Amaç
Bu proje çalışmamdaki amaç tüm Türkiye'yi ve Konya ilini kapsayan bir çalışma gerçekleştirmek ve hava kalitesinin istihdam oranlarında ne gibi etkileri olduğunu tahmin etmeye çalışmak.


#### Referans Materyaller

Veri kaynağı olarak "www.havaizleme.gov.tr" kullanılmıştır.</br>
Proje çalışmasında **Python** dili kullanılmıştır.</br>
Bazı hesaplamaların ve düzenlemelerin yapılabilmesi için **pandas** ve **numpy** kütüphaneleri kullanılmıştır.</br>
Grafiklerin çizdirilebilmesi için **seaborn** ve **matplotlib** kütüphaneleri kullanılmıştır.</br>
Tahminleme modeli olarak **fbprophet** kütüphanesi kullanılmıştır.</br>
Bazı text düzenleme işlemleri için **Notepad** Kullanılmıştır.

#### Tanımlar Ve Kısaltmalar

**tur.csv**: İçerisinde 2019 yılında Türkiye'nin bütün illerine ait günlük olarak hava verilerinin bulunduğu veri seti.</br>
**konya.csv**: İçerisinde Konya iline ait 2019 yılında PM10 değerinin günlük olarak bulunduğu veri seti.</br>
**hava.py**: Türkiye'nin hava kalitesinin incelendiği ve gerekli grafiklerin oluşturulduğu python dosyası.</br>
**fbprophet.py**: Konya iline ait 2020 yılı için geleceğe yönelik veri tahmininde bununduğum python dosyası.</br>

**PM10** : Çapı 10 mikrometreden küçük maddeler.</br>
**SO2** : Kükürt Dioksit Gazı</br>
**CO** : Karbonmonoksit Gazı</br>
**NO2** : Azot Dioksit Gazı</br>
**NOX** : Azot Oksit Gazları</br>
**NO** : Azot Oksit Gazı</br>
**O3** : Ozon Gazı</br>

## Aşama 2 - Verinin Görselleştirilmesi ve Sunumu

tur.cvs veri seti toplam 25722 satır ve 9 sutundan oluşmaktadır.

Sayısal değerler olan verileri Not Defteri aracılığı ile sayı değerleri ondalık ayırmada kullanılan virgülü nokta ile kolon ayırıcı olarak kullanılan boşluk değeri virgül olarak değiştirildi ve txt uzantılı dosya csv olarak kaydedildi.


Grafikler gösterilirken özellikler şehirlere göre sınıflandırıldı. Grafikler gösterilirken en yüksek değerden en düşük değere göre listeleme yapıldı.

**PM10** Değerinin 2019 yılında şehirlere göre dağılımı.

![](images/1.png)

Boş değerleri en az olan PM10 değerinde 2019 yılında en yüksek olan 3 şehrimiz Muş, Zonguldak ve Iğdır olmuştur.

**SO2** Değerinin 2019 yılında şehirlere göre dağılımı.

![](images/2.png)

SO2 değerlerinde 2019 yılında en yüksek olan 3 şehrimiz Manisa, Ardahan ve Kahramanmaraş olarak görülmekte.

**CO** Değerinin 2019 yılında şehirlere göre dağılımı.

![](images/3.png)

Veri setimde yüksek boş değere sahip olan CO değeri olarak 2019 yılında en yüksek değere sahip 3 şehir Samsun, Bursa ve Antalya olmuştur.

**NO2** Değerinin 2019 yılında şehirlere göre dağılımı.

![](images/4.png)

NO2 değerlerinde 2019 yılında en yüksek olan 3 şehrimiz Çorum, Kayseri ve Bursa olarak görülmekte.

**NOX** Değerinin 2019 yılında şehirlere göre dağılımı

![](images/5.png)

NOX değerlerinde 2019 yılında en yüksek olan 3 şehrimiz Çorum, Bursa ve Kayseri olarak görülmekte.

**O3** Değerinin 2019 yılında şehirlere göre dağılımı.

![](images/6.png)

O3 değerlerinde 2019 yılında en yüksek olan 3 şehrimiz Hatay, Bilecik ve Isparta olarak görülmekte.

## Aşama 3 - Verinin Karakteristiklerinin Analizi

İlk olarak ele alacağım özellikler hakkında detaylı bilgi edinelim. Bu özelliklerin artıp azalmasına neyin sebep olduğunu ve değerlerin insan sağlığı için önemini aşağıya yazdım.

**PM10** = Partiküler Madde (PM10) ve çapı 10 mikrometreden küçük diğer tanecikler akciğerlere ulaşarak iltihaplanmaya ya da insanları çok olumsuz etkileyecek kalp ve akciğer hastalıklarına neden olabilirler. Oluşma sebeplerinden biri katı yakıtların içeride ve açık mahallerde veya geleneksel sobalarda yakılması sonucudur.

**SO2** = Kükürt dioksit (SO2) insanlar için doğrudan zehirleyicidir; temel olarak solunum fonksiyonlarını etkiler. Sülfürik asit ve sülfat formuna dönüşmesi durumunda insan sağlığını dolaylı olarak tehdit edebilir. Şeker endüstrisinde kullanılır. Renksiz, keskin kokulu reaktif bir gaz olan kükürt dioksit; kömür, fuel-oil gibi kükürt içeren yakıtların yanması sırasında, metal eritme işlemleri ve diğer endüstriyel işlemler sonucu oluşur. Hava kirliliği ve asit yağmurlarına neden olur.

**CO** = Karbonmonoksit, bir karbon ve bir oksijen atomundan oluşan inorganik molekülün adı. Hidrokarbonların eksik yanmalarının ürünüdür. CO oluşumunda 3 temel neden vardır:
  - Yakıt ve oksijenin yetersiz karışımı,
  - Oksijen eksikliği,
  - Alıkonma süresinin çok kısa olması.

**NO2** = Azot dioksit, NO₂, kırmızımsı kahve renkli ve zehirli bir gazdır. Keskin bir kokuya sahip olan bu gazın kokusu klor gazına benzemektedir. NO2 fosil yakıtlarının, yani Gaz, Kömür ve Yağ'ların yanması sonucunda ortaya çıkmaktadır. Böylelikle araçların atık gazlarında ve ısınmak için kullanılan gaz ve kömürün yanmasıyla bol miktarda bu gazdan doğaya salınmaktadır.

**NOX** = Azot oksitlerin ana kaynağı motorlu araçlar ve enerji üretim istasyonlarıdır. Doğal kaynaklarından birisi topraktaki organik çürümelerdir. NOx’un doğal kaynakları arasında orman yangınları, yıldırım ve topraktaki mikrobiyolojik işlemler vardır.

**NO** = Azot monoksit, kimyasal formülü NO olan bir bileşiktir. Bu gaz, -insanlar da dâhil olmak üzere memelilerin vücutlarında önemli bir sinyal molekülü olmasının yanı sıra kimyasal endüstride de önemli bir ara üründür. Ayrıca NO, araba motorları ve elektrik santralleri tarafından üretilerek hava kirliliğine neden olur.

**O3** = Üç oksijen atomundan oluşan molekülleriyle Zehirli, renksiz bir gaz. Sıvı halde lacivert rengini alır. Atmosferin üst katmanlarında yer alan ozon, dünyayı güneşten gelen morötesi radyasyona karşı korur. Ozon çok tehlikeli bir maddedir. Yeryüzünde ise gözleri, burnu ve boğazı tahriş eden ozon, solunum sistemini tahrip eder. Güneş ışığında fotokimyasal tepkimeye giren egzoz gazları, kirli havadan oluşan duman bulutlarında ozon ve nitrojen dioksit bulunur.

Özelliklerin ne olduğunu bu özelliklerin oluşmasına neyin sebep olduğunu genel olarak öğrendikten sonra ilk olarak bu özelliklerin bir birleri ile herhangi bir ilişkisi var mı yok mu bakmak için bir dağılım grafiği çizdirdim.

![](images/8.png)

## Aşama 4 - Model Kurma

Facebook tarafından geliştirilen **fbprophet** modelini kullanarak modeli kurup tahminleme yaptım. Bu modelin güçlü yanlarından biri eksik verilere karşı da dayanıklı olmasıdır. Bende verisetimin boşluklarını önceden haftalık ortalamaya göre dolduruyordum ancak bu model bu işlemi otomatik olarak düzenliyor. Kurduğum modelde trend esnekliğini varsayılan değer olan 0.05 olarak ayarladım. Günlük verilerle çalıştığım için de freq değerini “D” olarak belirledim. 

## Aşama 5 - Geleceğe Yönelik Veri Tahmini

İlk olarak verisetimi ham olarak görselleştirdim ve bu sayede PM10 değerlerine genel bir göz atabiliyoruz.

![](images/9.jpeg)

2019.01.01 - 2019.12.31 tarihine kadar olan tüm verilerimiz görüntüleniyor. Çizilmeyen bazı küçük kesitlerse PM10 değeri bilinmeyen tarihlerdir.

Diğer görselimse 365 günlük olarak fbprophet modeli kullanarak yaptığım tahmine ait görsel.

![](images/10.jpeg)

Görselde bulunan noktalar değişim(change point) zamanlarıdır. Bu değerler PM10 değerinin ani değişim geçirdiği zamanlardır. Tahmin ve geçmiş değerlere baktığımızda PM10 Değerinin genel bir azalış eğiliminde olduğu görülmektedir. Buradan PM10 değerini düşürme çalışmalarının düşük bir oranda da olsa başarılı olduğunu veya yapılan çalışmaların PM10 değerini etkilemediği sonucuna ulaşabiliriz.


Diğer görselimse tahmin verilerine ait eğilim, haftalık ve yıllık olarak eğilimlerin sonuçlarını göstermekte.

![](media/11.jpeg)

İlk grafiğe(trend) baktığımızda eğilimin 2017 yılının sonlarında zirveye ulaşıp daha sonra eğilimin aşağı doğru indiğini görüyoruz.

İkinci grafiğe(weekly) baktığımızda PM10 değerinin haftanın hangi günlerinde artış ve azalış gösterdiğini görebiliyoruz. Pazar günleri artmaya başlayan değer Salı gününe kadar artışını devam ettirip sonra Cuma gününe kadar düşüş gerçekleştirmiş. Buradan PM10 değerinin artış sebebinin çalışma zamanlarına bağlayabiliriz.

Üçüncü grafiğe(yearly) baktığımızda yaz aylarında düşen eğilim sonbahar ve kış aylarında artış gösterdiği görülüyor. Bunu etkileyen faktörlerse havaların soğumasına bağlı olarak artak katı yakıt tüketimi olarak değerlendirebiliriz.

