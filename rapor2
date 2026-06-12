# İŞLETİM SİSTEMİ (OPERATİNG SYSTEM) TEMELLERİ
    İşletim sistemi işlemci (CPU), bellek, depolama birimleri ve giriş/çıkış cihazlarını yöneten bir sistem yazılımıdır. Başlıca
görevleri şunlardır:
- Kaynak yönetimi (CPU, RAM, disk)
- Süreç (process) yönetimi
- Bellek yönetimi
- Dosya sistemi yönetimi
- Güvenlik ve erişim kontrolü
- Kullanıcı arayüzü sağlama

İşletim sistemleri genel olarak çok kullanıcılı (multi-user), çok görevli (multi-tasking) ve çok işlemcili (multi-processing) sistemleri destekleyecek şekilde tasarlanır.

# KERNEL(ÇEKİRDEK) NEDİR?
    Kernel, işletim sisteminin en temel ve kritik bileşenidir. Donanım ile yazılım arasındaki doğrudan iletişimi sağlar. Sistem
kaynaklarının kontrolü kernel üzerinden gerçekleştirilir.

Kernel’in temel görevleri:
- Donanım kaynaklarını yönetmek
- Süreçler arasında iletişim sağlamak
- Bellek tahsisi yapmak
- Aygıt sürücülerini kontrol etmek

Kernel türleri:
1. Monolitik Kernel: Tüm hizmetler çekirdek içinde çalışır.
2. Mikro Kernel: Temel işlevler çekirdekte, diğerleri kullanıcı alanında çalışır.
3. Hibrit Kernel: İki yaklaşımın birleşimidir.

#  SÜREÇ(PROCRESS) ve İŞ PARÇACIĞI(THREAD) ARASINDAKİ FARKLAR

1. SÜREÇ(PROCRESS):
Bir programın çalışmakta olan halidir. Her süreç kendine ait bir adres alanına ve kaynaklara sahiptir.

2. İŞ PARÇACIĞI(THREAD):
Bir süreç içinde çalışan daha küçük yürütme birimidir. Aynı süreç içindeki thread’ler belleği paylaşır.

Temel farklar:
- Süreçler bağımsızdır, thread’ler bağımlıdır.
- Süreçler arası iletişim maliyetlidir, thread’ler arası daha hızlıdır.
- Süreçler daha fazla kaynak tüketir.
- Thread’ler aynı bellek alanını paylaşır.

# BELLEK YÖNETİMİ(MEMORY MANAGEMENT)
    İşletim sistemi, sınırlı olan RAM kaynağını verimli kullanmak için çeşitli teknikler uygular. Bellek yönetiminin temel amacı
süreçlere ihtiyaç duydukları alanı ayırmak ve süreçlerin birbirinin verisine erişmesini engellemektir.

Temel Teknikler:

- Paging (Sayfalama): Fiziksel belleği sabit boyutlu bloklara (frames) ve mantıksal belleği sayfalara (pages) ayırır. Bu sayede bellek parçalanması (fragmentation) önlenir.

- Virtual Memory (Sanal Bellek): RAM kapasitesinden daha büyük programların çalıştırılmasına olanak tanır. Sabit diskin bir kısmını RAM gibi kullanarak süreçlerin sadece o an ihtiyaç duyduğu kısımları belleğe yükler.

- Segmentation (Bölümleme): Belleği mantıksal birimlere (kod, veri, yığın) ayırarak yönetir.

# CPU ZAMANLAYICILARI (CPU SCHEDULERS)
    CPU zamanlaması, çok görevli (multitasking) sistemlerde hangi sürecin ne zaman ve ne kadar süreyle işlemciyi kullanacağına karar
veren mekanizmadır.

Zamanlama Algoritmaları:

- First-Come, First-Served (FCFS): İlk gelen sürece ilk hizmet verilir. Basittir ancak "Konvoy Etkisi"ne (uzun bir işlemin arkasında kısa işlemlerin beklemesi) neden olabilir.

- Shortest Job First (SJF): İşlem süresi en kısa olan sürece öncelik verilir. Ortalama bekleme süresini minimize eder.

- Round Robin (RR): Her sürece belirli bir zaman dilimi (time quantum) verilir. Süre bitince işlemci bir sonraki sürece geçer. Etkileşimli sistemler için idealdir.

- Priority Scheduling: Süreçlere önem derecelerine göre öncelik verilir.

- Multilevel Queue: Süreçler farklı kuyruklara ayrılır.

Amaçlar:
- CPU kullanımını maksimize etmek
- Bekleme süresini minimize etmek
- Adil bir dağılım sağlamak