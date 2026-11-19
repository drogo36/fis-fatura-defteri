# 🧾 Fiş & Fatura Defteri

Fiş ve faturalarını telefonunda takip etmeni sağlayan ücretsiz bir uygulama. Üyelik gerektirmez, kayıtların sadece senin telefonunda durur.

**Uygulamayı aç:** https://drogo36.github.io/fis-fatura-defteri/

## Neler yapar?

- 📷 **Fotoğrafla otomatik okuma:** Fişin fotoğrafını çekersin. İşyeri, tarih, tutar, KDV, belge no ve kategori otomatik dolar. Okuma telefonun içinde yapılır, fiş hiçbir yere gönderilmez.
- 🔔 **Harcama bildirimleri:** Aylık bütçeni aşınca, geçen aya göre çok harcayınca ya da bir kategoride (market, akaryakıt…) harcaman artınca bildirim gelir.
- 💰 **Vergi indirimi:** Eğitim ve sağlık harcamalarını ayırır. Hangi belgenin indirime uygun olduğunu gösterir ve tahmini vergi avantajını hesaplar.
- 📊 **Raporlar:** Aylık ve kategori bazlı harcama, ödenen KDV, garantisi bitecek ürünler.
- 📤 **Dışa aktarma:** Excel'de açılan CSV dosyası ve fotoğraflı tam yedek.
- 📶 **İnternetsiz çalışır** (sadece ilk fiş okumada okuma motoru bir kez indirilir).

## Telefona kurulum

**iPhone (Safari):** Linki aç → alttaki **Paylaş** simgesi → **Ana Ekrana Ekle** → **Ekle**. Bildirimler için uygulamayı ana ekrandaki simgeden açman gerekir (iOS 16.4 ve üzeri).

**Android (Chrome):** Linki aç → sağ üstteki **⋮** → **Uygulamayı yükle**.

Sonra uygulamada **⚙️ Ayarlar → Bildirimlere izin ver**.

## Önemli

- Kayıtların sadece bu telefonda saklanır. Telefon değiştirmeden önce **⚙️ Ayarlar → Yedek al** ile yedeğini al.
- Vergi bilgileri genel bilgilendirmedir, mali müşavir görüşü yerine geçmez.

## Teknik

Tek sayfalık PWA (HTML + JavaScript). Veriler IndexedDB'de tutulur, fiş okuma [Tesseract.js](https://github.com/naptha/tesseract.js) ile tarayıcıda yapılır. Sunucu yoktur.
