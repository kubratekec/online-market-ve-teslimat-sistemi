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



⚡ 5 Dakikada Firebase Yapılandırması
1️⃣ Firebase Projesi Oluşturma
Firebase Konsol'a geçiş : https://console.firebase.google.com/
"Proje ekle" (Proje Ekle) butonuna tıklayın
Proje adını girin: online-market-app(veya istediğiniz isim)
Google Analytics'i atlayabilirsiniz (isteğe bağlı)
"Proje Oluştur" (Proje Oluştur) butonuna tıklayın
Birkaç saniye bekleyin, proje oluşturulacak
2️⃣ Web Uygulaması Ekleme
Projenin eklenmesinden sonra, ana sayfada "Web" (</>) simgesine tıklayın
Uygulama adını girin:Online Market App
"Uygulamayı kaydet" (Uygulamayı Kaydet) butonuna tıklayın
Açılan pencerede kopyalayın :
const firebaseConfig = {
  apiKey: "AIzaSy...",           // ← Burayı kopyala
  authDomain: "...",              // ← Burayı kopyala
  projectId: "...",               // ← Burayı kopyala
  storageBucket: "...",           // ← Burayı kopyala
  messagingSenderId: "...",       // ← Burayı kopyala
  appId: "..."                    // ← Burayı kopyala
}
"Konsol'a devam et" butonuna tıklayın
3️⃣ Yapılandırmayı Projeye Ekleme
Projenize src/firebase/config.jsneyi açın
Firebase Console'dan kopyalardaki bilgiler firebaseConfignesneye yerleşiyor
Dosyayı Kaydet (Ctrl+S)
Örnek:

const firebaseConfig = {
  apiKey: "AIzaSyBvOkBvqLirjKGhiE-example",
  authDomain: "online-market-app.firebaseapp.com",
  projectId: "online-market-app",
  storageBucket: "online-market-app.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abc123def456"
};
4️⃣ Authentication'ı Etkileştirme
Firebase Console'da sol menüden "Kimlik Doğrulama" seçeneği
"Başlayın" (Başlayın) butonuna tıklayın
"Giriş yöntemi" (Giriş yöntemi) sekmesine geçiş
"E-posta/Şifre" satırını bulun ve tıklayın
"Etkinleştir" (Etkinleştir) toggle'ını açın
"Kaydet" (Kaydet) butonuna tıklayın
5️⃣ Firestore Database'i Etkileştirme
Sol menüden "Firestore Database" seçeneğini seçin
"Veritabanı oluştur" (Veritabanı oluştur) butonuna tıklayın
"Test modunda başlat" (Test modu başlatma) seç
Veritabanından seçin (örn: europe-west3veya europe-west1)
"Etkinleştir" (Etkinleştir) butonuna tıklayın
⚠️ NOT: Test modunda herkes veri tabanına erişebilir. Üretim'a ayrılmadan önce Güvenlik Kuralları'nı güncelleyin!

6️⃣ Storage'ı Etkinleştirme (Opsiyonel - Ürün Görselleri İçin)
Sol menüden "Storage" seçin
"Başlayın" butonuna tıklayın
Güvenlik kurallarını kabul edin (test modu)
Bir konum
"Tamamlandı" ><>
7️⃣ İlk Admin Kullanıcı Oluşturma
Uygulamada kayıt olun (yönetici rolünü seçebilirsiniz)
Firebase Konsolu > Firestore Veritabanı > kullanıcı koleksiyonuna geçiş
Oluşturduğunuz kullanıcı belgelerini bulun
"rol" uyarısı "admin" olarak güncelleyin
veya

Firestore'da doğrudan şunları ekleyin:

Koleksiyon:users
Belge Kimliği: (kendi durumunuzun bir kimliği veya otomatik)
Alanlar:
email(dize): admin@example.com
role(dize): yönetici
name(dize): Yönetici Kullanıcı
createdAt(zaman damgası): şu anki zaman
✅ Kurulum Tamamlandı!
Artık uygulamanızı çalıştırabilirsiniz:

npm run dev
🔒 Güvenlik Kuralları (Üretim İçin)
Test edildikten sonra Firestore Security Rules'ı güncelleyin. Ayrıntılar için FIREBASE_SETUP.mdayrıntılara bakın.

📋 Kontrol Listesi
Firebase projeleri
Web uygulamaları eklendi
 src/firebase/config.jsDosya güncellendi
