# Aşama B5 — Şah Cem Kaynak, Kanon ve Çelişki Denetimi

- Tarih: 2026-11-17
- Aşama: B5 — Kaynak, kanon ve çelişki denetimi
- Durum: TAMAMLANDI — denetim raporu
- Kapsam: B1–B4 çıktıları, Şah Cem karakter taslağı, karar matrisi, kanon karar günlüğü, kanon indeksi, çelişki kaydı ve ilgili temel evren önermeleri
- Kanon etkisi: Yok
- Tarihsel kayıt etkisi: Yok
- Yöntem: Depodaki mevcut dosyalar GitHub üzerinden yeniden okundu; kararların statüsü, dayanağı, kanon kayıtlarıyla uyumu ve açık çelişki/gerilim alanları karşılaştırıldı.

## 1. Yönetici özeti

B1–B4 çalışmaları tarihsel temel ile alternatif kurgu katmanını büyük ölçüde doğru ayırıyor. Bununla birlikte B5, karakter dosyasının kanona alınmasından önce çözülmesi gereken iki yüksek öncelikli kapsam/terminoloji sorunu ve iki önemli kayıt izlenebilirliği sorunu tespit etti.

Başlıca bulgular:

1. Kanonik temel zaman çizgisi, hikâyenin Cem'in doğumunda başlayıp ölümünde sona erdiğini söylüyor. B2'deki onaylı karar ise Cem'in saltanatından sonra oğlu Sultan Oğuz'un ayrı saltanatını öngörüyor. Oğuz'un saltanatı Cem'in ölümünden sonra başlayacaksa anlatının zaman kapsamı mevcut kanon önermesiyle uyuşmaz. Bunun bir çelişki mi yoksa hikâye kapsamının genişletilmesi mi olduğu kararlaştırılmalı.
2. Kullanıcının reddettiği “Cem Sultan” biçimi, kanonik temel zaman çizgisi ve temel anlatı önermesinin ad, özet ve açıklamalarında tekrar tekrar geçiyor. Bu, anlatı terminolojisi ile eski kayıt dili arasında düzeltilmesi gereken bir tutarsızlık.
3. B2'de K1 olarak sınıflandırılan Cem'e ait açık kullanıcı kararları, B2 raporunda doğru envanterlenmiş; ancak karar günlüğünde henüz ayrı karar girdileri olarak kayıtlı değil. B2 raporu kendi başına kanon oluşturmadığını açıkça söylüyor.
4. Kanonik temel anlatı önermesi, Cem'in arkasındaki gücün kimliğini, yapısını ve Cem'le ilişkisini henüz bilinmeyen olarak tanımlıyor. B2'de ise Zaman Şövalyesi'nin Cem'in hedefini bildiği ve ona yardım ettiği açık kullanıcı kararı olarak sınıflandırılmış. Bu iki kayıt güncel proje bilgisini aynı açıklıkta yansıtmıyor; temel önerme gözden geçirilmeli.

Bu rapor hiçbir bulguyu kendiliğinden çözmez. Kanon dosyaları, çelişki listesi, karar günlüğü ve karakter taslağı değiştirilmemiştir.

## 2. İncelenen kayıt envanteri

Aşama B belgeleri:
- reports/2026-11-17-asama-b-cem-sultan-karakter-plani.md
- reports/2026-11-17-asama-b1-tarihsel-temel-denetimi.md
- reports/2026-11-17-asama-b2-kurgu-kararlari-matrisi.md
- reports/2026-11-17-asama-b3-sah-cem-karakter-taslagi.md
- reports/2026-11-17-asama-b4-sah-cem-tutarlilik-denetimi.md
- 04_KARAKTERLER/ana-karakterler/sah-cem-taslak.md

Kanon ve evren kayıtları:
- 07_KANON/karar-gunlugu.md
- 07_KANON/kanon-indeksi.json
- 07_KANON/celiskiler.json
- 00_ANAYASA/KANON_ILKELERI.md
- 01_EVREN/temel-zaman-cizgisi.json
- 01_EVREN/temel-anlati-onermesi.json

