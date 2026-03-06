[14:20, 06.03.2026] kübra: # 🛒 Online Market ve Teslimat Sistemi

React ve Firebase kullanılarak geliştirilmiş; Müşteri, Market Sahibi ve Admin rollerine sahip kapsamlı bir e-ticaret, randevu ve teslimat platformudur. Bu proje, Aksaray Üniversitesi Yönetim Bilişim Sistemleri (MIS) bölümü akademik çalışmaları kapsamında hazırlanmıştır.

## 🌟 Öne Çıkan Özellikler

- *Gelişmiş Filtreleme:* İl > İlçe > Market hiyerarşisi ile konum bazlı alışveriş.
- *Detaylı Kategori Yapısı:* Gıda, Paketli Gıda, İçecek ve Donuk Ürünler ana kategorileri altında alt kırılımlar.
- *Randevu Sistemi:* Market çalışma saatlerine göre 30 dakikalık slotlarla teslimat zamanı seçimi.
- *Rol Bazlı Paneller:* - *Müşteri:* Ürün seçimi, sepet yönetimi ve sipariş takibi.
  - *Market Sahibi:* Ürün ekleme/düzenleme ve çalışma saatleri yönetimi.
  - *Admin:* Tüm kullanıcı, sipariş ve market verilerinin kontrolü.
- *Ödeme:* Teslimat sırasında nakit ödeme seçeneği.

## 🛠 Teknik Kurulum ve Çalıştırma

Projeyi lokal bilgisayarınızda çalıştırmak için şu adımları izleyin:

1. *Bağımlılıkları Yükleyin:*
   ```bash
   npm install
[14:21, 06.03.2026] kübra: 2Firebase Yapılandırması:
src/firebase/config.js dosyasındaki firebaseConfig objesini kendi Firebase projenizden aldığınız bilgilerle doldurun.
[14:21, 06.03.2026] kübra: 3)sunucuyu başlatın
[14:21, 06.03.2026] kübra: npm run dev
[14:21, 06.03.2026] kübra: Firebase Yapılandırma Rehberi
​Projenin tam kapasite çalışması için Firebase Console (caymazlutfiye3@gmail.com hesabı ile) üzerinden şu ayarların yapılması gerekir:
​Authentication: "Email/Password" yöntemini etkinleştirin.
​Firestore Database: "Test modunda" başlatın ve şu koleksiyonları oluşturun: users, stores, products, orders, carts.
​Güvenlik Kuralları: Adminlerin tam yetkiye, kullanıcıların ise sadece kendi verilerine erişebileceği kurallar tanımlanmalıdır.
​Hosting: Değişiklik sonrası npm run build ve ardından firebase deploy --only hosting komutlarını kullanın.
​🧪 Test Kullanıcıları ve Hızlı Giriş
​Sistemi denemek için aşağıdaki hazır hesapları kullanabilir veya http://localhost:5173/create-users adresinden otomatik oluşturabilirsiniz:
[14:22, 06.03.2026] kübra: Rol E-posta Şifre
Yönetici (Admin) admin@market.com admin123
Market Sahibi market1@market.com pazar123
Müşteri musteri1@market.com musteri123
[14:22, 06.03.2026] kübra: Sorun Giderme (Quick Fix)
​Giriş Hatası: Firebase Console'da Authentication sekmesinde kullanıcının varlığını ve şifresini kontrol edin.
​Veri Görünmüyor: Firestore'da "Test Modu" süresinin dolmadığından veya kuralların (Rules) doğru olduğundan emin olun.
​Güncelleme Yansıması: Canlı sitede değişiklik görmüyorsanız Ctrl + Shift + R ile önbelleği temizleyerek zorla yenileme yapın.
​📍 Bağlantılar
​Canlı Site: https://online-market-randevu-sistemi.web.app
​Geliştirici: Kübra Tekeç - Aksaray Üniversitesi MIS Bölümü
