# Aşama A — Kayıt Bütünlüğü Teknik Planı

- **Hazırlanma tarihi:** 2026-11-17
- **Depo:** `trippes/evren-arsivi`
- **Dal:** `main`
- **Plan türü:** Teknik çalışma planı; kanon kararı değildir.
- **Başlangıç referansı:** Denetim raporu `reports/2026-11-17-arsiv-denetim-raporu.md`

## 1. Amaç ve sınırlar

Aşama A'nın amacı, arşivdeki kanonik kayıtların tekil kimlik, tekil esas kayıt, tutarlı indeks ve izlenebilir karar geçmişi ilkeleriyle yönetilmesini sağlamaktır.

Bu belge yalnızca teknik planı tanımlar. Bu aşamada:
- Hikâye kanonu değiştirilmez.
- Karakter ayrıntıları kendiliğinden birleştirilmez veya statüsü yükseltilmez.
- Bilinmeyen karar tarihleri tahmin edilmez.
- Kullanıcı onayı olmadan mevcut kayıtlar taşınmaz, silinmez veya yeniden adlandırılmaz.

## 2. Başlangıç durumu

Denetimde şu durumlar tespit edilmiştir:

1. `04_KARAKTERLER/ana-karakterler/character-0001.json` karakterin yapılandırılmış kaydıdır ve `character-0001` kimliğini kullanır.
2. `04_KARAKTERLER/zaman_sovalyesi.md` aynı karakter için ikinci bir kimlik (`karakter-zaman-sovalyesi`) tanımlar.
3. Markdown belgesi; biyolojik yaşlanmanın durdurulması, insan kökeni, paralel dallarda atasını öldürme ilkesi ve zamandan bağımsız merkez gibi JSON'da bulunmayan ayrıntılar içerir.
4. Kanon indeksi JSON kaydını listeler; Markdown dosyasını ayrı bir kayıt olarak listelemez.
5. Karakter JSON kaydında hem `related_entities` hem `relationships` alanı bulunur; aralarındaki görev ayrımı belgelenmemiştir.
6. Karar günlüğünde yalnızca boş şablon vardır.

## 3. Önerilen hedef mimari

### 3.1 Tek esas kayıt

Her varlık için bir adet yapılandırılmış JSON kaydı, o varlığın makine tarafından okunabilir esas kaydı olacaktır.

Zaman Şövalyesi için mevcut `character-0001` kimliği korunması önerilir. Bu kimlik zaten yapılandırılmış karakter kaydında ve kanon indeksinde kullanılmaktadır. Yeni bir karakter kimliği üretilmesi önerilmez.

### 3.2 Markdown belgelerinin rolü

Markdown dosyaları iki amaçtan biriyle kullanılabilir:
- Esas JSON kaydından türetilmiş, açıklayıcı ve insan tarafından okunabilir belge.
- Taslak/araştırma belgesi; esas kayıttan açıkça ayrılmış ve kanon statüsü taşımayan içerik.

Zaman Şövalyesi Markdown belgesinin nihai rolü, içerik uzlaştırması tamamlanıp kullanıcı onayı alınana kadar belirlenmiş sayılmayacaktır. Aynı karakter için bağımsız ikinci bir kanon kimliği sürdürülmemelidir.

### 3.3 İlişki modeli

Önerilen tek ilişki alanı `relationships` olacaktır. Her ilişki en azından:
- `entity_id`: hedef kaydın kalıcı kimliği,
- `relation`: ilişkinin anlamı,
- `status`: ilişkinin kanon/taslak durumu

bilgilerini taşır.

`related_entities` aynı ilişkiyi ikinci kez ifade ediyorsa uzun vadede kaldırılmalıdır. Ancak kaldırma işlemi, tüm kayıtlar taranıp mevcut kullanımlar ve geriye dönük uyumluluk kontrol edildikten sonra yapılmalıdır. Aşama A'nın ilk uygulama adımında bu alan otomatik silinmeyecektir.

### 3.4 Kanon indeksi

`07_KANON/kanon-indeksi.json`, kanon statüsündeki esas kayıtların tekil envanteri olacaktır. Her indeks girdisinin:
- benzersiz `id`,
- kayıt `type`,
- görünen `name`,
- `status`,
- depodaki tekil esas `path`

alanları, ilgili JSON kaydıyla eşleşmelidir.

Taslak ve incelemedeki kayıtlar kanon indeksine kanon olarak eklenmemelidir.

### 3.5 Karar günlüğü

Karar günlüğü yalnızca doğrulanabilir proje sahibi kararlarını içermelidir. Her karar benzersiz `DEC-NNNN` kimliği almalıdır.

Geriye dönük karar kaydı hazırlanırken:
- Açık kararın gerçekten verildiği doğrulanabiliyorsa kayda alınır.
- Tarih doğrulanamıyorsa tarih uydurulmaz; bilinmeyen tarih açıkça belirtilir veya karar ileriye dönük kayda alınır.
- Asistan önerileri, kullanıcı tarafından onaylanmadıkça karar olarak yazılmaz.
- Mevcut kanon kaydının varlığı tek başına, o kaydın bütün alt ayrıntılarının ayrı ayrı onaylandığını kanıtlamaz.

## 4. Zaman Şövalyesi içerik uzlaştırma yöntemi

