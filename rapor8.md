1. API Nedir, Neden Var?
- API (Application Programming Interface - Uygulama Programlama Arayüzü), iki farklı yazılımın veya sistemin birbiriyle konuşmasını, veri alışverişi yapmasını sağlayan bir köprü veya tercümandır.

- Günlük Hayat Benzetmesi: Bir restorana gittiğini düşün. Sen istemcisin (client), mutfak ise verilerin işlendiği sunucu (server). Doğrudan mutfağa gidip aşçıyla konuşmazsın. Masana gelen garson, siparişini alır, mutfağa iletir ve yemek hazır olduğunda sana geri getirir. İşte bu senaryodaki garson, tam olarak API'dir.

> Neden Var?
Bir uygulamaya harita eklemek istediğinde sıfırdan tüm dünyanın uydularını ve harita verisini kodlamazsın. Google Maps API'sini çağırır
ve haritayı uygulamana dahil edersin.
- Güvenlik İçin: Kimse veritabanının kapılarını dış dünyaya tamamen açmak istemez. API, sadece izin verilen verilerin, izin verilen sınırlar dahilinde alınmasını sağlar.

2. GET – POST – PUT – DELETE Nedir? (HTTP Metotları)
İstemci (örneğin bir web tarayıcısı), sunucuya API üzerinden bir istek göndereceğinde ne yapmak istediğini belirtmek için bazı "eylem kelimeleri" kullanır. Bunlara HTTP metotları denir. Bir kütüphane veya kitapçı sistemi üzerinden düşünelim:

- GET (Veri Çekme): Sunucudan bir bilgiyi getirmek için kullanılır. Veri üzerinde bir değişiklik yapmaz.
Örnek: "Bana 'Nutuk' kitabının detaylarını getir."

- POST (Yeni Veri Oluşturma): Sunucuya yeni bir veri göndermek ve kaydetmek için kullanılır.
Örnek: Sisteme yeni bir kitap eklemek: "Kitap Adı: Suç ve Ceza, Yazar: Dostoyevski..."

- PUT (Veri Güncelleme): Var olan bir veriyi tamamen değiştirmek veya güncellemek için kullanılır.
Örnek: Bir kitabın fiyatı veya stok bilgisi değiştiğinde o kaydı güncellemek.

- DELETE (Veri Silme): Sunucudaki bir veriyi kalıcı olarak silmek için kullanılır.
Örnek: Sistemden eskiyen veya kaybolan bir kitabı silmek.

3. JSON Yapısı Nedir?
JSON (JavaScript Object Notation), sistemlerin birbiriyle konuşurken kullandığı, hem insanların rahatça okuyabildiği hem de bilgisayarların kolayca işleyebildiği ortak bir yazı/veri formatıdır.

API'ler (garsonlar), mutfaktan masaya ya da masadan mutfağa bilgi taşırken bu formatı kullanır. Python'daki sözlük (dictionary) yapısına inanılmaz derecede benzer. anahtar: değer (key: value) çiftlerinden oluşur.

-JSON Örneği:
{
  "kitap_adi": "Sefiller",
  "yazar": "Victor Hugo",
  "sayfa_sayisi": 1232,
  "stokta_var_mi": true,
  "kategoriler": ["Klasik", "Roman"]
}

4. Basit Bir Endpoint Nasıl Tasarlanır?
Endpoint (Uç Nokta), bir API'nin dış dünyaya açtığı, belirli bir işlevi yerine getiren web adresleridir (URL). İstemci, bu adreslere yukarıdaki metotlarla (GET, POST vb.) istek atar.
İyi bir endpoint tasarlarken isimlendirmelerin net, tutarlı ve çoğul isimler (nouns) olması tercih edilir (fiiller yerine).

- Uç nokta (endpoint) tasarımı, özünde "Hangi adrese, hangi yöntemle gidildiğinde, ne olacağının" planlanmasıdır.
En sade haliyle, bir uç nokta tasarlarken şu 3 temel adımı belirlersin:

1. Adres Belirleme (URL)
- Adresler her zaman isim ve çoğul olmalıdır (eylem/fiil içermemelidir).
> Doğru: /kitaplar veya /kullanicilar
> Yanlış: /kitaplariGetir veya /yeniKullaniciEkle

2. Yöntem Seçme (HTTP Metodu)
- Aynı adrese farklı istek türleriyle giderek farklı işlemler yaparsın:
GET /kitaplar -> Kitapları listele
POST /kitaplar -> Yeni kitap ekle
DELETE /kitaplar/5 -> 5 id'li kitabı sil

3. Veri Formatı Seçme (JSON)
- İletişimin pürüzsüz olması için veriler standart JSON formatında taşınır:

ÖRNEK:
{
  "id": 5,
  "ad": "Dune",
  "yazar": "Frank Herbert"
}