Tarihsel başvuru:
- 03_TARIH/cem-sultan-tam-kronoloji-1459-1499.md
- B1 raporunda listelenen tarihsel olay ve kişi kayıtları.

## 3. Karar statüsü denetimi

B2 karar matrisi K1, K2, T, A ve R sınıflarını birbirinden ayırmaktadır. Bu sınıflandırma yöntemi yerindedir. Ancak bu statüler, kanon günlüğündeki karar kayıtlarıyla aynı şey değildir.

### 3.1. K1 — açık kullanıcı kararları

B2'de altı madde K1 olarak sınıflandırılmıştır:

- Cem'in Cihan Hâkimiyeti ideali.
- Zaman Şövalyesi'nin bu hedefi bilmesine rağmen Cem'e yardım etmesi.
- Alternatif hanedan çizgisinde Cem'den sonra oğlu Oğuz'un ayrı saltanatı.
- Erkek hükümdarlarda Sultan unvanının isimden önce gelmesi.
- Cem'in Cem Han ve Şah Cem gibi Türkçe unvanları tercih etmesi.
- “Cem Sultan” ve “Oğuz Sultan” biçimlerinin anlatıda tercih edilmemesi.

Bu kararlar B2 matrisinde açık kullanıcı kararı olarak kaydedilmiştir. Ancak karar günlüğünde şu anda yalnızca DEC-0001, DEC-0002 ve DEC-0003 vardır; bunlar Zaman Şövalyesi'nin zaman sistemi, insan kökeni ve gerçeklik bilgisi/zaman hâkimiyetiyle ilgilidir. B2-K01–B2-K06 için ayrı DEC girdisi bulunmamaktadır.

**Denetim sonucu:** B2 karar matrisi, kullanıcı kararlarının envanteridir; karar günlüğünün yerine geçmez. B2-K01–B2-K06 kararlarının karar günlüğüne aktarılması, kararların kapsamı ve kaynak izi proje sahibi tarafından onaylandıktan sonra yapılmalıdır. B5 bu aktarımı yapmaz.

### 3.2. K2 — önceki karar kaydı olarak izlenen unsurlar

B2-K07–B2-K11 maddeleri önceki proje çalışma kaydında onaylı karar olarak izlenmektedir; ancak B2 raporu doğrudan kullanıcı mesajı eşleştirmesinin yeniden doğrulanamadığını açıkça belirtir.

Bu nedenle aşağıdaki unsurların kanon günlüğüne aktarılmasından önce karar kaynağı teyit edilmelidir:

- Cem ile Zaman Şövalyesi'nin 8–10 yaş aralığında ilk yüz yüze karşılaşması.
- İç Anadolu'daki gizli askerî yapılanma.
- 500.000 çocuk ve binlerce yetişkin görevli/uzman.
- Osmanlı'yı izleyen gizli istihbarat ağı.
- Cem'in yapılanmayı erken öğrenip gerçek ölçeği daha sonra öğrenmesi.

**Denetim sonucu:** K2 maddeleri kanon olarak varsayılmamalı; karar kaynağı doğrulanana kadar B2'nin belirttiği teyit statüsünde tutulmalıdır.

### 3.3. T ve A — taslak ve açık tasarım alanları

B2-T01–B2-T10 çalışma taslağı ayrıntılarıdır. Bunlar arasında gizli şehrin kuruluş zamanı ve yüzey yerleşimi, çocukların yaşları ve kaynak evrenleri, yetiştirme modeli, yetişkinlerin gönüllülüğü, Zaman Şövalyesi'nin Osmanlı stratejisi, bölgesel etki alanı ve teknoloji aktarım ilkesi bulunur.

B2-A maddeleri ise henüz karara bağlanmamış konulardır. Özellikle 500.000 çocuk ile 500.000 kişilik süvari kuvvetinin ilişkisi, şehrin lojistik sürdürülebilirliği, istihbarat ağının çalışma biçimi ve Sultan Oğuz'un hanedan içindeki konumu açık kalmalıdır.

**Denetim sonucu:** B3 taslağı ve B4 raporu bu ayrımları genel olarak korumuştur. T/A unsurlarının K1/K2 veya kanon statüsüne yükseltildiğine dair bir işlem yapılmamıştır.

