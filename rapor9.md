# 1. Veritabanı Mantığı ve SQL Temelleri
- Veritabanı mantığı, verinin bütünlüğünü (integrity), güvenliğini ve erişilebilirliğini minimum veri tekrarı ile sağlama sanatıdır. Excel gibi tablolarda veriler büyüdükçe satırları bulmak zorlaşır, formüller çöker ve aynı veri (örneğin müşteri adresi) yüzlerce kez tekrar edebilir. Veritabanları (DBMS) bu sorunları çözmek için tasarlanmıştır.

- SQL ise bu sistemlerin yönetim dilidir. Temelde 4 ana gruba ayrılır:

> DDL (Data Definition Language): Tablo oluşturma, silme, değiştirme(CREATE, DROP, ALTER)
> DML (Data Manipulation Language): Veri ekleme, silme, güncelleme (INSERT, UPDATE, DELETE)
> DQL (Data Query Language): Veri çekme (SELECT)
> DCL (Data Control Language): Yetkilendirme (GRANT, REVOKE)

# 2. Relational Database (İlişkisel Veritabanı - RDBMS)
- İlişkisel veritabanı, verileri satırlar (records/tuples) ve sütunlardan (fields/attributes) oluşan mantıksal tablolarda tutar. En büyük özelliği, veriler arasındaki ilişkilerin matematiksel (küme teorisi) temellere dayanmasıdır.

- İlişkisel modelde 3 tip ilişki türü vardır:

1. One-to-Many (Bire-Çok): En sık kullanılanıdır. Bir sınıfta birden fazla öğrenci olabilir ama bir öğrenci sadece bir sınıfa ait olabilir.

2. Many-to-Many (Çoka-Çok): Bir öğrenci birden fazla ders alabilir, bir dersi birden fazla öğrenci seçebilir. Bu ilişki araya üçüncü bir "Köprü (Join) Tablosu" konularak çözülür.

3. One-to-One (Bire-Bir): Bir kullanıcının sadece bir tane detaylı profil kartı olabilir. Genelde güvenlik veya performans nedeniyle tabloları bölmek için kullanılır.

# 3. Primary Key (PK) ve Foreign Key (FK)
- Bu iki kavram tablolar arasındaki "bağ dokusudur" ve veri tutarlılığını zorunlu kılar (Referential Integrity).

1. Primary Key (Birincil Anahtar)
Tablodaki her bir satırın benzersiz kimliğidir.
Özellikleri: NULL (boş) olamaz. Her tabloda sadece bir adet Primary Key tanımı olabilir (ancak birden fazla sütunun birleşimiyle oluşan Composite Key de PK olabilir).

> SQL Örneği:
CREATE TABLE Ogrenciler (
    OgrenciID INT PRIMARY KEY, -- İşte bu Primary Key
    Ad VARCHAR(50),
    Soyad VARCHAR(50)
);

2. Foreign Key (Yabancı Anahtar)
Bir tablodaki verinin, başka bir tablodaki veriyle eşleştiğini doğrulamak için kullanılır.
Özellikleri: Foreign Key olan bir alana, bağlandığı tablonun Primary Key'inde bulunmayan bir değer yazamazsınız. Bu sayede veritabanı "hayalet veri" oluşmasını engeller.

SQL Örneği:
CREATE TABLE Notlar (
    NotID INT PRIMARY KEY,
    DersAdi VARCHAR(50),
    Skor INT,
    OgrenciID INT, 
    FOREIGN KEY (OgrenciID) REFERENCES Ogrenciler(OgrenciID) -- Köprü kuruldu
);

# 4. SELECT – JOIN – GROUP BY Derinlemesine Bakış
Bu komutlar veri analizi ve raporlamanın temelidir. Bir senaryo üzerinden gidelim: Elimizde Musteriler ve Siparisler tablosu olsun.

> SELECT (Veri Seçme)
Sadece ihtiyacımız olan sütunları filtreleyerek ekrana getirmemizi sağlar. WHERE şartı ile birleştirilerek satır bazlı filtreleme de yapılır.

SQL Örneği:
SELECT Ad, Soyad FROM Musteriler WHERE Sehir = 'Antalya';

> JOIN (Tabloları Birleştirme)
İlişkili tabloları mantıksal olarak yan yana getirir. En popüler olanı INNER JOIN'dir (Her iki tabloda da karşılığı olan verileri getirir).

Senaryo: Hangi müşteri, ne kadarlık sipariş vermiş? (Müşteri adı bir tabloda, sipariş tutarı diğer tabloda).

SQL Örneği:
SELECT Musteriler.Ad, Siparisler.SiparisTutari
FROM Musteriler
INNER JOIN Siparisler ON Musteriler.MusteriID = Siparisler.MusteriID;

> GROUP BY (Gruplama)
Verileri kümeleyerek üzerlerinde istatistiksel işlemler (SUM, COUNT, AVG, MAX, MIN) yapmamızı sağlar.

Senaryo: Şehir bazında toplam kaç müşterimiz var?

SQL Örneği:
SELECT Sehir, COUNT(MusteriID) AS ToplamMusteri
FROM Musteriler
GROUP BY Sehir;

# 5. Index (İndeks) Mekanizması Nasıl Çalışır?
- Veritabanında bir sorgu çalıştırdığınızda (Örn: SELECT * FROM Kullanicilar WHERE Email = 'abc@gmail.com'), eğer Email sütununda bir indeks yoksa, veritabanı motoru ilk satırdan başlar ve milyonlarca satırı tek tek okur. Buna Full Table Scan (Tam Tablo Taraması) denir ve çok yavaştır.

> Arka Plandaki Mantık: B-Tree (Balanced Tree)
Bir sütuna Index tanımladığınızda, veritabanı arka planda o sütundaki verileri sıralı bir ağaç yapısında (B-Tree) kopyalar.
- Siz bir arama yaptığınızda, motor her defasında verinin yarısını eleyerek (Binary Search mantığına benzer şekilde) aradığınız kayda birkaç adımda ulaşır. Milyonlarca veri arasından hedefi bulmak saniyelerden milisaniyelere düşer.

> İndeks Türleri
- Clustered Index: Tablonun fiziksel olarak disk üzerindeki sıralamasını belirler. Bir tabloda sadece bir tane olabilir (Otomatik olarak Primary Key sütunudur).

- Non-Clustered Index: Tablodan bağımsız, ayrı bir yerde tutulan adres defteri gibidir. Bir tabloda birden fazla olabilir (Örn: Sık arama yapılan Email veya Tarih sütunlarına eklenir).