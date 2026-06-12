# BİLGİSAYAR BİLİMLERİ TEMELLERİ
    Bilgisayar bilimleri, bilgi işleme süreçlerini inceleyen ve bu süreçleri daha verimli hale getirmek için yöntemler geliştiren bir 
bilim dalıdır. Temelinde matematik, mantık ve mühendislik yer alır. Modern dünyada yapay zekâdan siber güvenliğe kadar birçok alan bu disipline dayanır.

# TEMEL BİLEŞENLER
Donanım (Hardware): Fiziksel parçalardır. (CPU, RAM, disk vb.)
Yazılım (Software): Programlar ve işletim sistemleridir.

# BİLGİSAYAR MİMARİSİ (CPU, RAM, CAHCE)

## CPU (Central Processing Unit):
    Merkezi İşlem Birimi, bir bilgisayarın "beyni" olarak kabul edilen en kritik donanım bileşenidir. Bilgisayar üzerindeki tüm veri
akışını yönetir, komutları yorumlar ve matematiksel/mantıksal işlemleri gerçekleştirir.

1. CPU'nun Temel Bileşenleri
Bir işlemci, karmaşık görevleri yerine getirmek için birbirine bağlı alt birimlerden oluşur:

# Kontrol Birimi (Control Unit - CU): 
Bellekten gelen komutları alır, bunları çözer (decode) ve donanımın diğer parçalarına ne yapmaları gerektiğini söyler. Bir nevi orkestra şefi gibidir.

# Aritmetik Mantık Birimi (ALU): 
İşlemcinin tüm matematiksel hesaplamaları ve mantıksal kararları yürüten "hesap makinesi" kısmıdır. Bilgisayarda gerçekleşen en karmaşık grafik işlemlerinden en basit metin düzenlemelerine kadar her şey en sonunda ALU'nun yapabileceği işlemlere indirgenir.
    ALU tek başına bir şey saklamaz. Veriler Register adı verilen ultra hızlı depolama alanlarından ALU'ya beslenir, işlem yapılır ve
sonuç tekrar bir Register'a gönderilir. Örneğin bir oyun oynarken karakterinizin koordinatlarının güncellenmesi, saniyede milyonlarca kez ALU üzerinden geçen toplama işlemleridir.

# Yazmaçlar (Registers):
İşlemcinin içindeki çok küçük ama inanılmaz derecede hızlı geçici depolama alanlarıdır. İşlenen veriler ve bir sonraki komutun adresi burada tutulur.

# Önbellek (Cache): 
    Önbellek, CPU ile ana bellek (RAM) arasında bulunan, düşük kapasiteli ama son derece hızlı bir bellek türüdür.
Neden İhtiyaç Duyulur?
İşlemciler çok hızlıdır ancak RAM onlara kıyasla çok yavaş kalır. Eğer CPU her veri lazım olduğunda RAM'e gitseydi, vaktinin çoğunu verinin gelmesini bekleyerek (idle) harcardı. Cache, CPU'nun sık kullandığı verileri "elinin altında" tutarak bu beklemeyi önler.
    Önbellek Hiyerarşisi (L1, L2, L3):
