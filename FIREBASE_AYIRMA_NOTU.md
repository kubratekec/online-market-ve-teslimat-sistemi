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

## ⚠️ Önemli Not

Artık e_ticaret projesindeki Firebase verilerine erişemezsiniz. Tüm veriler yeni Firebase projenizde olacak.

