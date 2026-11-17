# Evren Arşivi — Teknik ve Yapısal Denetim Raporu

- **Denetim tarihi:** 2026-11-17
- **Depo:** `trippes/evren-arsivi`
- **Denetlenen dal:** `main`
- **Denetim anındaki HEAD:** `a4fc9d32b9923a7cee3aa7d57fd422fca3562a74`
- **Kapsam:** Dosya ağacı, kayıt standartları, kanon indeksi, karakter kayıtları, JSON şeması, tarihsel kronoloji kapsamı ve doğrulama altyapısı.
- **Değişiklik sınırı:** Bu rapor dışında hiçbir kanon veya taslak kaydı değiştirilmemiştir. Denetim sırasında içeriklerin statüsü yükseltilmemiş, yeni bir hikâye kararı üretilmemiştir.

## 1. Yönetici özeti

Depo, tek doğruluk kaynağı ve kanon/taslak ayrımı bakımından doğru bir temel üzerine kurulmuştur. Özellikle bilinmeyen bilgilerin uydurulmaması, çelişkilerin sessizce birleştirilmemesi ve sohbet belleğinin depo yerine geçmemesi ilkeleri güçlüdür.

Bununla birlikte mevcut yapı henüz güvenilir bir arşiv iş akışını otomatik olarak koruyacak olgunlukta değildir. En önemli sorun, kanonik karakter bilgisinin iki ayrı dosyada tutulması fakat tek bir kimlik ve indeks kaydı altında birleştirilmemesidir. İkinci önemli sorun, tarihsel kronolojinin ana anlatının kapsadığı dönemin tamamını içermemesidir.

**Genel değerlendirme:** İyi kurulmuş başlangıç mimarisi; kayıt bütünlüğü, indeksleme, tarihsel kapsam ve otomatik doğrulama bakımından iyileştirme gerekli.

## 2. Olumlu bulgular

1. README ve `00_ANAYASA/KANON_ILKELERI.md`, kanon ile taslağı açık biçimde ayırıyor.
2. Öncelik sırası tanımlanmış: proje sahibinin güncel kararı, karar günlüğü, kanon kayıtları, incelemedeki kayıtlar ve taslaklar.
3. Bilinmeyen bilgilerin açıkça bilinmeyen olarak bırakılması ve çelişkilerin kayıt altına alınması ilkeleri mevcut.
4. `01_EVREN/temel-anlati-onermesi.json` içindeki gizemli gücün kimliğinin ve niteliğinin henüz belirlenmediği açıkça korunmuş.
5. `01_EVREN/temel-zaman-cizgisi.json`, Cem'in doğumuna kadar tarihsel akışın gerçek tarihle aynı olduğunu; doğumdan sonraki gelişmelerin ayrıca kararlaştırılacağını belirtiyor.
6. `08_CALISMA/sah-cem-hikaye-mimarisi-taslak.md` açıkça kanon dışı çalışma taslağı olarak işaretlenmiş. Bu, henüz karara bağlanmamış gizli şehir ve askerî yapılanma fikirlerinin yanlışlıkla kanon sayılmasını önlüyor.
7. Denetlenen yedi JSON dosyasının tamamı JSON sözdizimi açısından başarıyla ayrıştırıldı. Bu kontrol, JSON Schema doğrulaması yerine geçmez.

## 3. Bulgular ve risk düzeyleri

### BULGU-01 — Zaman Şövalyesi kaydında çift kayıt / kimlik bütünlüğü sorunu

**Önem:** Yüksek

İlgili dosyalar:
- `04_KARAKTERLER/ana-karakterler/character-0001.json`
- `04_KARAKTERLER/zaman_sovalyesi.md`
- `07_KANON/kanon-indeksi.json`

JSON karakter kaydının kimliği `character-0001`; Markdown dosyasının kendi içinde belirttiği kayıt kimliği ise `karakter-zaman-sovalyesi`. İkinci kimlik kayıt standartlarındaki ASCII, tür-0001 biçimiyle de uyumlu değil. Kanon indeksi yalnızca JSON dosyasını `character-0001` olarak listeliyor; Markdown dosyasının ayrı bir indeks girdisi yok.