Kimlik doğrulama etkinleştirildi (E-posta/Şifre)
Firestore Veritabanı dahil
Depolama etkinleştirildi ()
İlk admin bölümü yer aldı
❓ Sorun mu yaşıyorsunuz?
FIREBASE_SETUP.mdiçeriğinde detaylı bilgiler var
Firebase Console'da proje sistemi kontrolü edinin
Tarayıcı konsolunda hata mesajlarını kontrol edin

## Firebase Firestore Yapısı
# 🔥 Firebase Yapılandırma - Adım Adım Rehber

## ⚡ Hızlı Yapılandırma (5 Dakika)

### Adım 1: Firebase Console'a Gidin

1. Tarayıcıda şu adresi açın: https://console.firebase.google.com/
2. Google hesabınızla giriş yapın

### Adım 2: Yeni Proje Oluşturun

1. **"Add project"** (Proje Ekle) butonuna tıklayın
2. Proje adını girin: `online-market-teslimat` (veya istediğiniz isim)
3. Google Analytics'i **atlayabilirsiniz** (isteğe bağlı)
4. **"Create project"** (Proje Oluştur) butonuna tıklayın
5. Birkaç saniye bekleyin

### Adım 3: Web Uygulaması Ekleyin

1. Proje oluşturulduktan sonra ana sayfada **"Web" (</>)** ikonuna tıklayın
2. Uygulama takma adı: `Online Market App`
3. Firebase Hosting'i şimdilik seçmeyin
4. **"Register app"** (Uygulamayı Kaydet) butonuna tıklayın

### Adım 4: Yapılandırma Bilgilerini Kopyalayın

Firebase size şu formatta bir kod gösterecek:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "online-market-teslimat.firebaseapp.com",
  projectId: "online-market-teslimat",
  storageBucket: "online-market-teslimat.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef1234567890",
  measurementId: "G-XXXXXXXXXX"
};
```

**Bu bilgileri kopyalayın!**

### Adım 5: Config Dosyasını Güncelleyin

1. Projenizde `src/firebase/config.js` dosyasını açın
2. `firebaseConfig` objesini Firebase'den kopyaladığınız bilgilerle değiştirin
3. Dosyayı kaydedin

### Adım 6: Authentication'ı Etkinleştirin

1. Firebase Console'da sol menüden **"Authentication"** seçin
2. **"Get started"** (Başlayın) butonuna tıklayın
3. **"Sign-in method"** (Giriş yöntemi) sekmesine gidin
4. **"Email/Password"** satırını bulun ve tıklayın
5. **"Enable"** (Etkinleştir) toggle'ını açın
6. **"Save"** (Kaydet) butonuna tıklayın

### Adım 7: Firestore Database'i Oluşturun

1. Sol menüden **"Firestore Database"** seçin
2. **"Create database"** (Veritabanı oluştur) butonuna tıklayın
3. **"Start in test mode"** (Test modunda başlat) seçin
4. Bir konum seçin (örn: `europe-west3` veya size en yakın)
5. **"Enable"** (Etkinleştir) butonuna tıklayın

### Adım 8: Storage'ı Etkinleştirin (Opsiyonel)

1. Sol menüden **"Storage"** seçin
2. **"Get started"** butonuna tıklayın
3. Security rules'u kabul edin
4. Bir konum seçin
5. **"Done"** butonuna tıklayın

## ✅ Kontrol Listesi

- [ ] Firebase projesi oluşturuldu
- [ ] Web uygulaması eklendi
- [ ] `src/firebase/config.js` dosyası güncellendi
- [ ] Authentication etkinleştirildi (Email/Password)
- [ ] Firestore Database oluşturuldu
- [ ] Storage etkinleştirildi (opsiyonel)

## 🚀 Sonraki Adımlar

1. Uygulamayı çalıştırın: `npm run dev`
2. `/create-users` sayfasından test kullanıcılarını oluşturun
3. Giriş yapıp sistemi test edin

## ❓ Sorun mu Yaşıyorsunuz?

- `FIREBASE_SETUP.md` dosyasında detaylı bilgiler var
- Browser console'da (F12) hata mesajlarını kontrol edin
- Firebase Console'da proje ayarlarını kontrol edin



# Test Kullanıcıları Rehberi

## ⚠️ ÖNEMLİ: İlk Kullanıcıyı Oluşturmanız Gerekiyor!

Bu proje için henüz hiçbir kullanıcı oluşturulmamış. Giriş yapabilmek için önce kullanıcı hesabı oluşturmanız gerekiyor.

---

## 📝 Kullanıcı Oluşturma Yöntemleri

### Yöntem 1: Uygulama Üzerinden Kayıt Ol (ÖNERİLEN)

1. Tarayıcıda uygulamayı açın: `http://localhost:5173`
2. Sağ üst köşede **"Kayıt Ol"** butonuna tıklayın
3. Formu doldurun:
   - **Rol seçin:** Müşteri, Market Sahibi veya Admin
   - **Ad Soyad:** İsim girin
   - **Email:** Email adresinizi girin
   - **Telefon:** Telefon numaranızı girin
   - **Şifre:** En az 6 karakter şifre girin
   - **Şifre Tekrar:** Şifreyi tekrar girin
