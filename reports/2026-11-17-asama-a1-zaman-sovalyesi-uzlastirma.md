# A1 — Zaman Şövalyesi Kayıt ve İçerik Uzlaştırma Envanteri

- **Tarih:** 2026-11-17
- **Depo:** `trippes/evren-arsivi`
- **Dal:** `main`
- **Aşama:** A1 — Kayıt mimarisi ve içerik envanteri
- **Belge türü:** Teknik envanter ve karar hazırlık raporu
- **Kanon etkisi:** Yok; bu rapor hiçbir karakter kaydını veya kanon statüsünü değiştirmez.

## 1. Amaç ve yöntem

Bu rapor, Zaman Şövalyesi için mevcut iki dosyayı karşılaştırır:

1. Esas yapılandırılmış kayıt adayı: `04_KARAKTERLER/ana-karakterler/character-0001.json`
2. Ayrıntılı Markdown belgesi: `04_KARAKTERLER/zaman_sovalyesi.md`

Karşılaştırmada üç kanıt katmanı birbirinden ayrılmıştır:

- **JSON kaydı:** Depoda yapılandırılmış karakter kaydında bulunan bilgi.
- **Markdown kaydı:** İkinci belgede bulunan bilgi.
- **Proje sahibi tarafından daha önce açıkça kararlaştırılmış bilgi:** Önceki proje konuşmalarında açıkça belirlenmiş ve mevcut proje bağlamında doğrulanabilen kararlar. Bu katman, iki dosyadan birinde bulunmayan bir kararı da doğrulayabilir.

Bu belge yeni karar vermez. Teknik hedef, mevcut `character-0001` kimliğini koruyarak karakter için tek bir esas yapılandırılmış kayıt kullanmak; Markdown dosyasını ise A2'de verilecek karara göre türetilmiş açıklama veya kanon dışı çalışma belgesi olarak konumlandırmaktır.

## 2. Kayıt mimarisi bulguları

| Konu | Mevcut durum | Teknik değerlendirme |
|---|---|---|
| Karakter kimliği | JSON: `character-0001`; Markdown: `karakter-zaman-sovalyesi` | Aynı varlık için iki kimlik bulunuyor. Esas kimlik olarak indeksle zaten eşleşen `character-0001` korunmalı. |
| Kanon indeksi | Yalnızca JSON kaydı listelenmiş | Markdown bağımsız ikinci kanon varlığı olarak indekslenmemiş. Bu, tek esas kayıt yaklaşımıyla uyumlu; ancak Markdown başlığındaki kimlik/durum satırı yanıltıcı. |
| Kayıt statüsü | Her iki belgede de `kanon` yazıyor | Markdown'ın kendi başına ikinci bir kanon kaydı gibi görünmesine yol açıyor. A2'de bu statü ve kimlik ifadesi kaldırılmalı veya belge rolüne uygun biçimde değiştirilmelidir. |
| Alan modeli | JSON'da `related_entities` ve `relationships` birlikte var | Aynı hedefe iki ayrı alandan referans veriliyor. A1'de değiştirilmemeli; A4'te depo genelindeki kullanımlar taranmalı. |
| Kaynak izlenebilirliği | JSON kaynak alanı genel sohbet referansı içeriyor; Markdown'da madde bazında kaynak yok | Her ayrıntının hangi proje sahibi kararına dayandığı A3 karar günlüğünde ve kaynak kayıtlarında izlenebilir hâle getirilmeli. Tarih uydurulmamalı. |
| Dosya adı | `zaman_sovalyesi.md` | Kayıt standardındaki kebab-case ile uyumlu değil. Yeniden adlandırma A2'de bağlantılar tarandıktan sonra yapılabilir; bu rapor dosyayı değiştirmez. |

## 3. İçerik uzlaştırma tablosu

Sınıflar:
- **A — Doğrulanmış ortak/karar:** İki belgede ortak olan veya proje sahibinin önceki açık kararıyla doğrulanan içerik.
- **B — Yalnız Markdown:** Markdown'da bulunup JSON'da bulunmayan; ayrıca proje sahibi kararıyla doğrulanmamış içerik.
- **C — Çelişki/kapsam uyuşmazlığı:** Belgelerin kendi içinde veya birbirleriyle uyuşmayan ifade.
- **D — Belirsiz:** Açıkça karara bağlanmamış, teknik sınırları veya ayrıntıları bilinmeyen konu.

