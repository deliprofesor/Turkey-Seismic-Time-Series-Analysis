# Turkey-Seismic-Time-Series-Analysis

Bu proje, Türkiye’deki tarihsel deprem verilerini kullanarak zaman serisi analizi ve LSTM tabanlı tahminler yapmayı amaçlamaktadır.

---

##  Veri Setleri

### 1. Earthquakes.xlsx - data.csv
**Kapsam:** Ana deprem veri seti, LSTM eğitimi için kullanılır  
**Format:** CSV  

| Sütun Adı      | Tipi             | Açıklama                                      | Analiz Rolü                |
| -------------- | ---------------- | -------------------------------------------- | -------------------------- |
| Date           | Tarih/Nesne      | Depremin gerçekleştiği tarih                 | Zaman Serisi İndeksi       |
| Time           | Metin            | Depremin tam saati                            | Zaman Serisi İndeksi       |
| Latitude       | Sayısal (Float)  | Depremin enlem konumu (coğrafi girdi)        | Girdi Özelliği (Feature)   |
| Longitude      | Sayısal (Float)  | Depremin boylam konumu (coğrafi girdi)       | Girdi Özelliği (Feature)   |
| Depth          | Sayısal (Float)  | Depremin odak noktası derinliği (km)         | Girdi Özelliği (Feature)   |
| Magnitude      | Sayısal (Float)  | Depremin büyüklüğü                            | Tahmin Hedefi (Target)     |
| Magnitude Type | Metin            | Kayıtta kullanılan büyüklük ölçeği (Mw, Mb…) | Girdi Özelliği (Opsiyonel) |
| Location       | Metin            | Depremin yaklaşık coğrafi konumu             | Girdi Özelliği (Opsiyonel) |
| ID             | Metin/Sayısal    | Olayın benzersiz kimliği                      | İhmal Edilebilir           |

**Not:** Date ve Time sütunları birleştirilip DateTime formatına çevrilmelidir. Sayısal sütunlar normalizasyon için ölçeklenmelidir.

---

### 2. Earthquake_4.xlsx - data.csv
**Kapsam:** Ek veri seti, belirli bölge veya dönem analizi için  
**Format:** CSV  

| Sütun Adı      | Tipi             | Açıklama                   | Analiz Rolü                |
| -------------- | ---------------- | ------------------------- | -------------------------- |
| Date           | Tarih/Nesne      | Depremin gerçekleştiği tarih | Zaman Serisi İndeksi       |
| Time           | Metin            | Depremin tam saati         | Zaman Serisi İndeksi       |
| Latitude       | Sayısal (Float)  | Depremin enlem konumu      | Girdi Özelliği (Feature)   |
| Longitude      | Sayısal (Float)  | Depremin boylam konumu     | Girdi Özelliği (Feature)   |
| Depth          | Sayısal (Float)  | Depremin odak noktası derinliği | Girdi Özelliği (Feature)   |
| Magnitude      | Sayısal (Float)  | Depremin büyüklüğü         | Tahmin Hedefi (Target)     |
| Magnitude Type | Metin            | Kullanılan büyüklük ölçeği | Girdi Özelliği (Opsiyonel) |
| Location       | Metin            | Depremin yaklaşık konumu   | Girdi Özelliği (Opsiyonel) |
| ID             | Metin/Sayısal    | Olayın benzersiz kimliği   | İhmal Edilebilir           |

---

### 3. Earthquake_5.xlsx - data.csv
**Kapsam:** Eğitim ve çapraz doğrulama için ek zaman serisi verisi  
**Format:** CSV  
*Yapısı diğer veri setleri ile aynıdır.*

---

### 4. Earthquake_6.xlsx - data.csv
**Kapsam:** Test veri seti, model performansını değerlendirmek için  
**Format:** CSV  
*Yapısı diğer veri setleri ile aynıdır.*

---

### 5. Earthquake_7.xlsx - data.csv
**Kapsam:** Doğrulama ve geleceğe yönelik tahmin simülasyonu  
**Format:** CSV  
*Yapısı diğer veri setleri ile aynıdır.*