Markdown dosyası, JSON kaydında bulunmayan ek kanonik ayrıntılar içeriyor: DNA kodlamasıyla biyolojik yaşlanmanın durdurulması, insan kökeni, atasını öldürme kuralının ayrıntıları, zamandan bağımsız merkez ve kuantum bilgisayarının gözlem işlevleri. Bu durum hangi dosyanın esas kayıt olduğu konusunda belirsizlik yaratıyor.

**Öneri:** Tek bir karakter kimliği ve tek bir esas yapılandırılmış kayıt kullanılmalı. Markdown dosyası ya bu kaydın açıklayıcı görünümü olarak tanımlanmalı ya da kanonik içeriği JSON kaydına taşındıktan sonra arşivlenmeli. İki dosyada bağımsız ve farklı kimliklerle aynı karakterin kanonik tanımı sürdürülmemeli. Bu bir yapısal öneridir; hangi içeriğin kanonda kalacağı proje sahibinin onayını gerektirir.

### BULGU-02 — Kanon indeksi eksik ve karar günlüğü boş

**Önem:** Yüksek

`07_KANON/kanon-indeksi.json` üç kayıt içeriyor: `premise-0001`, `premise-0002` ve `character-0001`. Kanonik olarak işaretlenmiş `04_KARAKTERLER/zaman_sovalyesi.md` bu indekste ayrı bir kayıt olarak yer almıyor.

`07_KANON/karar-gunlugu.md` ise yalnızca boş karar şablonundan oluşuyor. Kanon ilkeleri, karar günlüğünü öncelik sıralamasında indeksin önüne koyduğu için, geçmişte alınan açık kararların burada bulunmaması kararların izlenebilirliğini zayıflatıyor.

**Öneri:** Mevcut kanon kayıtları için geriye dönük karar kaydı oluşturulması değerlendirilmeli. Ancak tarih ve karar metni yalnızca doğrulanabilen proje sahibi beyanlarından aktarılmalı; bilinmeyen tarihler tahmin edilmemeli. İndeks ile dosya sistemi arasında otomatik eşleşme kontrolü eklenmeli.

### BULGU-03 — Tarihsel kronoloji ana hikâye kapsamını tamamlamıyor

**Önem:** Yüksek

İlgili dosya: `03_TARIH/cem-sultan-tarihsel-kronoloji.md`

Ana zaman çizgisi önermesi hikâyenin Cem Sultan'ın doğumundan ölümüne kadar sürdüğünü belirtiyor. Mevcut tarihsel kronoloji ise 23 Aralık 1459'dan 29 Temmuz 1482'de Rodos'a ulaşmasına kadar olan dönemi kapsıyor. Belgenin kendi kapsam notu da Avrupa'daki sonraki hayatın ayrı dosyada araştırılması gerektiğini söylüyor.

Bu nedenle Cem'in Rodos sonrasındaki hayatı, Avrupa'daki diplomatik süreç, Papalık ve diğer aktörlerle ilişkiler, esaret dönemi ve ölümüne uzanan kronoloji henüz arşivde tamamlanmış değil.

**Öneri:** Mevcut dosyanın kapsamı açıkça korunmalı; 1482 sonrası dönem ayrı ve kaynaklandırılmış bir tarihsel araştırma dosyası olarak hazırlanmalı. Cem'in ölüm tarihi ve son dönem olayları doğrulanmadan ana kronoloji tamamlanmış kabul edilmemeli.

### BULGU-04 — JSON Schema kimliği örnek adres olarak bırakılmış

**Önem:** Orta

İlgili dosya: `schemas/entity.schema.json`

Şema içindeki `$id` alanı `https://example.invalid/evren-arsivi/schemas/entity.schema.json`. Bu, gerçek bir şema tanımlayıcısı değil, örnek amaçlı bir yer tutucu.

**Öneri:** Depoda kalıcı ve tutarlı bir şema kimliği belirlenmeli. Şema sürümleme ve referanslama yaklaşımı kararlaştırılmadan rastgele bir URL kullanılmamalı.

### BULGU-05 — Şema, kayıtların bütünlüğünü tam olarak denetlemiyor

**Önem:** Orta