| # | Konu / iddia | JSON kaydı | Markdown kaydı / önceki açık karar | Sınıf | Önerilen işlem ve karar ihtiyacı |
|---:|---|---|---|---|---|
| 1 | Asırlardır yaşaması | Açıkça asırlardır yaşadığı belirtiliyor | Kendi öznel zamanına göre yüzyıllardır yaşadığı belirtiliyor | A | Tek esas kayıtta korunmalı. |
| 2 | Bilim insanı ve çılgın/dehaya yakın kişilik yönelimi | Çılgın bilim insanı; deliliğe yaklaşan deha yönelimi | Çılgın bilim insanı olarak tanımlanıyor | A | Korunmalı. “Çılgın” ifadesi klinik tanı olarak yorumlanmamalı. |
| 3 | Zaman makinesine sahip olması | Açıkça belirtiliyor | Zaman yolculuğu ve zaman makinesi anlatının temelinde | A | Korunmalı. Makinenin teknik çalışma biçimi ayrıca belirlenmemiş kalmalı. |
| 4 | Kuantum mekaniğinde ileri kapasite | Kuantum mekaniğine hükmedebilecek güçte olduğu yazıyor | Kuantum fiziği ve zaman mekaniği üzerinde çalıştığı belirtiliyor | A | Genel kapasite korunmalı; “hükmetme”nin sınırları belirlenmiş gibi genişletilmemeli. |
| 5 | Alternatif evrenler oluşturması | Açıkça belirtiliyor | Yolculuk/müdahalelerin yeni paralel dallar doğurduğu anlatılıyor | A | Korunmalı. Oluşum mekanizmasının ayrıntısı D olarak kalmalı. |
| 6 | Cem'i önceden tarihsel kişilik olarak tanıması | Açıkça belirtiliyor | Açıkça belirtiliyor | A | Korunmalı. |
| 7 | Cem'le ilk kez şahsen karşılaşması | JSON'da hem “doğrudan temas kurup kurmadığı henüz belirlenmemiştir” deniyor hem de ilerleyen bölümde şahsen karşılaşacağı kesin ifade ediliyor | Cem'in onu ilk kez göreceği ve aralarında önceden kişisel ilişki bulunmadığı açık | C | JSON içindeki belirsizlik cümlesi A2'de düzeltilmeli. Karar: şahsen karşılaşma mevcut proje kararıyla sabit; önceden tanışıklık yok. |
| 8 | Kendini “Zaman Şövalyesi” diye tanıtması | Kesinleştirilmiş | “Ben bir zaman şövalyesiyim” ifadesiyle belirtilmiş | A | Korunmalı. Gerçek adı ve unvanın kökeni D. |
| 9 | İnsan kökenli olması | Açıkça belirtilmiyor | “İnsan kökenli” deniyor | B | Önceki açık proje sahibi kararıyla doğrulanamıyor. Kullanıcı kararı gerekli: kanon, incelemede veya reddedildi. |
| 10 | DNA kodlamasıyla biyolojik yaşlanmayı durdurması | Belirtilmiyor | Kendi DNA'sı üzerinde kodlama yaparak biyolojik yaşlanmayı durdurduğu yazıyor | B | Önceki açık proje sahibi kararıyla doğrulanamıyor. Kullanıcı kararı gerekli. Doğaüstü ölümsüzlük olmadığı da aynı kararın kapsamına bağlı. |
| 11 | Doğaüstü ölümsüz olmaması | Belirtilmiyor | Yaşlanmayı durdurduğu, ancak doğaüstü anlamda ölümsüz olmadığı yazıyor | B | 9–10. maddelerle birlikte ele alınmalı; kullanıcı kararı gerekli. |
| 12 | Yolculukların yeni paralel zaman dalı oluşturması | Alternatif evrenler oluşturduğu genel olarak belirtiliyor; her yolculuğun yeni dal oluşturması ayrıntısı yok | Her önemli müdahale veya yolculuğun yeni dal oluşturduğu açık | A | Önceki proje sahibi kararıyla doğrulanmış: yolculuk/müdahale yeni paralel dal oluşturur. JSON'a aktarılması önerilir. |
| 13 | Her dalın kendi tarihsel akışına devam etmesi | Açık değil | Açıkça belirtiliyor | A | Önceki proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 14 | Yeni dalda kendi soyundan bir atasını öldürmesi | Bulunmuyor | Yeni dalda kendi soy zincirindeki bir atasını öldürerek o dalda kendi versiyonunun doğmasını önlediği anlatılıyor | A | Önceki açık proje sahibi kararıyla doğrulanmış. JSON'a aktarılması önerilir. |
| 15 | Öldürülen kişinin ana zaman çizgisindeki atası olmaması | Bulunmuyor | Öldürülen kişinin yalnızca yeni paralel dalın soy versiyonu olduğu ve ana zaman çizgisindeki varlığını etkilemediği belirtiliyor | A | Önceki kararın önemli nedensel koşulu; JSON'a aktarılması önerilir. |
| 16 | “Bir zaman dalında ikinci bir Zaman Şövalyesi doğmamalıdır” ilkesi | Bulunmuyor | Açıkça temel ilke olarak yazılı | A | Önceki açık proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 17 | Zamandan bağımsız merkez | Bulunmuyor | Zaman akışından ve paralel dallardan bağımsız merkez inşa ettiği anlatılıyor | A | Önceki açık proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 18 | Merkezin “kuantum evreninin ötesinde” bulunması | Bulunmuyor | Bu ifade kullanılıyor | A | Önceki proje kararıyla merkezin zamandan bağımsızlığı doğrulanmış. “Kuantum evreninin ötesi” ifadesi de önceki tasarımın parçası; korunabilir, ancak teknik anlamı henüz açıklanmadı (D). |
| 19 | Merkezde dalları gösteren dev kuantum bilgisayarı | Bulunmuyor | Paralel zaman dallarını görsel olarak izleyen gelişmiş kuantum bilgisayarı var | A | Önceki açık proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 20 | Dalların ağ/dallanma şeklinde görselleştirilmesi | Bulunmuyor | Bilgisayar dalları ağ veya dallanan yapı hâlinde gösteriyor | A | Önceki proje tasarım kararıyla uyumlu; JSON'a aktarılması önerilir. |
| 21 | Dal sayısı, bağlantılar, yeni dallanmalar ve belirli gerçekliklerin izlenmesi | Bulunmuyor | Bu gözlem başlıkları tek tek listelenmiş | A | Önceki açık proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 22 | Her dala benzersiz kod atanması | Bulunmuyor | Her dalın benzersiz kodla takip edildiği yazıyor | A | Önceki açık proje sahibi kararıyla doğrulanmış; JSON'a aktarılması önerilir. |
| 23 | Dal kodlarının kesin biçimi | Bulunmuyor | Kesin teknik biçimin henüz belirlenmediği yazıyor | D | Bilinmeyen olarak korunmalı; kod formatı uydurulmamalı. |
| 24 | Kuantum bilgisayarının gözlem sınırları | Bulunmuyor | Gözlem sınırları bilinmeyenler arasında | D | Açık soru olarak kalmalı; her şeyi bildiği/izlediği varsayılmamalı. |
| 25 | Zaman makinesinin çalışma ilkesi | Henüz belirlenmemiş deniyor | Bilinmeyenler listesinde | D | Açık soru olarak kalmalı. |
| 26 | Zamandan bağımsız merkezin nasıl inşa edildiği | Belirtilmiyor | Bilinmeyenler listesinde | D | Açık soru olarak kalmalı. |
| 27 | Zaman yolculuğunun/alternatif dal oluşturmanın bedelleri | JSON'da belirlenmemiş | Markdown'da açık teknik bedel tanımlanmıyor | D | Henüz belirlenmemiş olarak kalmalı. |
| 28 | Cem'in zaman çizgisinin neden özel olduğu | Cem senaryosuna duyduğu merak açıklanıyor | Asıl ilgi nedeninin bilinmediği yazıyor | D | Genel motivasyon mevcut; daha derin neden açık soru olarak kalmalı. |
| 29 | Karakterin en büyük gücünün mutlak zaman hâkimiyeti değil, geniş gerçeklik bilgisi olması | Bulunmuyor | Karakterin temel çelişkisi bölümünde yorum olarak yazıyor | B | Önceki açık proje sahibi kararıyla doğrulanamıyor. Kanon kararı olarak değil, yazar yorumu/önerisi olarak tutulmalı; kullanıcı isterse ayrıca onaylayabilir. |
| 30 | Kuantum bilgisayarının insanların bütün kararlarını mutlak kontrol etmemesi | Bulunmuyor | Bilgisayarın böyle bir kontrol sağlamadığı yorumu var | B | Önceki açık karar olarak doğrulanamıyor. Bilimsel/öyküsel sınır kararı olarak kullanıcı onayı gerekli. |
| 31 | “Kendi öznel zamanına göre” yüzyıllardır yaşaması | Genel asırlardır yaşama var | Öznel zaman ifadesi var | B | Yaşadığı süre ile kendi deneyimlediği süre arasındaki ayrım henüz onaylı kural olarak doğrulanamıyor; kullanıcı kararı veya belirsiz bırakma. |
| 32 | Gerçek ad, doğum tarihi, görünüş | Belirlenmemiş | Gerçek ad ve bazı ayrıntılar bilinmiyor; doğum tarihi/görünüş tanımlanmıyor | D | Bilinmeyen olarak kalmalı. |
| 33 | Cem'le ilk karşılaşmanın kesin tarih ve yeri | JSON notes henüz belirlenmediğini söylüyor | Markdown kesin tarih ve yer vermiyor | D | Önceki çalışma taslağında 1467–1469 ve Cem'in 8–10 yaşları seçenek olarak tartışılmıştı; kesin kanon kararı değildir. |
| 34 | Zaman Şövalyesi'nin Cem'in yaşadığı dala geldikten sonra atasını öldürmesi ve ardından Cem'le karşılaşması | JSON'da bu sıralama yok | Markdown'da açıkça bu sırada anlatılıyor | A | Önceki proje sahibi kararıyla doğrulanmış; olay sırası JSON'a aktarılabilir. |
| 35 | Atanın öldürülmesinin nedeni | JSON'da yok | Yeni dalda ikinci Zaman Şövalyesi'nin doğmasını engellemek | A | 14–16. maddelerle birlikte aktarılmalı. |
| 36 | Atanın kimliği, dönemi, öldürülme yöntemi ve sahnenin sonuçları | Belirtilmiyor | Belirtilmiyor | D | Bilinmeyen olarak kalmalı; yeni ayrıntı uydurulmamalı. |

