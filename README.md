# Online Market & Teslimat Sistemi

React ve Firebase kullanılarak geliştirilmiş online market ve teslimat sistemi.

## Özellikler

- **Kullanıcı Rolleri**: Müşteri, Market Sahibi, Admin
- **Market Seçimi**: İl > İlçe > Market seçimi
- **Kategori Yapısı**: 
  - Gıda (Meyve & Sebze, Et & Tavuk & Balık, Süt & Süt Ürünleri, vb.)
  - Paketli Gıda (Konserve, Makarna, Atıştırmalıklar, vb.)
  - İçecek (Su, Gazlı İçecekler, Meyve Suları, vb.)
  - Donuk Ürünler (Dondurulmuş Sebze & Meyve, Donuk Pizza, Dondurma)
- **Sepet Yönetimi**: Ürün ekleme, çıkarma, miktar güncelleme
- **Teslimat Zamanı Seçimi**: Market çalışma saatlerine göre randevu sistemi
- **Market Sahibi Paneli**: Ürün yönetimi, çalışma saatleri düzenleme
- **Admin Paneli**: Sipariş, market ve kullanıcı yönetimi
- **Ödeme**: Teslimat sırasında nakit ödeme

## Kurulum

1. Bağımlılıkları yükleyin:
```bash
npm install
```

2. Firebase yapılandırmasını yapın:
   - Firebase Console'dan projenizi oluşturun
   - `src/firebase/config.js` dosyasındaki `firebaseConfig` objesini Firebase Console'dan alacağınız bilgilerle doldurun

3. Firebase Firestore kurallarını ayarlayın:
   - Authentication'ı etkinleştirin (Email/Password)
   - Firestore Database oluşturun
   - Gerekli koleksiyonları oluşturun (users, stores, products, orders, carts)

4. Geliştirme sunucusunu başlatın:
```bash
npm run dev
```
Firebase Dağıtım Adımları
📋 Web Sitesini Görüntüleme
Adım 1: Siteyi Aç
Tarayıcınızı açın (Chrome, Firefox, Edge vb.)

Adres çubuğuna şu URL'yi yazın ve Enter'a basın:

https://online-market-randevu-sistemi.web.app
VEYA

https://online-market-randevu-sistemi.firebaseapp.com
Site açılırsa ✅ başarılı!

Giriş/Kayıt olun
"Online Market" başlığı görünmeli
Firebase'in varsayılan sayfası görünüyorsa:

Ctrl + Shift + R(Windows) veya Cmd + Shift + R(Mac) ile sabit yenileme yapın
Veya tarayıcı önbelleğini temizleyin
🔧 Firebase Konsol Erişimi (Opsiyonel - Site Çalışıyorsa Gerekmez)
Adım 1: Doğru Google Hesabıyla Giriş
Chrome'da sağ üst köşedeki profil ikonuna tıklayın
caymazlutfiye3@gmail.comile giriş yaptığınızdan emin olun
Eğer farklı bir hesap görünüyorsa:
Profil ikonuna tıklayın
"Farklı bir hesap kullan" seçeneğini seçin
caymazlutfiye3@gmail.comile giriş yap
Adım 2: Firebase Console'a Git
Şu URL'yi açın:

https://console.firebase.google.com/project/online-market-randevu-sistemi/overview
Eğer "Bu proje mevcut değil veya onu görüntüleme izniniz yok" hatası görürseniz:

Sağ üstteki profil ikonuna tıklayın
Doğru hesabı seçin ( caymazlutfiye3@gmail.com)
Sayfayı yenileyin ( F5)
Adım 3: MFA (2 Adımlı Doğrulama) Etkinleştirme (Gerekirse)
Firebase Console'daki kırmızı uyarı banner'ında "2SV'yi aç" butonuna tıklayın
Veya doğrudan: https://myaccount.google.com/security
"2 Adımlı Doğrulama" bölümü bulun
"Başlat" butonuna tıklayın
Adımları takip ederek telefon numaranızı ekleyin
🔄 Yeni güncellemelerden Sonra Tekrar Konuşlandır Etme
Adım 1: Kodu Güncelle
Kodunuzda değişiklik yapın
Değişiklikler
Adım 2: Et'i Oluşturun
Terminal'de (PowerShell) şu çalıştırılır:

cd "online market ve teslimat sistemi\online-market-app"
npm run build
Adım 3: Et'i Dağıtın
Sonrasında şunları inşa edin:

firebase deploy --only hosting
Adım 4: Bekle
Dağıtım işlemi 1-2 dakikada tamamlanır. "Dağıtım tamamlandı!" Mesajını tamamladınız.

Adım 5: Et'yi Test Edin
Tarayıcıda siteyi aç ( https://online-market-randevu-sistemi.web.app )
Ctrl + Shift + Rile zor yenileme yap
değişikliklerin belirtilmediğini kontrol edin
⚠️Sorun Giderme
Site açılmıyor / Firebase varsayılan sayfası görünüyor
Yeniden yükle:Ctrl + Shift + R
Tarayıcı önbelleğini temizleyin
Gizli pencere modunu açma (Ctrl + Shift + N)
Farklı bir tarayıcı hatası
Konsola erişemiyorum
Doğru Google hesabıyla giriş yaptığınızdan emin olun
MFA (2 Adımlı Doğrulama) etkinleştirmenin
Tarayıcıyı yeniden açma
Dağıtım hatası al
Firebase CLI'nin güncel olduğundan emin olun:firebase --version
Build'in başarılı olduğundan emin olun:npm run build
.firebasercdosyada doğru proje kimliğinin olup olmadığını kontrol edin
📍 Önemli URL'ler
Canlı Site: https://online-market-randevu-sistemi.web.app
Firebase Konsolu: https://console.firebase.google.com/project/online-market-randevu-sistem/overview
Hosting Ayarları: https://console.firebase.google.com/project/online-market-randevu-sistemi/hosting/main
✅ Hızlı Kontrol Listesi
Site URL'sini tarayıcıda düzenler
Giriş/Kayıt olun sayfa görünüyor
Sert yenileme yaptım (Ctrl + Shift + R)
Console'a açmak için doğru Google hesabıyla giriş yaptım
MFA etkinleştirdim (gerekirse)

## Firebase Firestore Yapısı

### Koleksiyonlar

- **users**: Kullanıcı bilgileri (email, role, name, phone, address)
- **stores**: Market bilgileri (name, address, district, phone, ownerId, workingHours)
- **products**: Ürün bilgileri (name, price, unit, category, subcategory, storeId, image)
- **orders**: Sipariş bilgileri (userId, storeId, items, totalPrice, deliveryDate, deliveryTimeSlot, address, phone, status)
- **carts**: Sepet bilgileri (userId, storeId, items)

## Kullanıcı Rolleri

- **customer**: Müşteri - Alışveriş yapabilir, sipariş verebilir
- **storeOwner**: Market Sahibi - Ürün ekleyip düzenleyebilir, çalışma saatlerini ayarlayabilir
- **admin**: Admin - Tüm siparişleri, marketleri ve kullanıcıları yönetebilir

## Önemli Notlar

- Market sahipleri için market kaydı admin tarafından yapılmalıdır
- Çalışma saatleri market sahibi tarafından düzenlenebilir
- Teslimat saatleri 30 dakikalık slotlar halinde gösterilir
- Ödeme teslimat sırasında nakit olarak alınır

## Geliştirme

```bash
# Geliştirme sunucusu
npm run dev

# Production build
npm run build

# Build önizleme
npm run preview
```

## Lisans

Bu proje eğitim amaçlı geliştirilmiştir.
