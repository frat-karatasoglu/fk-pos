# FK POS

**Küçük işletmeler için çevrimdışı çalışmayı esas alan satış noktası (POS) yazılımı.**
**Offline-first point-of-sale software for small businesses.**

🇹🇷 [Türkçe](#türkçe) · 🇬🇧 [English](#english)

<p align="center">
  <a href="screenshots/03-yonetim-paneli.png"><img src="screenshots/03-yonetim-paneli.png" alt="FK POS yönetim paneli · FK POS dashboard" width="100%"></a>
</p>

---

## Türkçe

8 sektöre özel sürüm · 5 aktif işletme · Türkiye pazarı

→ [fkposyazilim.com](https://fkposyazilim.com)

> Bu bir vitrin (showcase) deposudur. FK POS ticari bir üründür, bu yüzden kaynak kodu açık değildir — bu sayfa ürünün mimarisini ve arkasındaki mühendislik kararlarını anlatır.

### Sorun

Bir dükkân, internet kesildi diye satış yapmayı bırakamaz. Modern POS yazılımlarının çoğu kesintisiz bir bağlantı varsayar ve bağlantı olmadığında kötü çalışır. FK POS bunun tersine kurgulanmıştır: gerçeğin kaynağı kasadır, bulut ise isteğe bağlı bir gözlemcidir.

### Mimari

**Önce çevrimdışı (offline-first).** Satış, kasa işlemleri, stok ve faturalama tamamen yerel makinede çalışır. Ödeme akışının hiçbir adımı için internet bağlantısı gerekmez.

**Eklenti olarak bulut senkronizasyonu.** İsteğe bağlı bir Supabase modülü, kasanın anlık durumunu her 2 dakikada bir ve bağlantı geri geldiğinde hemen gönderir. Böylece işletme sahibi dükkânı uzaktan izleyebilir, kasa ise çevrimdışı çalışmaya devam eder.

**Donanım Rust'ta.** Barkod okuyucular, elektronik teraziler, termal fiş yazıcıları ve ikinci müşteri ekranları, Rust ile yazılmış Tauri komutlarıyla sürülür; cihaz girdi/çıktısı JavaScript katmanının dışında tutulur.

**Tek dosya yedekler.** Özel bir .POS biçimi, tüm dükkân durumunu tek bir dosyada toplar — işletme sahibinin USB belleğe kopyalayabileceği kadar basit.

### Modüller

Satış · Stok · Cari hesaplar · Faturalama · Toplu fiyat güncelleme · Raporlama

### Teknoloji

React · TypeScript · Tauri · Rust · Supabase (PostgreSQL) · Windows

### Ekran görüntüleri

Görüntüler uydurma demo verisiyle alınmıştır. Büyütmek için üzerine tıklayın.

**Masaüstü uygulaması**

<table>
  <tr>
    <td align="center" width="50%"><a href="screenshots/01-giris-secimi.png"><img src="screenshots/01-giris-secimi.png" alt="Giriş"></a><br><sub>Giriş</sub></td>
    <td align="center" width="50%"><a href="screenshots/02-pin-girisi.png"><img src="screenshots/02-pin-girisi.png" alt="PIN ile giriş"></a><br><sub>PIN ile giriş</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/04-satis-ekrani.png"><img src="screenshots/04-satis-ekrani.png" alt="Satış ekranı"></a><br><sub>Satış ekranı</sub></td>
    <td align="center"><a href="screenshots/05-urun-yonetimi.png"><img src="screenshots/05-urun-yonetimi.png" alt="Ürün yönetimi"></a><br><sub>Ürün yönetimi</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/06-raporlar.png"><img src="screenshots/06-raporlar.png" alt="Raporlar"></a><br><sub>Raporlar</sub></td>
    <td align="center"><a href="screenshots/07-kasa-yonetimi.png"><img src="screenshots/07-kasa-yonetimi.png" alt="Kasa yönetimi"></a><br><sub>Kasa yönetimi</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/08-depo-stok-kritik.png"><img src="screenshots/08-depo-stok-kritik.png" alt="Depo ve kritik stok"></a><br><sub>Depo ve kritik stok</sub></td>
    <td align="center"><a href="screenshots/09-toptancilar.png"><img src="screenshots/09-toptancilar.png" alt="Toptancılar"></a><br><sub>Toptancılar</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/10-toptanci-detay.png"><img src="screenshots/10-toptanci-detay.png" alt="Toptancı detayı"></a><br><sub>Toptancı detayı</sub></td>
    <td align="center"><a href="screenshots/11-ayarlar-fis-tasarimi.png"><img src="screenshots/11-ayarlar-fis-tasarimi.png" alt="Fiş tasarımı ve canlı önizleme"></a><br><sub>Fiş tasarımı (canlı önizleme)</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/12-ayarlar-donanim.png"><img src="screenshots/12-ayarlar-donanim.png" alt="Donanım ayarları"></a><br><sub>Donanım ayarları</sub></td>
    <td></td>
  </tr>
</table>

**Telefon paneli (uzaktan takip)**

<table>
  <tr>
    <td align="center" width="25%"><a href="screenshots/remote-giris-aydinlik.png"><img src="screenshots/remote-giris-aydinlik.png" alt="Giriş, aydınlık mod"></a><br><sub>Giriş (aydınlık)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-giris-karanlik.png"><img src="screenshots/remote-giris-karanlik.png" alt="Giriş, karanlık mod"></a><br><sub>Giriş (karanlık)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-bugun-aydinlik.png"><img src="screenshots/remote-bugun-aydinlik.png" alt="Bugün, aydınlık mod"></a><br><sub>Bugün (aydınlık)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-bugun-karanlik.png"><img src="screenshots/remote-bugun-karanlik.png" alt="Bugün, karanlık mod"></a><br><sub>Bugün (karanlık)</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/remote-bugun-devami-aydinlik.png"><img src="screenshots/remote-bugun-devami-aydinlik.png" alt="Kritik stok, personel ve son satışlar"></a><br><sub>Kritik stok ve personel</sub></td>
    <td align="center"><a href="screenshots/remote-gecmis-aydinlik.png"><img src="screenshots/remote-gecmis-aydinlik.png" alt="Geçmiş günler"></a><br><sub>Geçmiş</sub></td>
    <td align="center"><a href="screenshots/remote-kasalar-aydinlik.png"><img src="screenshots/remote-kasalar-aydinlik.png" alt="Kasalar"></a><br><sub>Kasalar</sub></td>
    <td></td>
  </tr>
</table>

### Rolüm

Her şey: mimari, geliştirme, müşteri işletmelerinde yerinde kurulum ve sürekli destek.

---

[Fırat Karataşoğlu](https://github.com/frat-karatasoglu) tarafından geliştirilmekte ve sürdürülmektedir.

---

## English

8 industry-specific versions · 5 active businesses · Turkish market

→ [fkposyazilim.com](https://fkposyazilim.com)

> This is a showcase repository. FK POS is a commercial product, so the source code is not public — this page documents the architecture and the engineering decisions behind it.

### The problem

A shop cannot stop selling because the internet is down. Most modern POS software assumes a stable connection and degrades badly without one. FK POS is built the other way round: the register is the source of truth, and the cloud is an optional observer.

### Architecture

**Offline-first.** Sales, register operations, inventory and invoicing run entirely on the local machine. No connection is required for any part of the checkout flow.

**Cloud sync as an add-on.** An optional Supabase module pushes the current state of the register every 2 minutes, and immediately when connectivity returns, so the owner can watch the shop remotely while the till itself keeps working offline.

**Hardware in Rust.** Barcode scanners, electronic scales, thermal receipt printers and second customer displays are driven through Tauri commands in Rust, keeping device I/O out of the JavaScript layer.

**Single-file backups.** A custom .POS format packs the whole shop state into one file — simple enough for a shop owner to copy to a USB stick.

### Modules

Sales · Inventory · Accounts · Invoicing · Bulk price updates · Reporting

### Stack

React · TypeScript · Tauri · Rust · Supabase (PostgreSQL) · Windows

### Screenshots

Screenshots use fictitious demo data. Click an image to enlarge it.

**Desktop app**

<table>
  <tr>
    <td align="center" width="50%"><a href="screenshots/01-giris-secimi.png"><img src="screenshots/01-giris-secimi.png" alt="Sign-in"></a><br><sub>Sign-in</sub></td>
    <td align="center" width="50%"><a href="screenshots/02-pin-girisi.png"><img src="screenshots/02-pin-girisi.png" alt="PIN sign-in"></a><br><sub>PIN sign-in</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/04-satis-ekrani.png"><img src="screenshots/04-satis-ekrani.png" alt="Sales screen"></a><br><sub>Sales screen</sub></td>
    <td align="center"><a href="screenshots/05-urun-yonetimi.png"><img src="screenshots/05-urun-yonetimi.png" alt="Product management"></a><br><sub>Product management</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/06-raporlar.png"><img src="screenshots/06-raporlar.png" alt="Reports"></a><br><sub>Reports</sub></td>
    <td align="center"><a href="screenshots/07-kasa-yonetimi.png"><img src="screenshots/07-kasa-yonetimi.png" alt="Cash register management"></a><br><sub>Cash register management</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/08-depo-stok-kritik.png"><img src="screenshots/08-depo-stok-kritik.png" alt="Inventory and low stock"></a><br><sub>Inventory &amp; low stock</sub></td>
    <td align="center"><a href="screenshots/09-toptancilar.png"><img src="screenshots/09-toptancilar.png" alt="Suppliers"></a><br><sub>Suppliers</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/10-toptanci-detay.png"><img src="screenshots/10-toptanci-detay.png" alt="Supplier detail"></a><br><sub>Supplier detail</sub></td>
    <td align="center"><a href="screenshots/11-ayarlar-fis-tasarimi.png"><img src="screenshots/11-ayarlar-fis-tasarimi.png" alt="Receipt designer with live preview"></a><br><sub>Receipt designer (live preview)</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/12-ayarlar-donanim.png"><img src="screenshots/12-ayarlar-donanim.png" alt="Hardware settings"></a><br><sub>Hardware settings</sub></td>
    <td></td>
  </tr>
</table>

**Phone panel (remote monitoring)**

<table>
  <tr>
    <td align="center" width="25%"><a href="screenshots/remote-giris-aydinlik.png"><img src="screenshots/remote-giris-aydinlik.png" alt="Sign-in, light mode"></a><br><sub>Sign-in (light)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-giris-karanlik.png"><img src="screenshots/remote-giris-karanlik.png" alt="Sign-in, dark mode"></a><br><sub>Sign-in (dark)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-bugun-aydinlik.png"><img src="screenshots/remote-bugun-aydinlik.png" alt="Today, light mode"></a><br><sub>Today (light)</sub></td>
    <td align="center" width="25%"><a href="screenshots/remote-bugun-karanlik.png"><img src="screenshots/remote-bugun-karanlik.png" alt="Today, dark mode"></a><br><sub>Today (dark)</sub></td>
  </tr>
  <tr>
    <td align="center"><a href="screenshots/remote-bugun-devami-aydinlik.png"><img src="screenshots/remote-bugun-devami-aydinlik.png" alt="Low stock, staff and recent sales"></a><br><sub>Low stock &amp; staff</sub></td>
    <td align="center"><a href="screenshots/remote-gecmis-aydinlik.png"><img src="screenshots/remote-gecmis-aydinlik.png" alt="Sales history"></a><br><sub>History</sub></td>
    <td align="center"><a href="screenshots/remote-kasalar-aydinlik.png"><img src="screenshots/remote-kasalar-aydinlik.png" alt="Registers"></a><br><sub>Registers</sub></td>
    <td></td>
  </tr>
</table>

### My role

Everything: architecture, development, on-site installation at customer premises, and ongoing support.

---

Built and maintained by [Fırat Karataşoğlu](https://github.com/frat-karatasoglu).