## 4. Önceki açık proje sahibi kararlarıyla doğrulanan Markdown ayrıntıları

Aşağıdaki içerikler yalnızca Markdown'da yer aldıkları için değil, önceki proje kararlarıyla da doğrulandıkları için A sınıfında değerlendirilmiştir:

1. Zaman Şövalyesi'nin zaman yolculuğu/müdahalesi yeni bir paralel zaman dalı oluşturur.
2. Her dal kendi tarihsel gelişimini sürdürür.
3. Zaman Şövalyesi yeni bir dala girdiğinde o dalda kendi soyundan gelen bir atasını öldürerek o dalda kendi gelecekteki versiyonunun doğmasını engeller.
4. Öldürülen ata ana zaman çizgisindeki atası değildir; bu nedenle Zaman Şövalyesi'nin mevcut varlığı silinmez.
5. “Bir zaman dalında ikinci bir Zaman Şövalyesi doğmamalıdır” ilkesi.
6. Zamandan bağımsız, zaman akışının dışında bir merkez.
7. Merkezde paralel zaman dallarını görsel olarak izleyen dev kuantum bilgisayarı.
8. Bilgisayarın dalları ve bağlantıları takip etmesi; her dala benzersiz kod verilmesi.
9. Cem'i önceden yalnızca tarihsel kişilik olarak tanıması, Cem'in ise onu ilk kez görmesi.
10. Cem'le karşılaşmadan önce o dalda kendi soy atasını öldürmesi ve ardından Cem'in karşısına çıkması.

