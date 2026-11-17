# A3 — Kanon İndeksi ve Karar Günlüğü Doğrulama Raporu

- **Tarih:** 2026-11-17
- **Depo:** `trippes/evren-arsivi`
- **Dal:** `main`
- **Aşama:** A3 — Kanon indeksi ve karar günlüğü
- **Kanon etkisi:** Daha önce proje sahibi tarafından onaylanmış kararlar karar günlüğüne işlendi. Yeni hikâye kararı üretilmedi.

## 1. Amaç

Kanon indeksindeki kayıtların esas JSON dosyalarıyla tutarlılığını doğrulamak; doğrulanabilir proje sahibi kararlarını tarih uydurmadan karar günlüğüne aktarmak; ilişki alanlarının görev ayrımını kayıt standardında açıklamak.

## 2. Kanon indeksi denetimi

`07_KANON/kanon-indeksi.json` içindeki üç kayıt GitHub'dan tek tek çekilerek karşılaştırıldı:

| Kimlik | Esas kayıt yolu | Kayıt kimliği | Tür | Durum | Ad |
|---|---|---|---|---|---|
| `premise-0001` | `01_EVREN/temel-zaman-cizgisi.json` | Eşleşiyor | Eşleşiyor | Eşleşiyor | Eşleşiyor |
| `premise-0002` | `01_EVREN/temel-anlati-onermesi.json` | Eşleşiyor | Eşleşiyor | Eşleşiyor | Eşleşiyor |
| `character-0001` | `04_KARAKTERLER/ana-karakterler/character-0001.json` | Eşleşiyor | Eşleşiyor | Eşleşiyor | Eşleşiyor |

- İndekste 3 kayıt bulunuyor.
- Kimlikler benzersiz.
- Her indeks girdisinin dosya yolu mevcut ve JSON kaydındaki `id`, `type`, `name`, `status` alanlarıyla eşleşiyor.
- İndeksin mevcut içeriği tutarlı olduğundan gereksiz değişiklik yapılmadı.
- `updated_at` alanı mevcut şemada nullable ve tarih biçimi standardı dışında özel bir indeks güncelleme kuralı tanımlanmamış olduğundan null bırakıldı.

## 3. Karar günlüğüne eklenen kararlar

`07_KANON/karar-gunlugu.md` artık üç onaylı karar içeriyor:

### DEC-0001 — Zaman dalları, soy müdahalesi ve zamandan bağımsız merkez

Önceki Şah Cem proje konuşmalarında açıkça belirlenmiş; zaman yolculuğunun yeni dal oluşturması, dalların bağımsız tarihsel akışı, ikinci Zaman Şövalyesi'nin doğmasını önlemek için dal içindeki soy atasına müdahale, ana zaman çizgisindeki varlığın korunması, zamandan bağımsız merkez ve kuantum bilgisayarının gözlem işlevleri kaydedildi.

**Tarih notu:** Bu kararların tek tek kesin tarihleri mevcut arşivde bulunmadığından tarih uydurulmadı; önceki proje konuşmalarına dayandığı açıkça belirtildi.

### DEC-0002 — İnsan kökeni ve DNA kodlamasıyla biyolojik yaşlanmanın durdurulması

17 Kasım 2026 tarihli açık kullanıcı onayı kaydedildi. Biyolojik yaşlanmanın durdurulmasının doğaüstü ölümsüzlük anlamına gelmediği de karar kapsamına alındı.

### DEC-0003 — Gerçeklik bilgisi ve mutlak zaman hâkimiyetinin ilişkisi

17 Kasım 2026 tarihli kullanıcı açıklaması kaydedildi. Geniş gerçeklik bilgisi ile mutlak zaman hâkimiyetinin birbirinin alternatifi olmadığı; zaman yolculuğu ve müdahale kapasitesinin mutlak zaman hâkimiyetini gösterdiği belirtildi.

Her üç kararın etkilenen esas kaydı `character-0001` olarak gösterildi. Karar günlüğü ile JSON kaynak notları birbiriyle uyumludur.

## 4. İlişki alanlarının görev ayrımı

`00_ANAYASA/KAYIT_STANDARTLARI.md` dosyasına aşağıdaki ayrım eklendi:

- `related_entities`: Bir kaydın bağlantılı olduğu varlık kimliklerinin kısa ve yalın listesi.
- `relationships`: İlişkinin hedefini, anlamını ve durumunu açıklayan yapılandırılmış ilişki listesi.

Aynı hedefin iki alanda bulunması tek başına hata sayılmaz; alanların farklı işlevleri vardır. Ancak çelişen hedef/ilişki bilgisi üretilemez. Bu alanların JSON Schema ve şablonlardaki desteği A4 kapsamında incelenecektir.

## 5. Doğrulama

- [x] Kanon indeksindeki tüm girdiler mevcut esas JSON kayıtlarıyla karşılaştırıldı.
- [x] Kimlik, tür, ad ve durum alanlarının eşleştiği doğrulandı.
- [x] İndeks kimliklerinin benzersiz olduğu doğrulandı.
- [x] Karar günlüğüne DEC-0001, DEC-0002 ve DEC-0003 eklendi.
- [x] Önceki kararların kesin tarihleri bilinmediğinde tarih uydurulmadı.
- [x] 17 Kasım 2026 tarihli açık kararlar doğru tarihle kaydedildi.
- [x] İlişki alanlarının görev ayrımı kayıt standardına eklendi.
- [x] Eski `zaman_sovalyesi.md` yolunun kaldırıldığı GitHub'da 404 yanıtıyla doğrulandı; yeni `zaman-sovalyesi.md` yolu A2'de doğrulanmıştı.

## 6. Açık kalan teknik işler

- `relationships` alanı mevcut karakter JSON'unda kullanılıyor; ancak `schemas/entity.schema.json` içinde açık bir şema tanımı bulunmuyor. Şemanın `additionalProperties: true` olması bu alanı şu an engellemese de açık tanım ve doğrulama eksikliği A4'te ele alınmalı.
- `related_entities` ve `relationships` alanlarının depo genelindeki kullanımı A4'te taranmalı.
- Kanon indeksinin `updated_at` alanı için standart bir güncelleme politikası henüz tanımlı değil.
- Karar günlüğü biçimi şu an Markdown temelli; karar kimliklerinin benzersizliği için otomatik kontrol henüz bulunmuyor.

## 7. A3 kapanış

**A3 durumu: Tamamlandı.**

Kanon indeksi ile üç esas kayıt arasında kimlik, tür, ad, durum ve yol tutarlılığı doğrulandı. Üç karar, kaynak ve tarih hassasiyeti korunarak günlüğe işlendi. İlişki alanlarının görev ayrımı kayıt standardına eklendi.

**Kanon indeksi:** Tutarlı, değişiklik gerekmedi.  
**Karar günlüğü:** Üç onaylı karar içeriyor.  
**Sonraki alt aşama:** A4 — İlişki tutarlılığı, şema/şablon uyumluluğu ve Aşama A kapanışı.