- L1 Cache (Level 1): İşlemci çekirdeğinin içine gömülüdür. En hızlısıdır ama kapasitesi çok küçüktür (genellikle birkaç KB). Her çekirdeğin kendine ait L1'i vardır.
- L2 Cache (Level 2): L1'den biraz daha yavaş ama daha geniştir (MB seviyelerinde). Yine çekirdeğe çok yakındır.
- L3 Cache (Level 3): Genellikle tüm işlemci çekirdekleri tarafından ortaklaşa kullanılır. En yavaş (ama yine de RAM'den kat kat hızlı) ve en büyük kapasiteli önbellektir.

2. Çalışma Prensibi: "Fetch-Decode-Execute" Döngüsü
    CPU, her işlemi dört temel adımda gerçekleştirir:
- Getirme (Fetch): İhtiyaç duyulan komut, sistem belleğinden (RAM) alınır.
- Kod Çözme (Decode): Kontrol birimi, bu komutun ne anlama geldiğini (ne tür bir işlem yapılacağını) belirler.
- Yürütme (Execute): ALU veya ilgili birim işlemi gerçekleştirir (örneğin iki sayıyı toplar).
- Geri Yazma (Write-back): İşlemin sonucu belleğe veya ilgili yazmaca kaydedilir.

3. Performans Parametreleri 
- Saat Hızı (Clock Speed): CPU'nun saniyede kaç döngü yapabildiğini gösterir.
    Örn: 3.5 GHz, saniyede 3.5 milyar işlem döngüsü demektir.
- Çekirdek Sayısı (Cores): Modern işlemciler "çok çekirdekli"dir. Her çekirdek, aynı anda farklı komut dizilerini işleyebilen bağımsız bir işlem birimi gibi çalışır.
- Mimari ve Üretim Teknolojisi: Transistörlerin ne kadar küçük (nanometre - nm) ve verimli yerleştirildiği ile ilgilidir. Transistör sayısı arttıkça işlem gücü artar.

## RAM (Random Access Memory):
 Rastgele Erişimli Bellek, bilgisayarın "kısa süreli hafızasıdır". İşlemcinin o an üzerinde çalıştığı verileri ve çalışan
uygulamaların komutlarını geçici olarak sakladığı, çok hızlı bir depolama birimidir.

1. Temel Özellikleri
- RAM, elektrik kesildiği anda içindeki tüm bilgileri kaybeder. Bu yüzden veriler kalıcı olarak SSD veya Hard Disk'e kaydedilir, ancak işlenirken RAM'e çağrılır.
- RAM, bir SSD'den yaklaşık 10 ila 100 kat, bir Hard Disk'ten ise binlerce kat daha hızlıdır.
- Genellikle GB (Gigabyte) birimiyle ölçülür. Günümüzde standart sistemlerde 8 GB veya 16 GB RAM yaygındır.

2. RAM Nasıl Çalışır?
Bir programı başlattığınızda, o programa ait dosyalar yavaş olan kalıcı depolamadan (SSD) alınır ve hızlı olan RAM'e kopyalanır. İşlemci, veriye ihtiyaç duyduğunda doğrudan RAM'den çeker.
- RAM Türleri:
DRAM (Dynamic RAM): Bilgisayarlarda ana bellek olarak kullanılan türdür. Sürekli olarak elektriksel olarak yenilenmesi gerekir.
SRAM (Static RAM): Daha hızlı ve pahalıdır genellikle işlemci içindeki Cache (Önbellek) yapımında kullanılır. Yenilenmeye ihtiyaç duymaz.

3. RAM Performansını Etkileyen Faktörler
Sadece kapasite (8GB, 16GB) her şeyi belirlemez, performans için şu iki değer de kritiktir:

- Frekans (Mhz): RAM'in saniyede ne kadar veri aktarabileceğini belirler. (Örn: 3200 MHz, 4800 MHz).

- Gecikme Süresi (CL): İşlemcinin RAM'den bir veri istediğinde, verinin gelmesine kadar geçen süredir. CL değeri ne kadar düşükse, RAM o kadar tepkiseldir.


## DİSK 
    Disk, verilerin bilgisayar kapatılsa bile kalıcı olarak saklandığı fiziksel birimdir. RAM'in "geçici hafıza" olmasına
karşın, disk bilgisayarın "arşivi" veya "kütüphanesi" görevini görür.

1. HDD (Hard Disk Drive - Sabit Disk Sürücüsü):

- Geleneksel depolama teknolojisidir. Veriler, manyetik bir tabaka ile kaplanmış ve çok yüksek hızda dönen plakalar üzerine yazılır.
- Hareketli bir okuma/yazma kafası, dönen plakalar üzerinde verinin bulunduğu konuma fiziksel olarak gider.
- Düşük maliyetle çok yüksek depolama kapasitesi (TB'larca veri) sunar.
- Mekanik parçalar içerdiği için sarsıntılara karşı hassastır ve SSD'lere göre çok daha yavaş çalışır. Ayrıca çalışma sırasında ses ve ısı üretir.

2. SSD (Solid State Drive - Katı Hal Sürücüsü)
    Modern bilgisayarlarda standart haline gelen teknolojidir. İçinde hareketli hiçbir parça yoktur, veriler tıpkı USB belleklerdeki gibi
flash bellek çiplerinde saklanır.

- Veriye erişim tamamen elektroniktir. Bu sayede okuma/yazma kafasının hareket etmesini bekleme süresi ortadan kalkar.
- Bilgisayarın açılış süresini ve programların yüklenme hızını HDD'ye göre 10-20 kat artırabilir.
- Hareketli parça olmadığı için düşme ve darbelere karşı çok daha dirençlidir.
- Tamamen sessiz çalışır ve daha az enerji tüketir.

3. Depolama ve Performans İlişkisi
    Disk, bilgisayarın genel "hissedilen" hızını belirleyen en önemli unsurdur. İşlemciniz ne kadar hızlı olursa olsun, veriyi diskten
RAM'e çekme hızı düşükse sistem darboğaza girer.
    Disk kapasitesi, bilgisayarın aynı anda kaç programı çalıştırabileceğini değil, içine ne kadar dosya kaydedebileceğini belirler. Aynı
anda çok iş yapmak için RAM, çok veri saklamak için Disk kapasitesi önemlidir.