Bu maddelerin karar günlüğüne aktarılması teknik olarak uygun görünmektedir. Ancak geriye dönük karar kaydı hazırlanırken sohbet geçmişindeki gerçek karar tarihi ve mümkün olan en açık kaynak referansı kullanılmalı; tarih tahmin edilmemelidir. Bu nedenle karar günlüğü A2/A3 uygulamasında ayrıca ele alınacaktır.

## 5. Kullanıcı kararı gerektiren konular

### 5.1 İnsan kökeni ve DNA ile yaşlanmanın durdurulması

Markdown belgesi Zaman Şövalyesi'nin insan kökenli olduğunu ve kendi DNA'sı üzerinde yaptığı kodlama sayesinde biyolojik yaşlanmasını durdurduğunu söylüyor. Bu iki ayrıntı yapılandırılmış JSON kaydında yoktur ve önceki açık proje sahibi kararıyla doğrulanamamaktadır.

Bu nedenle bu unsurlar A2'de otomatik olarak JSON'a taşınmamalıdır. Kullanıcı bunların kanon olup olmadığını belirlemelidir.

### 5.2 Karakterin gerçeklik bilgisi ve mutlak hâkimiyet sınırı

Markdown'da Zaman Şövalyesi'nin gücünün mutlak zaman kontrolü değil, geniş gerçeklik bilgisi olduğu yorumu bulunuyor. Bu, karakterin güç ölçeğini ve anlatıdaki sınırlarını etkileyen önemli bir yazarlık kararıdır. Önceki açık proje sahibi kararıyla doğrulanamadığından kullanıcı onayı olmadan kanonlaştırılmamalıdır.