## 4. Kanon kayıtlarıyla karşılaştırma

### 4.1. Temel zaman çizgisi ve Sultan Oğuz'un saltanatı

01_EVREN/temel-zaman-cizgisi.json kanonik kaydı, anlatının Cem'in doğumuyla başladığını ve ölümüyle sona erdiğini belirtir. Aynı kayıt, Cem'in doğumundan sonraki gelişmelerin ayrıca kararlaştırılacağını da söyler.

B2-K03 ise Cem'in saltanatını oğlu Oğuz'un ayrı saltanatının izlemesini açık kullanıcı kararı olarak sınıflandırır.

Bu iki ifade ancak şu ihtimallerden biri açıklığa kavuşturulursa birlikte tutarlı hâle gelir:

- Anlatının ana hikâyesi Cem'in ölümüyle biter; Sultan Oğuz'un saltanatı yalnızca epilog, hanedan kronolojisi veya sonraki dönem kaydı olarak yer alır.
- Anlatının kapsamı Sultan Oğuz'un saltanatını da içerecek şekilde genişletilir.
- Cem'in saltanatının sona ermesi ile ölümü arasında Oğuz'un tahta çıkmasını sağlayan farklı bir veraset düzeni kurulur.

Bu seçeneklerden hiçbiri mevcut kayıtlarda kararlaştırılmış değildir.

**Önem:** Yüksek. Bu, yalnızca karakter ayrıntısı değil, evrenin ana zaman kapsamı ve hanedan kronolojisiyle ilgilidir.

### 4.2. “Cem Sultan” terminolojisi

Kullanıcının güncel terminoloji kararı, “Cem Sultan” ve “Oğuz Sultan” biçimlerini anlatı dilinde reddeder; erkek hükümdar unvanının isimden önce kullanılmasını ve Cem'in Türkçe unvan tercihlerini esas alır.

Buna karşın kanonik temel zaman çizgisi ve temel anlatı önermesi dosyalarında “Cem Sultan” biçimi:
- kayıt adlarında,
- özetlerde,
- açıklamalarda,
- notlarda

kullanılmaktadır.

B2 matrisi tarihsel kaynak başlıkları ve alıntılar için ayrı bir istisna tanımlamıştır. Fakat temel evren önermelerindeki kullanım bir tarihsel kaynak alıntısı değildir; eski kayıt terminolojisidir.

**Denetim sonucu:** Bu kanonik kayıtlar anlatı terminolojisiyle uyumlu değildir. Proje sahibi, kayıtların “Sultan Cem” veya anlatının tercih edeceği başka biçimlerle güncellenmesini onaylamalıdır. Dosya yolu ve teknik ID'ler bu nedenle değiştirilmek zorunda değildir.

### 4.3. Gizemli güç ve Zaman Şövalyesi

01_EVREN/temel-anlati-onermesi.json, Cem'in arkasında bir güç bulunduğunu; bu gücün kimliği, yapısı, kökeni, amaçları ve Cem'le ilişkisinin henüz bilinmediğini söyler.

B2-K02 ise Zaman Şövalyesi'nin Cem'in Cihan Hâkimiyeti hedefini en başından bildiğini ve buna rağmen ona yardım ettiğini açık kullanıcı kararı olarak sınıflandırır. DEC-0001 de Zaman Şövalyesi'nin Cem'in yaşadığı dala geldiğini ve Cem'le karşılaştığını zaten kayda geçirmiştir.

Burada “gücün tüm yapısı ve ayrıntıları henüz bilinmiyor” ifadesi ile “gücün kimliği ve Cem'e yardım ilişkisi bilinmiyor” ifadeleri birbirinden ayrılmalıdır. İlk ifade hâlâ geçerli olabilir; ikincisi güncel kararlarla eskimiş görünmektedir.

**Denetim sonucu:** temel-anlati-onermesi.json güncel proje bilgisini yansıtacak şekilde gözden geçirilmeye adaydır. Ancak gizemli gücün Zaman Şövalyesi ile özdeşliği, gizli yapılanmayla ilişkisinin kapsamı ve ne kadarının hikâye başında bilinmez kalacağı proje sahibi onayı olmadan yeniden yazılmamalıdır.