Şema:
- `additionalProperties: true` kullanıyor; bu esnekliği artırsa da yazım hatalı veya beklenmeyen alanların fark edilmesini zorlaştırabilir.
- `relationships`, `aliases`, `path` gibi mevcut kayıtlarda kullanılan alanları tanımlamıyor.
- `related_entities` değerlerinin gerçekten var olan kimliklere işaret ettiğini doğrulamıyor.
- `id` biçimini denetliyor ancak dosya adı, kayıt kimliği ve kanon indeksi arasındaki eşleşmeyi denetlemiyor.

**Öneri:** Şema, kayıt türlerine göre genişletilmeli; ilişkiler ve indeks bütünlüğü için JSON Schema'nın tek başına yeterli olmadığı yerde ayrı bir doğrulama betiği kullanılmalı. Esnek alan politikası bilinçli biçimde kararlaştırılmalı.

### BULGU-06 — Kayıt standartları ile mevcut dosya adları arasında uyumsuzluk

**Önem:** Düşük

`00_ANAYASA/KAYIT_STANDARTLARI.md` dosya adlarının küçük harfli ASCII ve tire ile ayrılmış olmasını istiyor. `04_KARAKTERLER/zaman_sovalyesi.md` dosya adı alt çizgi kullanıyor.

**Öneri:** Dosya adı standardı tutarlı uygulanmalı. Dosya yeniden adlandırılacaksa tüm bağlantılar, indeksler ve metin içi referanslar birlikte güncellenmeli.

### BULGU-07 — Tarih ve kaynak metaverileri eksik

**Önem:** Orta

Kanonik JSON kayıtlarında `created_at` ve `updated_at` alanları zorunlu alan olarak mevcut ancak değerleri `null`. Kaynaklar çoğunlukla “bu sohbet içindeki açık tanım” biçiminde kaydedilmiş. Bu, kararın kaynağını genel olarak gösteriyor ancak hangi tarihli karar veya hangi karar günlüğü girdisi olduğunu tek başına bulmayı sağlamıyor.

**Öneri:** Yeni kayıtlar için oluşturulma/güncellenme zamanları gerçek kayıt işlemi sırasında doldurulmalı. Önceki tarihler bilinmiyorsa geriye dönük tahmin yapılmamalı. Proje sahibi kararları mümkün olduğunda kalıcı karar kimlikleriyle ilişkilendirilmeli.

### BULGU-08 — Otomatik kalite kontrol altyapısı henüz görünmüyor

**Önem:** Orta

Denetlenen `main` dosya ağacında test klasörü veya `.github/workflows` altında GitHub Actions iş akışı bulunmuyor. Bu nedenle JSON sözdizimi, şema uygunluğu, benzersiz kimlikler, indeks-dosya eşleşmesi ve kırık ilişkiler her değişiklikte otomatik olarak kontrol edilmiyor.

**Öneri:** Küçük ve bağımlılığı düşük bir doğrulama aracı ile GitHub Actions iş akışı eklenmeli. En azından JSON parse, JSON Schema, benzersiz ID, kanon indeksi-dosya eşleşmesi, ilişkili ID çözümleme ve beklenen klasör yapısı denetlenmeli.

### BULGU-09 — Raporlama alanı başlangıç deposunda yok

**Önem:** Düşük

Denetim öncesi dosya ağacında `reports/` klasörü bulunmuyordu. Bu rapor klasörü ilk kez oluşturmaktadır.

**Öneri:** Denetim, karar ve sürüm raporları için `reports/` altında tarihli ve değiştirilmeyen raporlar tutulabilir.

## 4. Kayıtlar arası ilişki kontrolü

Mevcut üç kanon indeksi girdisinin dosya yolları depoda bulunuyor. `character-0001` kaydının `related_entities` alanındaki `premise-0002` kimliği mevcut kanon indeksindeki bir kayda karşılık geliyor.

Bununla birlikte:
- `zaman_sovalyesi.md` kendi kimliğini ayrı tanımlıyor ve indekslenmiyor.
- `premise-0001` ve `premise-0002` kayıtlarında `related_entities` alanları boş. Bu tek başına hata değildir; ancak karakter ile anlatı önermesi arasındaki ilişki yalnızca karakter kaydında tutuluyor.
- Karakter JSON kaydında hem `related_entities` hem de `relationships` bulunuyor. İki alanın farklı amaçları açıkça belgelenmezse aynı ilişkinin iki yerde farklılaşması riski var.