4. **"Kayıt Ol"** butonuna tıklayın

### Yöntem 2: Firebase Console'dan Manuel Oluşturma

1. [Firebase Console](https://console.firebase.google.com/) → Projenizi seçin
2. **Authentication** → **Users** sekmesine gidin
3. **"Add user"** butonuna tıklayın
4. Email ve şifre girin
5. **"Add user"** butonuna tıklayın
6. **Firestore Database** → **users** koleksiyonuna gidin
7. Yeni doküman oluşturun (Document ID = Authentication UID)
8. Alanları ekleyin:
   - `email` (string): kullanıcının email'i
   - `role` (string): "customer", "storeOwner" veya "admin"
   - `name` (string): kullanıcının adı
   - `phone` (string): telefon numarası
   - `createdAt` (timestamp): şu anki zaman

---

## 📋 Önerilen Test Kullanıcıları

### 1. Müşteri (Customer)

**Kayıt Ol Sayfasında:**
- Rol: **Müşteri**
- Ad Soyad: Ahmet Yılmaz
- Email: `musteri@test.com`
- Telefon: 5551234567
- Şifre: `musteri123`

**Özellikler:**
- Market seçebilir
- Ürünleri sepete ekleyebilir
- Sipariş verebilir
- Siparişlerini görüntüleyebilir

---

### 2. Market Sahibi (Store Owner)

**Kayıt Ol Sayfasında:**
- Rol: **Market Sahibi**
- Ad Soyad: Ayşe Demir
- Email: `market@test.com`
- Telefon: 5551234568
- Şifre: `market123`

**Özellikler:**
- Ürün ekleyip düzenleyebilir
- Çalışma saatlerini ayarlayabilir
- Siparişleri görüntüleyebilir

**NOT:** Market sahibi için ayrıca Firestore'da `stores` koleksiyonunda bir market kaydı oluşturmanız gerekiyor:
```json
{
  "name": "Test Market",
  "address": "Test Mahallesi, Test Caddesi No:1",
  "district": "Kadıköy",
  "phone": "0216 123 45 67",
  "ownerId": "MARKET_SAHIBI_UID",
  "workingHours": {
    "monday": { "start": "09:00", "end": "18:00", "closed": false },
    "tuesday": { "start": "09:00", "end": "18:00", "closed": false },
    "wednesday": { "start": "09:00", "end": "18:00", "closed": false },
    "thursday": { "start": "09:00", "end": "18:00", "closed": false },
    "friday": { "start": "09:00", "end": "18:00", "closed": false },
    "saturday": { "start": "09:00", "end": "18:00", "closed": false },
    "sunday": { "start": "10:00", "end": "16:00", "closed": false }
  }
}
```

---

### 3. Admin

**Kayıt Ol Sayfasında:**
- Rol: **Admin**
- Ad Soyad: Mehmet Kaya
- Email: `admin@test.com`
- Telefon: 5551234569
- Şifre: `admin123`

**Özellikler:**
- Tüm siparişleri görüntüleyebilir
- Sipariş durumlarını güncelleyebilir
- Marketleri görüntüleyebilir
- Kullanıcıları görüntüleyebilir

**ÖNEMLİ:** Admin rolü ile kayıt olduktan sonra, Firebase Console'da Firestore Database → users → [admin kullanıcısının UID'si] → role alanını kontrol edin. Eğer "admin" değilse manuel olarak "admin" olarak güncelleyin.

---

## 🚀 Hızlı Başlangıç

### 1. İlk Müşteri Oluşturma

