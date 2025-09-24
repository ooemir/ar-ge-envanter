# Ar-Ge Envanter Sistemi

Basit, tek dosyalık bir envanter yönetimi. HTML içindeki gömülü JavaScript ile çalışır; CSV dosyalarınızı okuyup kategori ve ürünleri listeleyebilir, ekleme/düzenleme/silme yapabilirsiniz. İsterseniz verileri HTML içine gömüp tek dosya halinde paylaşabilirsiniz. Artık CSV dosyalarını hem kökten hem de `sample-db/` klasöründen otomatik olarak bulup yükler.

## Özellikler
- Kategoriler ve ürünler (CSV'den yükleme + gömülü veri)
- Arama ve filtreleme
- Düşük ve kritik stok özetleri (dashboard)
- Tek tıkla JSON dışa/İçe aktarma
- HTML içine veri gömerek paylaşma ("HTML İndir")
- Otomatik CSV fallback: Dosya kökte yoksa `sample-db/` klasöründen yüklenir
- Modern responsive arayüz
- Kolay GitHub paylaşımı

## Hızlı Başlangıç
- Bu klasörü VS Code ile açın.
- `ar-ge-envanter-updatedd.html` dosyasını açın.
- VS Code Live Server eklentisini kullanın ve dosyayı "Open with Live Server" ile çalıştırın.
- Sayfa açıldığında otomatik olarak CSV dosyalarınızı okumaya çalışır (aynı klasörde olmalı). Kökte bulunamazsa `sample-db/` klasöründeki örnek CSV'lere otomatik geçer.

> Not: Tarayıcı güvenlik kısıtları nedeniyle yerel dosya okuma CORS engeline takılırsa Live Server kullanın. Live Server yoksa CSV okuma başarısız olabilir; yine de gömülü örnek veriyle uygulama çalışır.

## Klasör Yapısı
- `ar-ge-envanter-updatedd.html`: Uygulamanın tamamı
- CSV dosyaları: Aynı klasörde (ör. `Capacitors.csv`, `Resistors.csv` ...)
- `sample-db/`: Paylaşım ve test için küçük örnek CSV seti (otomatik fallback)

## CSV Formatı
Tüm CSV'ler şu kolon düzenini kullanacak şekilde okunur (ilk satır başlık):
- Alt Kategori
- INFO (Açıklama)
- MPN (Parça Numarası)
- Quantity (Miktar)
- Link (İsteğe bağlı)

## Kullanım
- Dashboard: Özet istatistikleri ve düşük/kritik stok öğelerini gösterir.
- Envanter Listesi: Kategori sekmelerinden birini seçerek ürünleri görün.
- Arama: Parça adı/numarası/açıklamada arar.
- Filtre: Aktif kategoride benzersiz parça adlarına göre filtreler.
- Yeni Parça: Ekle, düzenle, sil işlemleri yapılabilir.
- JSON Dışa Aktar: O anki `categories` yapısını JSON indirir.
- JSON İçe Aktar: Daha önce indirdiğiniz JSON'u geri yükler.
- HTML İndir: Güncel `categories` verisini HTML içine gömer ve yeni HTML indirir.

## Kategori Sayısı
Dashboard'daki "Kategori Sayısı" dinamik hesaplanır ve mevcut tüm kategorileri sayar.

## Örnek Veritabanı (Sample DB)
Minimal bir demo için `sample-db/` klasörü sağlanmıştır. Bu dosyaları proje köküne kopyalayabilir veya doğrudan `sample-db/` içinde bırakabilirsiniz. Uygulama önce kökten dosyayı arar, bulamazsa `sample-db/` altından yükler.

## GitHub'a Yükleme
1. Yeni repo oluşturun (GitHub).
2. Bu klasörde Git başlatın ve gönderin:
```bash
git init
git add .
git commit -m "feat: initial commit ar-ge envanter"
git remote add origin <REPO_URL>
git branch -M main
git push -u origin main
```

## Sorun Giderme
- CSV okunmuyor: Live Server ile çalıştırın. Dosya isimleri birebir eşleşmeli.
- Kategori görünmüyor: İlgili CSV boş olabilir; uygulama yine kategoriyi oluşturur ama veri satırı yoksa liste boş görünür.
- Dosya kökte yoksa, `sample-db/` altına koyun.

## Kalite ve Eklenti Önerileri
- VS Code Live Server ile anında test edin.
- Responsive arayüz ve modern tasarım.
- Kategori ekleme/silme, toplu veri güncelleme gibi ek fonksiyonlar eklenebilir.
- Kodunuzu GitHub'da paylaşırken MIT lisansı ile açık kaynak sunabilirsiniz.
- README dosyasını güncel tutun ve örnek ekran görüntüsü ekleyin.