### 4.4. Kanon indeksi ve Cem taslağının statüsü

07_KANON/kanon-indeksi.json üç kanonik kayıt listeler: premise-0001, premise-0002 ve character-0001.

Şah Cem taslağı:
- 04_KARAKTERLER/ana-karakterler/sah-cem-taslak.md yolundadır.
- Kanon indeksi içinde yer almaz.
- Ayrı bir karakter ID'si almamıştır.
- Başlığında ve içeriğinde taslak olduğu açıkça belirtilmiştir.

Bu durum B3 ve B4 raporlarıyla uyumludur.

**Denetim sonucu:** Şah Cem karakter taslağının yanlışlıkla kanona alınması veya kanon indeksine eklenmesi söz konusu değildir. B6 ve B7 ayrımı korunmalıdır.

## 5. Tarihsel kaynak ve alternatif kurgu sınırı

B1 raporu ile ana tarihsel kronoloji, tarihsel Cem'in yaşamına ilişkin belirsizlikleri korumaktadır. Özellikle:

- Doğum tarihi için 23 Aralık / 3 Aralık 1459 farkı.
- Rodos'a varış için 26 / 29 Temmuz 1482 farkı ve Vâkıât'taki hicrî/harita notlarının takvim sorunu.
- Roma'ya geliş için 4 / 13 Mart 1489 farkı.
- Rodos ve Papalık anlaşmalarındaki ödeme miktarı/para birimi ayrımı.
- Fatih'in Cem'i kesin veliaht tayin ettiğinin kanıtlanmamış olması.
- Otlukbeli sonrasında lalaların biatının Cem'in bizzat planladığı bir girişim olarak gösterilememesi.
- Gedik Ahmed Paşa'nın gizli Cem taraftarlığının kesin olmaması.
- Oğuz Han Çelebi hakkındaki öldürme emrinin, emrin uygulanma biçimini ve ölüm sonucunu tek başına kanıtlamaması.
- Cem'in zehirlenerek öldürüldüğünün kesinleşmemiş olması.

B3 karakter taslağı ve B4 denetimi bu ihtiyatları genel olarak korumaktadır. Alternatif kurgu unsurlarının tarihsel kronolojiye sessizce eklenmesine dair bulgu yoktur.

**Denetim sonucu:** Tarihsel kaynakların güven düzeyi veya tarihsel belirsizlikler bakımından B3 taslağını geçersiz kılan yeni bir sorun saptanmadı. B1'de belirtilen araştırma boşlukları devam etmektedir; B5 bunları tarihsel gerçekmiş gibi tamamlamaz.

## 6. Çelişki ve risk kayıtları

Aşağıdaki sınıflandırma, mevcut dosyaların birlikte okunmasından çıkan denetim bulgularıdır. 07_KANON/celiskiler.json dosyasına henüz yeni kayıt eklenmemiştir.

| ID | Bulgu | Tür | Öncelik | Gerekli işlem |
|---|---|---|---|---|
| B5-01 | Cem'in ölümünde biten kanonik anlatı kapsamı ile sonrasında ayrı saltanat sürecek Sultan Oğuz kararı arasındaki kapsam gerilimi | Kanon kapsamı / kronoloji | Yüksek | Anlatı kapsamı ve Oğuz saltanatının hikâyedeki yeri kararlaştırılmalı |
| B5-02 | Kanonik temel önermelerde “Cem Sultan” kullanımının, kullanıcının reddettiği anlatı terminolojisiyle çelişmesi | Terminoloji / kayıt tutarlılığı | Yüksek | Kanonik metinlerin adlandırma dili onayla güncellenmeli |
| B5-03 | B2-K01–K06 açık kullanıcı kararlarının karar günlüğünde ayrı DEC kayıtlarıyla izlenmemesi | Kanon izlenebilirliği | Orta-yüksek | Karar kapsamı ve kaynak izi onaylanarak günlüğe aktarılmalı |
| B5-04 | temel-anlati-onermesi.json gizemli gücün kimliği ve Cem'le ilişkisini bilinmeyen sayarken sonraki kararların Zaman Şövalyesi'ni tanımlaması | Kayıt güncelliği / kapsam | Orta-yüksek | Bilinen kimlik ile bilinmeyen yapı/amaç/kapasite ayrıştırılmalı |
| B5-05 | B2-K07–K11 maddelerinin karar günlüğünde doğrudan karar iziyle eşleştirilmemiş olması | Kaynak izlenebilirliği | Orta | Önceki kullanıcı onayı teyit edilmeli; teyit edilmeden kanonlaştırılmamalı |
| B5-06 | Sultan Oğuz'un tarihsel Oğuz Han Çelebi ile kimlik ve akıbet ilişkisi | Alternatif tarih sürekliliği | Yüksek | Tarihsel ayrışma noktası ve hanedan bağlantısı tasarlanmalı |
| B5-07 | Cem Han / Şah Cem / Sultan Cem kullanımının dönemsel ve anlatıcı düzeyindeki hiyerarşisinin belirlenmemiş olması | Terminoloji tasarımı | Orta | Unvan kullanım çizelgesi oluşturulmalı |