1. `http://localhost:5173/register` adresine gidin
2. Rol: **Müşteri** seçin
3. Bilgileri girin (örn: musteri@test.com / musteri123)
4. Kayıt olun
5. Giriş yapın

### 2. İlk Admin Oluşturma

1. `http://localhost:5173/register` adresine gidin
2. Rol: **Admin** seçin
3. Bilgileri girin (örn: admin@test.com / admin123)
4. Kayıt olun
5. Firebase Console'da role alanını kontrol edin ve gerekirse "admin" olarak güncelleyin
6. Giriş yapın

---

## 📝 Özet Test Kullanıcı Bilgileri

| Rol | Email | Şifre |
|-----|-------|-------|
| Müşteri | musteri@test.com | musteri123 |
| Market Sahibi | market@test.com | market123 |
| Admin | admin@test.com | admin123 |

---

## ✅ Kontrol Listesi

- [ ] Firebase Authentication etkinleştirildi (Email/Password)
- [ ] Firestore Database oluşturuldu
- [ ] İlk müşteri kullanıcısı oluşturuldu
- [ ] İlk admin kullanıcısı oluşturuldu (rol kontrol edildi)
- [ ] Market sahibi için market kaydı oluşturuldu (storeOwner kullanıcısı için)

---

## 🔍 Sorun Giderme

### "Giriş başarısız" hatası
- Kullanıcı henüz oluşturulmamış olabilir
- Şifreyi kontrol edin
- Firebase Authentication'ın etkin olduğundan emin olun

### "Yetkisiz erişim" hatası
- Kullanıcının role alanı Firestore'da doğru ayarlanmamış olabilir
- Firebase Console → Firestore Database → users → [kullanıcı UID] → role alanını kontrol edin

### Market Sahibi paneli açılmıyor
- Kullanıcının bir market kaydı olmalı
- Firestore'da stores koleksiyonunda ownerId alanı kullanıcının UID'si ile eşleşen bir kayıt olmalı



# Firestore Security Rules - Stores Delete İçin

Eğer market silme işlemi çalışmıyorsa, Firestore Security Rules'ı kontrol edin.

## Sorun

Admin panelinden market silme işlemi çalışmıyor olabilir. Bu genellikle Firestore Security Rules nedeniyle olur.

## Çözüm

Firebase Console'da Firestore Database → Rules sekmesine gidin ve şu kuralları kullanın:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Helper function: Admin mi?
    function isAdmin() {
      return request.auth != null && 
        get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin';
    }
    
    // Kullanıcılar
    match /users/{userId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && request.auth.uid == userId;
    }
    
    // Marketler
    match /stores/{storeId} {
      allow read: if request.auth != null;
      // Admin tüm marketleri silebilir ve yazabilir
      allow write, delete: if request.auth != null && isAdmin();
      // Market sahibi kendi marketini güncelleyebilir
      allow update: if request.auth != null && request.auth.uid == resource.data.ownerId;
    }
    
    // Ürünler
    match /products/{productId} {
      allow read: if request.auth != null;
      allow create, update, delete: if request.auth != null && 
        (get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         isAdmin());
    }
    
    // Siparişler
    match /orders/{orderId} {
      allow read: if request.auth != null && 
        (request.auth.uid == resource.data.userId ||
         get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         isAdmin());
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow update: if request.auth != null && 
        (get(/databases/$(database)/documents/stores/$(resource.data.storeId)).data.ownerId == request.auth.uid ||
         isAdmin());
    }
    
    // Sepetler
    match /carts/{cartId} {
      allow read, write: if request.auth != null && request.auth.uid == resource.data.userId;
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
    }
  }
}
```

## Test Modu (Geliştirme İçin)

Eğer hala çalışmıyorsa, geliştirme aşamasında test mode kullanabilirsiniz (sadece geliştirme için):

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.time < timestamp.date(2025, 12, 31);
    }
  }
}
```

⚠️ **UYARI:** Test mode herkese yazma izni verir. Production'da kullanmayın!

## Adımlar

1. Firebase Console → Firestore Database → Rules
2. Yukarıdaki kurallardan birini yapıştırın
3. "Publish" butonuna tıklayın
4. Tarayıcıda sayfayı yenileyin
5. Market silme işlemini tekrar deneyin






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
# "Mağaza" İçeren Kayıtları Silme - Browser Console Scripti

