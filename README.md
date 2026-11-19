# 🧾 Fiş & Fatura Defteri

Fiş ve faturalarını telefonunda takip etmeni sağlayan ücretsiz bir uygulama. Üyelik gerektirmez, internetsiz de çalışır.

**Uygulamayı aç:** https://drogo36.github.io/fis-fatura-defteri/

## Neler yapar?

### 👛 Bütçe yönetimi
- **Gelir & gider:** Maaşını ve ek gelirlerini ekle; ay içinde ne kadar harcadığını ve ne kadar kaldığını, tasarruf oranını gör.
- **Ay sonu tahmini:** "Bu gidişle ay sonunda yaklaşık ne kadar harcamış olacaksın" hesabı.
- **Kategori bütçeleri:** Market, akaryakıt, yeme-içme… her kategori için aylık sınır. %80'de ve aşınca uyarı.
- **Düzenli ödemeler:** Kira, faturalar, abonelikler, kredi taksitleri, maaş. Günü yaklaşınca hatırlatma, "Öde" ile tek dokunuşla gidere işleme.
- **Taksitler:** Kredi kartıyla taksitli alışverişler aylara bölünür; bu ay ve gelecek ay ne kadar taksit ödeyeceğini gösterir.
- **Tasarruf hedefleri:** Ev, araba, tatil… Ne kadar biriktirdiğin ve hedef tarihe ulaşmak için ayda ne kadar ayırman gerektiği.
- **Borç & alacak:** Kime borç verdin, kimden aldın; vadesi gelince hatırlatma.
- **Ödeme yöntemi:** Kredi kartı, banka kartı, nakit, havale.

### 🧾 Fiş ve fatura
- **🤖 Yapay zeka ile fiş okuma (Gemini):** Fişin fotoğrafını çekersin; işyeri, tarih, tutar, KDV, belge no, belge türü ve kategori kendiliğinden dolar. ⚙️ Ayarlar'a ücretsiz Gemini anahtarını (AQ. ile başlar) bir kez yapıştırman yeterli ([anahtar al](https://aistudio.google.com/apikey)). Anahtar sadece telefonunda saklanır ve bir daha istenmez; Google anahtarı reddederse (süresi dolmuş, eksik kopyalanmış vb.) uygulama nedenini Türkçe açıklar.
- **📷 İnternetsiz yedek okuyucu:** Anahtar yoksa ya da internet yoksa fiş, telefonun içindeki okuyucuyla okunur.
- **💰 Vergi indirimi hesabı:** Eğitim ve sağlık harcamalarını ayırır, belgesi uygun olmayanlar için "FATURA İSTE" uyarısı verir, tahmini vergi avantajını hesaplar.
- **🛡️ Garanti takibi:** Garantisi bitmek üzere olan ürünler.

### 🔔 Bildirimler
Bütçe %80 / aşım, gelirden fazla harcama, geçen aya göre artış, kategori artışı, yaklaşan ve geciken ödemeler, borç vadesi, garanti bitişi.

### 📊 Raporlar
Gelir-gider grafiği (12 ay), aylık harcama, kategoriler, en çok harcanan yerler, ödeme yöntemleri, günlük ortalama, sabit giderler, ödenen KDV. Excel'de açılan CSV dışa aktarma.

### 🔒 Güvenlik ve yedek
- 4 haneli uygulama kilidi.
- **Otomatik yedek:** Her gün kendiliğinden, son 10 gün saklanır; ayrıca her silmeden önce. Tek dokunuşla o güne dönülür.
- **Haftalık hatırlatma:** Telefon dışına (iCloud Drive / Google Drive) tek dokunuşla yedek.
- Fotoğraflar dahil tüm verilerin tek dosyada yedeklenip geri yüklenmesi.

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