### 5.3 Öznel zaman

“Yüzyıllardır yaşamak” ile “kendi öznel zamanına göre yüzyıllardır yaşamak” aynı iddia değildir. İkinci ifade, zaman yolculuklarının karakterin kişisel yaşantı süresine etkisi hakkında ek bir kural içerir. Bu fark henüz kesinleştirilmemiştir.

## 6. JSON kaydındaki ayrıca düzeltilmesi gereken iç tutarsızlık

JSON açıklamasında şu iki ifade birbiriyle uyuşmamaktadır:

- Cem Sultan ile doğrudan temas kurup kurmadığının henüz belirlenmediği yazılıyor.
- Aynı açıklamanın devamında gelecekten geçmişe gelerek Cem Sultan ile şahsen karşılaşacağı kesin biçimde belirtiliyor.

Proje sahibinin önceki açık kararı, şahsen karşılaşmanın gerçekleşeceği ve Cem'in onu ilk kez göreceği yönündedir. Dolayısıyla A2'de belirsizlik cümlesi kaldırılmalı; kesinleşmiş karşılaşma bilgisi korunmalıdır.

## 7. A2 için önerilen uygulama sözleşmesi

A2'ye geçildiğinde aşağıdaki işlemler önerilir:

1. `character-0001` kimliği korunur; yeni karakter kimliği üretilmez.
2. `character-0001.json` tek esas yapılandırılmış kayıt olur.
3. Önceki açık proje sahibi kararlarıyla doğrulanan A sınıfı içerikler, kaynak/karar iziyle JSON'a aktarılır.
4. İnsan kökeni, DNA ile yaşlanmayı durdurma ve gerçeklik bilgisi/karakter gücü yorumu kullanıcı kararı olmadan taşınmaz.
5. Belirsiz teknik konular açıkça belirsiz bırakılır.
6. `zaman_sovalyesi.md` bağımsız ikinci kanon kaydı olarak bırakılmaz. Nihai rolü, kullanıcı onayı ve içerik uzlaştırması sonrasında belirlenir.
7. `related_entities` ile `relationships` alanları A2'de aceleyle birleştirilmez; A4'te depo genelindeki kullanım taraması yapılır.
8. Kanon indeksi, tek esas kayıt mimarisine göre ancak A2 değişiklikleri onaylandıktan sonra güncellenir.

## 8. A1 çıkış kontrolü

- [x] Güncel JSON ve Markdown dosyaları karşılaştırıldı.
- [x] Kayıt kimliği ve kanon indeksi uyuşmazlığı belirlendi.
- [x] İçerik iddiaları madde madde sınıflandırıldı.
- [x] Önceki açık proje sahibi kararları, yalnızca Markdown'da bulunan ve doğrulanmamış ayrıntılardan ayrıldı.
- [x] JSON içindeki doğrudan temas tutarsızlığı kayda alındı.
- [x] Kullanıcı kararı gerektiren ayrıntılar ayrıştırıldı.
- [x] A2 için teknik uygulama sözleşmesi hazırlandı.
- [x] Bu rapor hazırlanırken hiçbir kanon veya karakter kaydı değiştirilmedi.

**A1 durumu:** Tamamlandı — içerik envanteri hazır.  
**Kanon etkisi:** Yok.  
**Sonraki aşama:** A2 — Zaman Şövalyesi kaydının birleştirilmesi; yalnızca kullanıcı tarafından onaylanan içeriklerle.
