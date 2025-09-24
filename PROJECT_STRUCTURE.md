# Project Structure

```
ar-ge-envanter-repo/
├── ar-ge-envanter-updatedd.html   # Main application (HTML+CSS+JS in one file)
├── README.md                      # Documentation
├── LICENSE                        # MIT license
├── .gitignore                     # Git ignore rules
├── PROJECT_STRUCTURE.md           # Project structure and notes
├── sample-db/                     # Sample CSV data (fallback, demo, test)
│   ├── Capacitors.csv
│   ├── Resistors.csv
│   ├── Inductor.csv
│   └── ... (other CSV files)
```

## CSV Dosyaları
- Tüm CSV dosyalarını `sample-db/` klasöründe tutabilirsiniz. Uygulama önce kökten arar, bulamazsa otomatik olarak `sample-db/` altından yükler.
- Klasör düzeni için tüm demo/test CSV'leri burada tutmak önerilir.

## Fallback ve Okuma Mantığı
- Uygulama, kategoriye ait CSV dosyasını önce kökten (`Capacitors.csv`), bulamazsa `sample-db/Capacitors.csv` yolundan yükler.
- Kategori sayısı ve veri, dosya sayısına göre dinamik olarak güncellenir.

## Ek Notlar
- Kendi CSV'lerinizi eklerken dosya adlarını ve formatını README.md'ye uygun tutun.
- Kategori sayısı ve veri güncelliği için dosya isimlerinin doğru olduğundan emin olun.
