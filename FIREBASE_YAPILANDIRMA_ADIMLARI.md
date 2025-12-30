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