B5-01, B5-02 ve B5-04 kanonik temel kayıtların güncelliğini etkiler. B5-03 ve B5-05 ise kararların izlenebilirliğiyle ilgilidir. B5-06 ve B5-07, B4'te saptanan tasarım risklerini teyit eder.

## 7. B5 kabul ölçütleri

- [x] B1–B4 raporları yeniden okundu ve birbirleriyle karşılaştırıldı.
- [x] B2 karar matrisi K1/K2/T/A/R sınıfları bakımından denetlendi.
- [x] K1 kararlarının karar günlüğünde bulunup bulunmadığı kontrol edildi.
- [x] K2 maddelerinin kaynak teyidi ihtiyacı korundu.
- [x] Kanon indeksi ve karar günlüğü karşılaştırıldı.
- [x] Temel zaman çizgisi ve temel anlatı önermesi güncel kararlarla karşılaştırıldı.
- [x] Tarihsel kronolojideki belirsizliklerin B3'e yanlış kesinlikle aktarılmadığı kontrol edildi.
- [x] Oğuz Han / Sultan Oğuz süreklilik sorunu yeniden değerlendirildi.
- [x] Taslak karakter dosyasının kanon indeksine yanlışlıkla eklenmediği doğrulandı.
- [x] Tespitler önceliklendirilerek raporlandı.
- [x] Kanon ve tarihsel kayıt dosyaları değiştirilmedi.

## 8. B5 sonucu ve sonraki aşama

**B5 tamamlandı — denetim raporu hazır.**

Şah Cem taslağı, tarihsel temel ve alternatif kurgu ayrımını korumaktadır; fakat mevcut hâliyle doğrudan kanona alınmaya hazır değildir. Bunun nedeni karakter mimarisinin başarısız olması değil, kanonik temel kayıtların terminoloji ve anlatı kapsamı bakımından güncel kararlarla uzlaştırılmamış olmasıdır.

**B6'ya geçiş için önerilen sıra:**

1. Önce B5-01: Sultan Oğuz'un saltanatının ana hikâyenin zaman kapsamına nasıl yerleşeceği kararlaştırılmalı.
2. B5-02: Kanonik kayıtlardaki hükümdar adlandırmaları gözden geçirilmeli.
3. B5-03 ve B5-05: Kullanıcı kararları karar günlüğüyle eşleştirilmeli; yalnızca teyitli olanlar kayda alınmalı.
4. B5-04: Gizemli güç önermesinin bilinen ve bilinmeyen yönleri ayrıştırılmalı.
5. B5-06 ve B5-07: Sultan Oğuz sürekliliği ile unvan kullanım çizelgesi karakter taslağına işlenmeden önce karara bağlanmalı.

B6, bu rapor ve kullanıcı değerlendirmesi doğrultusunda düzeltme aşamasıdır. **B7 ise yalnızca karakter dosyasının kanona alınmasına ilişkin ayrıca ve açık kullanıcı onayıyla yürütülebilir.**

---

**Belge sonu — B5 denetim raporudur; yeni kanon kararı veya kanon değişikliği içermez.**
