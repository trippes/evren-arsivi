# Evren Arşivi

Bu depo, hikâye projesinin evrenine ait bilgilerin yapılandırılmış, izlenebilir ve doğrulanabilir biçimde saklandığı tek doğruluk kaynağıdır (Single Source of Truth).

## Temel ilkeler
- Depoda açıkça kayıtlı olmayan bilgi, evren gerçeği kabul edilmez.
- Taslak, öneri ve kesinleşmiş kanon birbirinden ayrılır.
- Bir kayıt onaylanmadan kanona taşınmaz.
- Çelişkiler sessizce düzeltilmez; 07_KANON/celiskiler.json içinde izlenir.
- Her önemli varlık benzersiz bir id taşır.
- Bilinmeyen değerler tahmin edilmez; null veya açık TODO kullanılır.
- Değişiklikler gerekçeleriyle kaydedilir.

## Dizin yapısı
| Dizin | İçerik |
|---|---|
| 00_ANAYASA/ | Kanon, kayıt ve terminoloji kuralları |
| 01_EVREN/ | Kozmoloji, doğa yasaları ve evrenin genel çerçevesi |
| 02_COGRAFIYA/ | Kıtalar, bölgeler, yerleşimler ve haritalar |
| 03_TARIH/ | Kronoloji, dönemler ve tarihsel gelişmeler |
| 04_KARAKTERLER/ | Karakter kayıtları ve ilişkiler |
| 05_TOPLUMLAR/ | Halklar, kültürler, devletler ve kurumlar |
| 06_OLAYLAR/ | Olaylar, sonuçlar ve bağlantılar |
| 07_KANON/ | Kanon indeksi, çelişkiler ve karar günlüğü |
| 08_CALISMA/ | Henüz onaylanmamış taslaklar |
| schemas/ | JSON doğrulama şemaları |
| templates/ | Yeni kayıt şablonları |

## Kayıt durumları
- taslak: Üzerinde çalışılıyor.
- incelemede: Tutarlılık ve kaynak kontrolü bekliyor.
- kanon: Yetkili kararla kesinleşti.
- reddedildi: Kanona alınmadı.
- arsiv: Aktif kullanım dışı, geçmiş kaydı korunuyor.

## Yeni bilgi ekleme
1. İlgili dizinde şablonu temel alarak kayıt oluştur.
2. Benzersiz ve kalıcı bir id belirle.
3. Bilginin durumunu ve dayanağını belirt.
4. İlişkili kayıtların id değerlerini kullan.
5. Onaylanan bilgiyi kanon indeksine ekle.
6. Çelişki varsa karar verilene kadar açıkça işaretle.

Kanon ilkeleri 00_ANAYASA/KANON_ILKELERI.md dosyasında tanımlıdır. Sohbetlerde üretilen içerik, depoya işlenip onaylanmadıkça kanon değildir. Açıklamalar Türkçe, dosya adları ve makine anahtarları ASCII tutulur. Yapılandırılmış kayıtlar UTF-8 JSON kullanır.
