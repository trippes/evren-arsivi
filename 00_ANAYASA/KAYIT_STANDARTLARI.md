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