Eğer admin panelindeki buton çalışmıyorsa, bu scripti tarayıcı console'unda çalıştırabilirsiniz.

## Nasıl Kullanılır:

1. Admin Panel sayfasında F12 tuşuna basın
2. **Console** sekmesine gidin
3. Aşağıdaki kodu tamamen kopyalayıp console'a yapıştırın
4. Enter'a basın
5. Onay penceresinde "OK" deyin
6. Script tüm "mağaza" içeren kayıtları silecek


   # ⚠️ Firebase Projesi Ayrıldı

Online Market & Teslimat Sistemi artık e_ticaret projesinden bağımsız çalışıyor.

## 🔧 Yapılması Gerekenler

### 1. Yeni Firebase Projesi Oluşturun

1. [Firebase Console](https://console.firebase.google.com/) → "Add project"
2. Proje adı: `online-market-teslimat` (veya istediğiniz isim)
3. Web uygulaması ekleyin (</> ikonu)
4. Yapılandırma bilgilerini kopyalayın

### 2. Config Dosyasını Güncelleyin

`src/firebase/config.js` dosyasındaki `firebaseConfig` objesini yeni Firebase projenizin bilgileriyle doldurun.

### 3. Firebase Servislerini Etkinleştirin

- ✅ Authentication (Email/Password)
- ✅ Firestore Database
- ✅ Storage (opsiyonel)

### 4. Test Kullanıcılarını Oluşturun

`/create-users` sayfasından test kullanıcılarını oluşturun.

## 📋 Detaylı Rehber

- `FIREBASE_HIZLI_KURULUM.md` - Hızlı kurulum adımları
- `FIREBASE_SETUP.md` - Detaylı kurulum rehberi


## Script:

```javascript
(async function deleteAllMagazaStores() {
  // Firebase'i import et
  const { initializeApp } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-app.js');
  const { getFirestore, collection, getDocs, doc, deleteDoc } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore.js');
  
  // Firebase config - src/firebase/config.js dosyasındaki bilgileri buraya kopyalayın
  const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "your-messaging-sender-id",
    appId: "your-app-id",
  };
  
  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  
  console.log('🚀 "Mağaza" içeren kayıtlar siliniyor...\n');
  
  try {
    // Tüm marketleri al
    const querySnapshot = await getDocs(collection(db, 'stores'));
    const allStores = [];
    querySnapshot.forEach((doc) => {
      allStores.push({ id: doc.id, ...doc.data() });
    });
    
    console.log(`📊 Toplam ${allStores.length} adet market bulundu\n`);
    
    // "Mağaza" içeren kayıtları filtrele
    const storesToDelete = allStores.filter(store => {
      const name = (store.name || '').toLowerCase();
      return name.includes('mağaza');
    });
    
    console.log(`🎯 ${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu\n`);
    
    if (storesToDelete.length === 0) {
      console.log('✅ Silinecek kayıt bulunamadı');
      return;
    }
    
    // Örnekleri göster
    console.log('Silinecek kayıtlar (ilk 10):');
    storesToDelete.slice(0, 10).forEach((store, index) => {
      console.log(`${index + 1}. ${store.name} (ID: ${store.id})`);
    });
    if (storesToDelete.length > 10) {
      console.log(`... ve ${storesToDelete.length - 10} adet daha\n`);
    }
    
    // Onay iste
    const confirmDelete = confirm(
      `${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu.\n\nHepsini silmek istediğinize emin misiniz?\n\nBu işlem geri alınamaz!`
    );
    
    if (!confirmDelete) {
      console.log('❌ İşlem iptal edildi');
      return;
    }
    
    console.log('🗑️ Silme işlemi başlıyor...\n');
    
    let deletedCount = 0;
    let errorCount = 0;
    
    // Her kayıt için silme işlemini gerçekleştir
    for (const store of storesToDelete) {
      try {
        await deleteDoc(doc(db, 'stores', store.id));
        deletedCount++;
        if (deletedCount % 100 === 0) {
          console.log(`✅ ${deletedCount} adet kayıt silindi...`);
        }
      } catch (error) {
        console.error(`❌ Hata (${store.name}):`, error.message);
        errorCount++;
      }
    }
    
    console.log('\n' + '='.repeat(50));
    console.log(`\n✅ ${deletedCount} adet kayıt başarıyla silindi`);
    if (errorCount > 0) {
      console.log(`❌ ${errorCount} adet kayıt silinirken hata oluştu`);
    }
    console.log('='.repeat(50) + '\n');
    
    // Sayfayı yenile
    console.log('🔄 Sayfa yenileniyor...');
    setTimeout(() => {
      window.location.reload();
    }, 2000);
    
  } catch (error) {
    console.error('❌ Kritik hata:', error);
    alert('Hata oluştu: ' + error.message);
  }
})();
```


"Mağaza" İçeren Kayıtları Silme - Browser Console Scripti
Eğer admin panelindeki buton çalışmıyorsa, bu scripti tarayıcı console'unda çalıştırabilirsiniz.

Nasıl Kullanılır:
Admin Panel sayfasında F12 tuşuna basın
Console sekmesine gidin
Aşağıdaki kodu tamamen kopyalayıp console'a yapıştırın
Enter'a basın
Onay penceresinde "OK" deyin
Script tüm "mağaza" içeren kayıtları silecek
Script:
(async function deleteAllMagazaStores() {
  // Firebase'i import et
  const { initializeApp } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-app.js');
  const { getFirestore, collection, getDocs, doc, deleteDoc } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore.js');
  
  // Firebase config - src/firebase/config.js dosyasındaki bilgileri buraya kopyalayın
  const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "your-messaging-sender-id",
    appId: "your-app-id",
  };
  
  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  
  console.log('🚀 "Mağaza" içeren kayıtlar siliniyor...\n');
  
  try {
    // Tüm marketleri al
    const querySnapshot = await getDocs(collection(db, 'stores'));
    const allStores = [];
    querySnapshot.forEach((doc) => {
      allStores.push({ id: doc.id, ...doc.data() });
    });
    
    console.log(`📊 Toplam ${allStores.length} adet market bulundu\n`);
    
    // "Mağaza" içeren kayıtları filtrele
    const storesToDelete = allStores.filter(store => {
      const name = (store.name || '').toLowerCase();
      return name.includes('mağaza');
    });
    
    console.log(`🎯 ${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu\n`);
    
    if (storesToDelete.length === 0) {
      console.log('✅ Silinecek kayıt bulunamadı');
      return;
    }
    
    // Örnekleri göster
    console.log('Silinecek kayıtlar (ilk 10):');
    storesToDelete.slice(0, 10).forEach((store, index) => {
      console.log(`${index + 1}. ${store.name} (ID: ${store.id})`);
    });
    if (storesToDelete.length > 10) {
      console.log(`... ve ${storesToDelete.length - 10} adet daha\n`);
    }
    
    // Onay iste
    const confirmDelete = confirm(
      `${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu.\n\nHepsini silmek istediğinize emin misiniz?\n\nBu işlem geri alınamaz!`
    );
    
    if (!confirmDelete) {
      console.log('❌ İşlem iptal edildi');
      return;
    }
    
    console.log('🗑️ Silme işlemi başlıyor...\n');
    
    let deletedCount = 0;
    let errorCount = 0;
    
    // Her kayıt için silme işlemini gerçekleştir
    for (const store of storesToDelete) {
      try {
        await deleteDoc(doc(db, 'stores', store.id));
        deletedCount++;
        if (deletedCount % 100 === 0) {
          console.log(`✅ ${deletedCount} adet kayıt silindi...`);
        }
      } catch (error) {
        console.error(`❌ Hata (${store.name}):`, error.message);
        errorCount++;
      }
    }
    
    console.log('\n' + '='.repeat(50));
    console.log(`\n✅ ${deletedCount} adet kayıt başarıyla silindi`);
    if (errorCount > 0) {
      console.log(`❌ ${errorCount} adet kayıt silinirken hata oluştu`);
    }
    console.log('='.repeat(50) + '\n');
    
    // Sayfayı yenile
    console.log('🔄 Sayfa yenileniyor...');
    setTimeout(() => {
      window.location.reload();
    }, 2000);
    
  } catch (error) {
    console.error('❌ Kritik hata:', error);
    alert('Hata oluştu: ' + error.message);
  }
})();
Alternatif: Sayfada Yenile Butonu
Admin panelinde "🔄 Yenile" butonuna tıklayarak listeyi manuel olarak yenileyebilirsiniz.

## Alternatif: Sayfada Yenile Butonu

Admin panelinde "🔄 Yenile" butonuna tıklayarak listeyi manuel olarak yenileyebilirsiniz.




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
