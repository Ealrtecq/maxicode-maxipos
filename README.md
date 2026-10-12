<div align="center">

<img src="assets/img/banner-v2.svg" alt="MaxiPOS v3: Restoran ve kafeler için adisyon ve POS sistemi" width="100%"/>

<br/>

![Durum](https://img.shields.io/badge/Durum-Aktif-success?style=for-the-badge)
![Sürüm](https://img.shields.io/badge/S%C3%BCr%C3%BCm-v3-5fc4cc?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Web%20%C2%B7%20PWA-blue?style=for-the-badge)
![Çalışma](https://img.shields.io/badge/%C4%B0nternetsiz-%C3%87al%C4%B1%C5%9F%C4%B1r-orange?style=for-the-badge)
![Lisans](https://img.shields.io/badge/Lisans-Propriyeter-red?style=for-the-badge)

**Masa, mutfak, kasa ve raporlama tek sistemde. Dükkânınızdaki mini PC üzerinde, internet olmadan çalışır.**

[Özellikler](#-özellikler) · [Nasıl çalışır](#-nasıl-çalışır) · [Ekranlar](#-ekran-görüntüleri) · [Teknoloji](#-teknoloji) · [Kurulum](#-kurulum) · [İletişim](#-demo-ve-iletişim)

</div>

> **Not:** Bu depo **MaxiPOS** ürününün tanıtım sayfasıdır. Kaynak kodlar ticari ve güvenlik nedenleriyle kapalı tutulur. Demo, fiyat ve özel geliştirme için [iletişim](#-demo-ve-iletişim) bölümüne bakın.

---

## 🍽️ MaxiPOS nedir?

MaxiPOS, restoran, kafe ve bar gibi işletmelerde siparişten ödemeye, mutfak takibinden gün sonu raporuna kadar bütün işi tek çatı altında toplayan bir **adisyon (POS) otomasyonudur**.

Garson, aşçı, kasiyer ve yönetici aynı sistemi kendi rolüne göre görür ve hepsi anlık olarak senkron çalışır. Veriler dükkânınızdaki cihazda durur; internet kesilse bile satış devam eder.

<div align="center">
<img src="assets/img/siparis-yolculugu.svg" alt="Bir siparişin yolculuğu" width="100%"/>
</div>

---

## ✨ Özellikler

<div align="center">
<img src="assets/img/ozellikler.svg" alt="MaxiPOS özellikleri" width="100%"/>
</div>

### 📱 Garson
- Telefon ve tabletle tam uyumlu mobil arayüz
- Masa ve kategoriye göre hızlı ürün seçimi, porsiyon ve ekstra seçenekleri
- Siparişe özel not ("az pişmiş", "buzsuz")
- Mutfaktan hazır çıkan siparişi görüp teslim edildi işaretleme
- Hesap servis ücretini kendisi ekleyebilir

### 👨‍🍳 Mutfak ve bar
- Yeni sipariş sesli uyarıyla ekrana düşer
- Hazırlanıyor / Hazır durumu, geciken siparişte renkli uyarı
- Mutfak fişi (M001, M002 numaralı)
- Mutfak raporu

### 💻 Kasa ve ödeme
- Masa planı, canlı adisyon tutarları
- Nakit, kredi kartı, yemek çeki, cari (veresiye) ve ikram
- Parçalı ödeme, kişi başı hesap bölme, tutar girerek ödeme
- Masa taşıma, birleştirme ve ürün aktarma
- İndirim, ürün iptali ve ikram (sebep zorunlu, hepsi kayıt altında)
- Termal yazıcıdan tek tıkla hesap fişi

### 💰 Tip box (bahşiş)
Müşteri hesaptan fazla para verirse sistem sorar: para üstü mü verilecek, yoksa tip box'a mı atılacak? Bahşiş ciroya girmez, garson bazında ayrı raporlanır ve gün sonunda Z fişinde ayrı satır olarak çıkar.

<div align="center">
<img src="assets/img/odeme-akisi.svg" alt="Ödeme akışı" width="100%"/>
</div>

### 📦 Stok, maliyet ve cari
- Malzeme, reçete, alış / sayım / fire hareketleri
- Ürün maliyeti ve kâr marjı
- Tedarikçi, personel ve müşteri cari hesapları, ekstre ve tahsilat
- Kayıp / kaçak alarmları
- Kasadan çıkış giderleri (pazar alımı, fatura, avans)

### 📊 Yönetim ve raporlar
- Ciro, kâr, KDV, ürün ve kategori raporları
- Saatlik gelir trendi grafiği
- Garson ve personel performansı, mesai takibi
- İptal, mutfak, cari ve tip box raporları
- **Otomatik gün sonu (Z raporu)**, en geç gece yarısı

<div align="center">
<img src="assets/img/gun-sonu.svg" alt="Otomatik gün sonu akışı" width="100%"/>
</div>

### 🔐 Güvenlik
- Rol bazlı yetki: garson kasayı, kasiyer ayarları göremez
- Her önemli işlem (fiyat değişikliği, silme, taşıma, giriş) işlem kaydına yazılır
- Yerel HTTPS, parola ve PIN ile giriş
- Zamanlı otomatik yedek, ayarlardan indirilebilir yedekler

---

## 🧭 Nasıl çalışır?

<div align="center">
<img src="assets/img/mimari-v2.svg" alt="MaxiPOS mimarisi" width="100%"/>
</div>

Kasa, garson ve mutfak ekranları aynı yerel ağdaki tarayıcılardan açılır. Hepsi dükkândaki tek MaxiPOS sunucusuna bağlanır; sunucu verileri MariaDB'ye yazar, fişleri USB termal yazıcıya gönderir ve yedekleri alır. Bağlantı koparsa ekranlarda **"Sunucu ile bağlantı koptu"** uyarısı çıkar.

---

## 📸 Ekran görüntüleri

### 🪑 Satış: masa planı
Boş ve dolu masalar bölgelere göre listelenir; dolu masada geçen süre ve güncel hesap görünür.
<div align="center">
  <img src="assets/screenshots/satis-masalar.jpg" width="900" alt="Satış ekranı: masa planı"/>
</div>

### 🧾 Masa adisyonu
Masaya tıklayınca açılan adisyonda fotoğraflı menü, hesap, tutar girerek ve kişi başı ödeme, nakit / kart / yemek fişi / cari butonları tek ekranda.
<div align="center">
  <img src="assets/screenshots/masa-adisyon.jpg" width="900" alt="Masa adisyon ekranı"/>
</div>

### 🍔 Menü yönetimi
Kategori, ürün, fiyat ve fotoğraf yönetimi Ayarlar içinde.
<div align="center">
  <img src="assets/screenshots/menu-yonetimi.jpg" width="900" alt="Menü yönetimi"/>
</div>

### 🗺️ Masa planı yönetimi
Masalar bölgelere (bahçe, iç mekan, VIP) göre gruplanır; ekleme, düzenleme ve ikon değiştirme tek ekranda.
<div align="center">
  <img src="assets/screenshots/masa-plani-ayarlar.jpg" width="900" alt="Masa planı yönetimi"/>
</div>

### 📦 Stok
Malzemeler satışta reçeteye göre otomatik düşer; kritik seviye uyarısı ve stok değeri anında görünür.
<div align="center">
  <img src="assets/screenshots/stok.jpg" width="900" alt="Stok ekranı"/>
</div>

### 🔐 Roller ve yetkiler
Her role hangi ekranları göreceği ve hangi işlemleri yapabileceği tek tek verilir.
<div align="center">
  <img src="assets/screenshots/roller-yetkiler.jpg" width="900" alt="Roller ve yetkiler"/>
</div>

### 🌙 Gün sonu ayarları
Otomatik ya da manuel Z raporu, gün dönümü saati.
<div align="center">
  <img src="assets/screenshots/gun-sonu-ayarlari.jpg" width="900" alt="Gün sonu ayarları"/>
</div>

---

## 🔧 Teknoloji

| Katman | Teknoloji |
| --- | --- |
| Sunucu | Go, Fiber, GORM |
| Arayüz | React, Vite, Bootstrap, PWA (ana ekrana eklenebilir) |
| Veritabanı | MariaDB (yerel) |
| Anlık iletişim | WebSocket |
| Yazıcı | USB termal yazıcı (fiş, mutfak fişi, Z raporu) |
| Donanım | Mini PC (amd64, Debian/Ubuntu) |
| Tema | Açık ve koyu tema |

---

## 🚀 Kurulum

Kurulum dükkânda tek komutla yapılır, kurulumdan sonra sistem internetsiz çalışır.

<div align="center">
<img src="assets/img/kurulum.svg" alt="Kurulum 4 adım" width="100%"/>
</div>

1. Cihazı internete bağlayın ve kurulum USB'sini takın.
2. `sudo bash kur.sh` komutunu çalıştırın.
3. Telefon ve tabletlere yerel sertifikayı bir kez yükleyin.
4. `https://maxipos.local` adresini açıp ana ekrana ekleyin.

Kurulum betiği veritabanını, servisi, otomatik yedeği ve yazıcı iznini kendisi hazırlar; sonraki çalıştırmalarda veriyi koruyarak yalnızca uygulamayı günceller ve açılmazsa önceki sürüme döner.

---

## 📞 Demo ve iletişim

Canlı demo, fiyatlandırma veya işletmenize özel geliştirme için bize ulaşın:

- 📧 **E-posta:** info@maxicode.com.tr
- 🌐 **Web:** https://maxicode.com.tr · https://adisyon.maxicode.com.tr

---

<div align="center">
  <sub>© 2026 MaxiCode · Tüm hakları saklıdır.</sub>
</div>