Mevcut iki dosyadaki her iddia, aşağıdaki sınıflardan birine ayrılacaktır:

| Sınıf | Anlamı | İşlem |
|---|---|---|
| A — Ortak ve açık | İki belgede ortak veya proje sahibinin açık kararıyla doğrulanmış | Esas JSON kaydında korunması önerilir |
| B — Yalnız Markdown | JSON'da bulunmayan, Markdown'da yer alan ayrıntı | Ayrı kullanıcı onayı olmadan esas kayda taşınmaz |
| C — Çelişkili | Belgeler arasında anlam veya kapsam farkı bulunan | Çelişki olarak sunulur; otomatik çözülmez |
| D — Belirsiz | Kaynağı/statüsü açıkça doğrulanamayan | Belirsiz olarak korunur; kanonlaştırılmaz |

Özellikle biyolojik yaşlanmanın durdurulması ve insan kökeni gibi Markdown'a özgü ayrıntılar, sırf mevcut Markdown dosyasında `kanon` yazdığı için otomatik olarak ana JSON kaydına taşınmayacaktır. Bunların proje sahibinin önceki açık kararlarıyla doğrulanması gerekir.

## 5. Uygulama alt aşamaları

### A1 — Kayıt mimarisi ve içerik envanteri
- **Durum:** Tamamlandı; rapor: `reports/2026-11-17-asama-a1-zaman-sovalyesi-uzlastirma.md`
- Tek esas kayıt ilkesini kesinleştirecek teknik tasarım.
- Zaman Şövalyesi JSON/Markdown iddialarının madde madde karşılaştırılması.
- Kullanıcı onayı gerektiren içeriklerin ayrı listelenmesi.
- Bu aşama sonunda kullanıcıya içerik uzlaştırma tablosu sunulması.

**Çıkış koşulu:** Her ayrıntının kaynağı ve önerilen işlemi görünür; hiçbir yeni kanon kararı verilmemiş olmalı.

### A2 — Zaman Şövalyesi kaydının birleştirilmesi
- **Durum:** Tamamlandı; rapor: `reports/2026-11-17-asama-a2-zaman-sovalyesi-birlestirme.md`
- Kullanıcı tarafından onaylanan ayrıntıları `character-0001.json` kaydına işleme.
- Markdown belgesini kararlaştırılan türe (türetilmiş açıklama veya taslak/araştırma) dönüştürme.
- Dosya adı ve bağlantı güncellemelerini yapma.
- Kanon indeksini tek esas kayıtla eşleştirme.

**Çıkış koşulu:** Aynı karakter için ikinci ve bağımsız kanon kimliği kalmamalı; içerik kaybı veya onaysız statü değişikliği olmamalı.

### A3 — Kanon indeksi ve karar günlüğü
- **Durum:** Tamamlandı; rapor: `reports/2026-11-17-asama-a3-kanon-indeksi-karar-gunlugu.md`
- Kanon indeksindeki her girdiyi dosya ve kayıt kimliğiyle karşılaştırma.
- Doğrulanabilen kararları kaynaklarıyla günlüğe ekleme.
- Bilinmeyen tarihleri tahmin etmeme.
- Kayıtlar arası ilişki alanlarının görevini netleştirme.

**Çıkış koşulu:** Kanon indeksi ile esas kayıtlar tutarlı; karar günlüğü yalnızca doğrulanmış kararları içeriyor olmalı.

### A4 — İlişki tutarlılığı ve kapanış
- **Durum:** Tamamlandı; rapor: `reports/2026-11-17-asama-a4-iliski-tutarliligi-kapanis.md`
- `relationships` ve `related_entities` kullanımlarının depo genelinde taranması.
- Tek ilişki modeline geçiş için geriye dönük uyumluluk değerlendirmesi.
- Kimlik, indeks ve ilişki tutarlılığı denetimi.
- Aşama A kapanış raporunun hazırlanması.

**Çıkış koşulu:** Kayıt kimlikleri, indeks yolları ve ilişkiler arasında doğrulanmış tutarlılık; açık kalan konular raporlanmış olmalı.

## 6. Önerilen teknik uygulama sırası

1. A1 içerik envanterini hazırla ve kullanıcıya sun.
2. Kullanıcı içerik sınıflandırmasını onayladıktan sonra A2'ye geç.
3. A2 değişikliklerini doğrula ve ardından A3'ü uygula.
4. A4 kapsamında depo genelini denetle ve kapanış raporunu oluştur.

Her alt aşama kendi test/denetim sonuçlarıyla kapatılmalıdır. Kanon içeriğine dokunan her işlem kullanıcı onayına bağlıdır.

## 7. İlk uygulama için kapsam

Bu planın eklenmesi dışında mevcut kanon ve taslak dosyalarında değişiklik yapılmayacaktır. Bir sonraki somut çıktı, A1 kapsamında hazırlanacak Zaman Şövalyesi içerik uzlaştırma tablosudur.

---

**Durum:** Aşama A — Kayıt Bütünlüğü tamamlandı (A1–A4).  
**Kanon etkisi:** Yalnızca proje sahibinin açıkça onayladığı kararlar işlendi; teknik planın kendisi kanon kararı değildir.  
**Kapanış raporu:** `reports/2026-11-17-asama-a4-iliski-tutarliligi-kapanis.md`.
