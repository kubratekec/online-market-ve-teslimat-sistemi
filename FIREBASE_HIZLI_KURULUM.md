# 🔥 Firebase Hızlı Kurulum Rehberi

## ⚡ 5 Dakikada Firebase Yapılandırması

### 1️⃣ Firebase Projesi Oluşturma

1. **Firebase Console'a gidin**: https://console.firebase.google.com/
2. **"Add project"** (Proje Ekle) butonuna tıklayın
3. Proje adını girin: `online-market-app` (veya istediğiniz isim)
4. Google Analytics'i **atlayabilirsiniz** (isteğe bağlı)
5. **"Create project"** (Proje Oluştur) butonuna tıklayın
6. Birkaç saniye bekleyin, proje oluşturulacak

---

### 2️⃣ Web Uygulaması Ekleme

1. Proje oluşturulduktan sonra, ana sayfada **"Web" (</>)** ikonuna tıklayın
2. Uygulama adını girin: `Online Market App`
3. **"Register app"** (Uygulamayı Kaydet) butonuna tıklayın
4. Açılan pencerede **yapılandırma bilgilerini kopyalayın**:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",           // ← Burayı kopyala
  authDomain: "...",              // ← Burayı kopyala
  projectId: "...",               // ← Burayı kopyala
  storageBucket: "...",           // ← Burayı kopyala
  messagingSenderId: "...",       // ← Burayı kopyala
  appId: "..."                    // ← Burayı kopyala
}
```

5. **"Continue to console"** butonuna tıklayın

---

### 3️⃣ Yapılandırmayı Projeye Ekleme

1. Projenizde `src/firebase/config.js` dosyasını açın
2. Firebase Console'dan kopyaladığınız bilgileri `firebaseConfig` objesine yapıştırın
3. **Dosyayı kaydedin** (Ctrl+S)

**Örnek:**
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyBvOkBvqLirjKGhiE-example",
  authDomain: "online-market-app.firebaseapp.com",
  projectId: "online-market-app",
  storageBucket: "online-market-app.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abc123def456"
};
```

---

### 4️⃣ Authentication'ı Etkinleştirme

1. Firebase Console'da sol menüden **"Authentication"** seçin
2. **"Get started"** (Başlayın) butonuna tıklayın
3. **"Sign-in method"** (Giriş yöntemi) sekmesine gidin
4. **"Email/Password"** satırını bulun ve tıklayın
5. **"Enable"** (Etkinleştir) toggle'ını açın
6. **"Save"** (Kaydet) butonuna tıklayın

---

### 5️⃣ Firestore Database'i Etkinleştirme

1. Sol menüden **"Firestore Database"** seçin
2. **"Create database"** (Veritabanı oluştur) butonuna tıklayın
3. **"Start in test mode"** (Test modunda başlat) seçin
4. Veritabanı konumunu seçin (örn: `europe-west3` veya `europe-west1`)
5. **"Enable"** (Etkinleştir) butonuna tıklayın

⚠️ **NOT:** Test mode'da herkes veritabanına erişebilir. Production'a geçmeden önce Security Rules'ı güncelleyin!

---

### 6️⃣ Storage'ı Etkinleştirme (Opsiyonel - Ürün Görselleri İçin)

1. Sol menüden **"Storage"** seçin
2. **"Get started"** butonuna tıklayın
3. Security rules'u kabul edin (test mode)
4. Bir konum seçin
5. **"Done"** butonuna tıklayın

---

### 7️⃣ İlk Admin Kullanıcı Oluşturma

1. Uygulamada kayıt olun (admin rolü seçerek)
2. Firebase Console > **Firestore Database** > **users** koleksiyonuna gidin
3. Oluşturduğunuz kullanıcı dokümanını bulun
4. **"role"** alanını **"admin"** olarak güncelleyin

**veya**

Firestore'da direkt olarak ekleyin:
- Collection: `users`
- Document ID: (kendi belirlediğiniz bir ID veya otomatik)
- Alanlar:
  - `email` (string): admin@example.com
  - `role` (string): admin
  - `name` (string): Admin User
  - `createdAt` (timestamp): şu anki zaman

---

### ✅ Kurulum Tamamlandı!

Artık uygulamanızı çalıştırabilirsiniz:

```bash
npm run dev
```

---

## 🔒 Security Rules (Production İçin)

Test aşamasından sonra Firestore Security Rules'ı güncelleyin. Detaylar için `FIREBASE_SETUP.md` dosyasına bakın.

---

## 📋 Kontrol Listesi

- [ ] Firebase projesi oluşturuldu
- [ ] Web uygulaması eklendi
- [ ] `src/firebase/config.js` dosyası güncellendi
- [ ] Authentication etkinleştirildi (Email/Password)
- [ ] Firestore Database oluşturuldu
- [ ] Storage etkinleştirildi (opsiyonel)
- [ ] İlk admin kullanıcı oluşturuldu

---

## ❓ Sorun mu yaşıyorsunuz?

- `FIREBASE_SETUP.md` dosyasında detaylı bilgiler var
- Firebase Console'da proje ayarlarını kontrol edin
- Browser console'da hata mesajlarını kontrol edin

