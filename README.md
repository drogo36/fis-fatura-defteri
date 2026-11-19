# 🧾 Fiş & Fatura Defteri

Fiş ve faturalarını telefonunda takip etmeni sağlayan ücretsiz bir uygulama. Üyelik gerektirmez, internetsiz de çalışır.

**Uygulamayı aç:** https://drogo36.github.io/fis-fatura-defteri/

## Neler yapar?

- **📷 Fotoğrafla otomatik okuma:** Fişin fotoğrafını çekersin; işyeri, tarih, tutar, KDV, belge no, belge türü ve kategori kendiliğinden dolar. Okuma telefonunun içinde yapılır, fişlerin hiçbir sunucuya gönderilmez.
- **🔔 Harcama bildirimleri:**
  - Aylık bütçenin %80'ine gelince ve bütçeyi aşınca
  - Geçen ayın aynı dönemine göre %25'ten fazla harcayınca
  - Geçen ayın toplam harcamasını geçince
  - Bir kategoride (market, akaryakıt…) son 3 ay ortalamasının 1,5 katını geçince
  - Bir ürünün garantisinin bitmesine 30 gün kala
- **💰 Vergi indirimi hesabı:** Eğitim ve sağlık harcamalarını ayırır, belgesi uygun olmayanlar için "FATURA İSTE" uyarısı verir, yıllık gelirine göre tahmini vergi avantajını hesaplar.
- **📊 Raporlar:** Aylık ve kategori bazlı harcama grafikleri, ödenen toplam KDV.
- **📤 Dışa aktarma:** Excel'de açılan CSV dosyası (mali müşavirine göndermek için).
- **💾 Yedekleme:** Fotoğraflar dahil tüm kayıtları tek dosyada yedekle, yeni telefona geri yükle.

## Telefona kurulum

### iPhone (Safari ile)
1. Yukarıdaki bağlantıyı **Safari**'de aç.
2. Alttaki **Paylaş** simgesine (kutudan yukarı çıkan ok) dokun.
3. **Ana Ekrana Ekle**'yi seç, sonra **Ekle**'ye bas.
4. Uygulamayı artık ana ekrandaki simgeden aç.
5. Sağ üstteki ⚙️ simgesine dokun ve **Bildirimlere izin ver**'e bas.

> iPhone'da bildirimler sadece uygulama ana ekrandan açıldığında çalışır (iOS 16.4 ve üstü).

### Android (Chrome ile)
1. Yukarıdaki bağlantıyı **Chrome**'da aç.
2. Sağ üstteki **⋮** menüsüne dokun.
3. **Uygulamayı yükle** ya da **Ana ekrana ekle**'yi seç.
4. Uygulamayı açıp ⚙️ simgesinden **Bildirimlere izin ver**'e bas.

## Bilmen gerekenler

- **Kayıtların sadece senin telefonunda durur.** Telefonu değiştirirsen ya da uygulamayı silersen kaybolmaması için ⚙️ → **Yedek al** ile ayda bir yedek alıp Drive'a veya WhatsApp'ta kendine gönder.
- **Fiş okuma motoru** ilk kullanımda bir kez indirilir (yaklaşık 15 MB). Sonrasında internetsiz de çalışır.
- **Bildirimler** fiş eklediğinde ve uygulamayı açtığında kontrol edilir. Her uyarı ayda bir kez gelir.
- Vergi bölümündeki bilgiler genel bilgilendirmedir, mali müşavir görüşü yerine geçmez.

## Teknik

Tek sayfalık bir web uygulaması (PWA). Sunucu, hesap veya ücretli servis yoktur.

| Dosya | Görevi |
|---|---|
| `index.html` | Uygulamanın tamamı |
| `sw.js` | İnternetsiz çalışma ve bildirimler |
| `manifest.webmanifest` | Ana ekrana kurulum bilgileri |
| `icons/` | Uygulama simgeleri |

Veriler tarayıcının IndexedDB deposunda tutulur. Fiş okuma [Tesseract.js](https://github.com/naptha/tesseract.js) (Türkçe dil paketi) ile cihaz üzerinde yapılır.
