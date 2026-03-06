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

Firebase Kurulum Rehberi
1. Firebase Projesi Oluşturma
Firebase Konsolu'na gidin
"Proje ekle" butonuna tıklayın
Proje adını girin ve "Devam Et" butonuna tıklayın
Google Analytics'e bağlı olarak etkinleştirmenin
"Proje oluştur" butonuna tıklayın
2. Kimlik Doğrulama Kurulumu
Sol menüden "Kimlik Doğrulama" seçeneğini seçin
"Başlayın" butonuna tıklayın
"Giriş yöntemi" sekmesine gidin
"E-posta/Şifre" seçeneğinin etkinleştirilmesi
"Etkinleştir" butonuna tıklayın ve kaydedin
3. Firestore Veritabanı Kurulumu
Sol menüden "Firestore Database" seçeneğini seçin
"Veritabanı oluştur" butonuna tıklayın
"Test modunda başlat" seçeneğini seçin (geliştirme için)
Bir konum seçin (örn: europe-west3)
"Etkinleştir" butonuna tıklayın
Firestore Güvenlik Kuralları
Geliştirme aşamasında test modunu kullanabilirsiniz. Üretim için aşağıdaki kuralları kullanın:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Kullanıcılar
    match /users/{userId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && request.auth.uid == userId;
    }
    
    // Marketler
    match /stores/{storeId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && 
        (request.auth.uid == resource.data.ownerId || 
         get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin');
    }
    
    // Ürünler
    match /products/{productId} {
      allow read: if request.auth != null;
      allow create, update, delete: if request.auth != null && 
        (get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin');
    }
    
    // Siparişler
    match /orders/{orderId} {
      allow read: if request.auth != null && 
        (request.auth.uid == resource.data.userId ||
         get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin');
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow update: if request.auth != null && 
        (get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin');
    }
    
    // Sepetler
    match /carts/{cartId} {
      allow read, write: if request.auth != null && request.auth.uid == resource.data.userId;
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
    }
  }
}
4. Web Uygulaması
Sol menüden proje ayarlarına (⚙️) geçiş
"Proje ayarları" seçin
Aşağıya doğru açılır ve "Uygulamalarınız" bölümünde web simgesine (</>) tıklayın
Uygulama takma adını girin ve "Uygulamayı kaydet" butonuna tıklayın
Firebase'in içeriğini kopyalayın
src/firebase/config.jsdosyasındaki firebaseConfignesneleri bu bilgilerle güncelleyin
5. Depolama (Opsiyonel - Ürün Görselleri İçin)
Sol menüden "Storage" seçin
"Başlayın" butonuna tıklayın
Güvenlik kurallarını kabul edin
Bir konum
"Tamamlandı" ><>
6. İlk Admin Kullanıcı Oluşturma
Uygulamada kayıt olun (admin rolü ile)
Firebase Konsolu > Firestore Veritabanı > kullanıcı koleksiyonuna geçiş
Oluşturduğunuz kullanıcı belgelerini bulun
"rol" uyarısı "admin" olarak güncelleyin
7. İlk Market Oluşturma (Test İçin)
Firestore'da storeskoleksiyona bir test markette sunulabilir:

{
  name: "Test Market",
  address: "Test Mahallesi, Test Caddesi No:1",
  district: "Kadıköy",
  phone: "0216 123 45 67",
  ownerId: "market-sahibi-user-id",
  workingHours: {
    monday: { start: "09:00", end: "18:00", closed: false },
    tuesday: { start: "09:00", end: "18:00", closed: false },
    wednesday: { start: "09:00", end: "18:00", closed: false },
    thursday: { start: "09:00", end: "18:00", closed: false },
    friday: { start: "09:00", end: "18:00", closed: false },
    saturday: { start: "09:00", end: "18:00", closed: false },
    sunday: { start: "10:00", end: "16:00", closed: false }
  }
}
Koleksiyon Yapısı
kullanıcılar
e-posta (dize)
rol (dize): "müşteri", "mağaza sahibi", "yönetici"
ad (dize)
telefon (dize)
adres (dize)
oluşturulma tarihi (zaman damgası)
mağazalar
ad (dize)
adres (dize)
ilçe (dize)
telefon (dize)
sahipKimliği (dize)
Çalışma Saatleri (harita)
ürünler
ad (dize)
fiyat (sayı)
birim (string): "adet", "kg", "gram", "litre"
kategori (dize)
alt kategori (dize)
mağaza kimliği (dize)
resim (dize, isteğe bağlı)
siparişler
kullanıcı kimliği (dize)
mağaza kimliği (dize)
öğeler (dizi)
ToplamFiyat (sayı)
teslimatTarihi (dize)
teslimatZamanDurumu (dize)
adres (dize)
telefon (dize)
durum (dize)
oluşturulma tarihi (zaman damgası)
ödemeDurumu (dize)
arabalar
kullanıcı kimliği (dize)
mağaza kimliği (dize)
öğeler (dizi)
(Zaman damgası) tarihinde güncellendi
Notlar
Geliştirme aşamasında Firestore kuralları'nı test modunda bırakabilirsiniz
Üretim'a ayrılmadan önce güvenlik kuralları'nı mutlaka güncelleyin
Depolamayı kullanmıyorsanız, ürün görselleri için URL'yi kullanabilirsiniz
İlk admin kullanıcıyı manuel olarak Firestore'da oluşturmanız mümkündür



Hızlı Başlangıç ​​- Test Kullanıcıları Oluşturma
Test Kullanıcılarını Oluşturmak İçin:
Yöntem 1: Web Sayfası (ÖNERİLEN - En Kolay)
yüzü:

npm run dev
Tarayıcıda şu adrese geçiş:

http://localhost:5173/create-users
"Tüm Kullanıcıları Oluştur" butonuna tıklayın

Sonuçları bekleyin (10-15 saniye)

Artık giriş yapabilirsiniz!

📋 Oluşturulacak kullanıcılar
Rol	E-posta	Şifre
Yönetici	admin@market.com	admin123
Pazar Sahibi 1	market1@market.com	pazar123
Market Sahibi 2	market2@market.com	pazar123
Müşteri 1	musteri1@market.com	musteri123
Müşteri 2	musteri2@market.com	musteri123
Müşteri 3	musteri3@market.com	musteri123
✅ Giriş Yapma
http://localhost:5173/loginsiz
Yukarıdaki e-posta ve şifrelerden birini kullanın
Giriş yap!
⚠️ÖNEMLİ: Önce Kontrol Edin
Kullanıcıların oluşturmadan önce düzenliliğinin hazır olduğundan emin olun:

Firebase Kimlik Doğrulaması etkinleştirildi (E-posta/Şifre)
Firestore Veritabanı dahil
 npm run devile uygulama çalışıyor
Sorun mu yaşıyorsunuz? → TROUBLESHOOTING.mdbağlantıya bakın.

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
