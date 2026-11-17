# Kayıt Standartları

- Her varlık için benzersiz, değişmez bir id kullanılır: ör. char-0001, place-0001.
- Dosya adları küçük harfli ASCII, kelimeler tire ile ayrılmış biçimde olmalıdır.
- JSON dosyaları UTF-8 ve iki boşluk girintili kaydedilir.
- Tarihi bilinmeyen olaylara uydurma tarih verilmez.
- Kesin tarih, yaklaşık tarih ve tartışmalı tarih birbirinden ayrılır.
- İlişkiler mümkün olduğunda kayıt id değerleriyle kurulur.
- Her kayıtta status, created_at, updated_at ve sources alanları bulunur.
- Tarihler ISO 8601 biçiminde yazılır. Tarih bilinmiyorsa null kullanılır.
- Bir kaydın anlamı değişiyorsa id korunur; yeni bir varlıksa yeni id verilir.
- Silme yerine arsiv durumu tercih edilir.
- Kaynak yoksa sources: [] kullanılır; kaynak varmış gibi gösterilmez.

## İlişki alanlarının kullanımı

- `related_entities`, bir kaydın bağlantılı olduğu varlıkların kimliklerini kısa ve yalın bir liste olarak tutar. İlişkinin yönü veya anlamı bu alanda açıklanmaz.
- `relationships`, ilişkinin anlamını ve durumunu açıklayan yapılandırılmış ilişkiler için kullanılır. Her öğe en az `entity_id`, `relation` ve `status` alanlarını taşır.
- Aynı hedef kimliğin iki alanda da bulunması tek başına veri hatası değildir: `related_entities` genel bağlantı dizini, `relationships` ise anlamlı ilişki tanımıdır. Ancak iki alanın birbiriyle çelişen hedef veya ilişki bilgisi üretmesine izin verilmez.
- Bir kayıt türünde bu alanların hangilerinin zorunlu olduğu, JSON Schema ve kayıt şablonlarında ayrıca tanımlanmalıdır. Şema tanımı bulunmayan alanların kullanımı Aşama A4 kapsamındaki şema ve uyumluluk denetiminde ele alınır.