## 5. Tarihsel / alternatif tarih / bilimkurgu ayrımı

Mevcut arşivde bu ayrımın temeli doğru kurulmuş:

- **Tarihsel katman:** Cem Sultan kronolojisi, tarihsel kaynaklarla desteklenen referans belgesi olarak tanımlanmış.
- **Alternatif tarih katmanı:** Fatih'in ölümünden sonra Cem'in tahta çıkması ana karşı-olgusal kırılma noktası olarak kaydedilmiş.
- **Bilimkurgu katmanı:** Zaman Şövalyesi'nin zaman yolculuğu ve paralel dallar mekanizması ayrı karakter belgesinde tutulmuş.
- **Çalışma taslağı:** Gizli şehir ve 500.000 kişilik askerî yapılanma, açıkça kanon dışı taslakta tutulmuş.

Bu ayrım korunmalı. Özellikle tarihsel kronolojideki boşluklar, alternatif tarih taslağına göre doldurulmamalı; kurgu müdahaleleri tarihsel olay gibi yazılmamalı.

## 6. Önceliklendirilmiş iyileştirme planı

### Aşama A — Kayıt bütünlüğü
1. Zaman Şövalyesi için tek esas kayıt ve kimlik kararı.
2. Kanon indeksinin tüm kanonik kayıtlarla eşleştirilmesi.
3. Karar günlüğünün doğrulanabilir geçmiş kararlarla başlatılması.
4. `related_entities` ve `relationships` alanlarının görevlerinin netleştirilmesi.

### Aşama B — Tarihsel kapsam
1. Cem Sultan'ın 1482 sonrası hayatının kaynaklandırılmış kronolojisi.
2. Avrupa'daki aktörler ve diplomatik gelişmelerin ayrı kayıtlarla ele alınması.
3. Cem'in ölümüne kadar ana zaman çizgisi kapsamının tamamlandığının kontrolü.

### Aşama C — Teknik doğrulama
1. JSON Schema kimliğinin ve kapsamının düzeltilmesi.
2. Kayıt türlerine uygun alan şemalarının oluşturulması.
3. ID, dosya yolu, indeks ve ilişkiler için doğrulama aracı.
4. GitHub Actions ile her değişiklikte otomatik kontrol.

### Aşama D — Arşiv yönetişimi
1. Tarihli denetim ve karar raporlarının `reports/` altında tutulması.
2. Yeni kayıt ve kanon değişikliği için standart iş akışının belirlenmesi.
3. Taslak → incelemede → kanon geçişinin açık onay ve karar kaydıyla yapılması.

## 7. Bu denetimde yapılmayanlar

- Kanonik karakter veya evren kayıtları değiştirilmedi.
- Zaman Şövalyesi'nin iki dosyasından hangisinin esas kabul edileceğine karar verilmedi.
- Yeni kanon kararı oluşturulmadı.
- Cem Sultan'ın tarihsel kronolojisine yeni olay veya tarih eklenmedi.
- Şema veya otomatik test kodu yazılmadı.
- Tarihsel kaynakların bağımsız akademik doğrulaması yapılmadı; mevcut dosyanın kapsamı ve arşiv içindeki konumu incelendi.

## 8. Sonuç

Evren Arşivi'nin temel ilkeleri doğru yönde. Şu aşamada yeni hikâye ayrıntıları eklemekten önce kayıt bütünlüğünü ve tarihsel referans kapsamını güçlendirmek daha sağlıklı olacaktır.

**İlk önerilen iş:** Aşama A kapsamında Zaman Şövalyesi'nin tekil kayıt yapısını ve kanon indeksini düzeltmek. Bu işlemden önce hangi mevcut ayrıntıların kanon kabul edildiği, proje sahibinin kararına göre ayrıştırılmalıdır.

---

*Bu rapor, denetim anındaki `main` dalının fotoğrafıdır. Sonraki değişiklikler bu raporu geriye dönük olarak değiştirmez; yeni denetimler yeni tarihli raporlar oluşturmalıdır.*
