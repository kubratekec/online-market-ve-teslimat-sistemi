# Firebase Deploy Adımları

## 📋 Web Sitesini Görüntüleme

### Adım 1: Siteyi Aç
1. Tarayıcınızı açın (Chrome, Firefox, Edge vb.)
2. Adres çubuğuna şu URL'yi yazın ve Enter'a basın:
   ```
   https://online-market-randevu-sistemi.web.app
   ```
   VEYA
   ```
   https://online-market-randevu-sistemi.firebaseapp.com
   ```

3. Site açılırsa ✅ başarılı!
   - Login/Register sayfası görünmeli
   - "Online Market" başlığı görünmeli

4. Eğer Firebase'in varsayılan sayfası görünüyorsa:
   - `Ctrl + Shift + R` (Windows) veya `Cmd + Shift + R` (Mac) ile hard refresh yapın
   - Veya tarayıcı cache'ini temizleyin

---

## 🔧 Firebase Console Erişimi (Opsiyonel - Site Çalışıyorsa Gerekmez)

### Adım 1: Doğru Google Hesabıyla Giriş
1. Chrome'da sağ üst köşedeki profil ikonuna tıklayın
2. `caymazlutfiye3@gmail.com` ile giriş yaptığınızdan emin olun
3. Eğer farklı bir hesap görünüyorsa:
   - Profil ikonuna tıklayın
   - "Farklı bir hesap kullan" seçeneğini seçin
   - `caymazlutfiye3@gmail.com` ile giriş yapın

### Adım 2: Firebase Console'a Git
1. Şu URL'yi açın:
   ```
   https://console.firebase.google.com/project/online-market-randevu-sistemi/overview
   ```

2. Eğer "Bu proje mevcut değil veya onu görüntüleme izniniz yok" hatası görürseniz:
   - Sağ üstteki profil ikonuna tıklayın
   - Doğru hesabı seçin (`caymazlutfiye3@gmail.com`)
   - Sayfayı yenileyin (`F5`)

### Adım 3: MFA (2 Adımlı Doğrulama) Etkinleştirme (Gerekirse)
1. Firebase Console'daki kırmızı uyarı banner'ında "2SV'yi açın" butonuna tıklayın
2. Veya doğrudan: https://myaccount.google.com/security
3. "2 Adımlı Doğrulama" bölümünü bulun
4. "Başlayın" butonuna tıklayın
5. Adımları takip ederek telefon numaranızı ekleyin

---

## 🔄 Yeni Değişikliklerden Sonra Tekrar Deploy Etme

### Adım 1: Kodu Güncelle
1. Kodunuzda değişiklikler yapın
2. Değişiklikleri kaydedin

### Adım 2: Build Et
Terminal'de (PowerShell) şu komutu çalıştırın:
```powershell
cd "online market ve teslimat sistemi\online-market-app"
npm run build
```

### Adım 3: Deploy Et
Build tamamlandıktan sonra:
```powershell
firebase deploy --only hosting
```

### Adım 4: Bekle
Deploy işlemi 1-2 dakika sürebilir. "Deploy complete!" mesajını görünce tamamlanmıştır.

### Adım 5: Test Et
1. Tarayıcıda siteyi açın (https://online-market-randevu-sistemi.web.app)
2. `Ctrl + Shift + R` ile hard refresh yapın
3. Değişikliklerin göründüğünü kontrol edin

---

## ⚠️ Sorun Giderme

### Site açılmıyor / Firebase varsayılan sayfası görünüyor
1. Hard refresh yapın: `Ctrl + Shift + R`
2. Tarayıcı cache'ini temizleyin
3. Gizli pencere modunda açın (Ctrl + Shift + N)
4. Farklı bir tarayıcı deneyin

### Console'a erişemiyorum
1. Doğru Google hesabıyla giriş yaptığınızdan emin olun
2. MFA (2 Adımlı Doğrulama) etkinleştirin
3. Tarayıcıyı kapatıp yeniden açın

### Deploy hatası alıyorum
1. Firebase CLI'nin güncel olduğundan emin olun: `firebase --version`
2. Build'in başarılı olduğundan emin olun: `npm run build`
3. `.firebaserc` dosyasında doğru proje ID'sinin olduğunu kontrol edin

---

## 📍 Önemli URL'ler

- **Canlı Site:** https://online-market-randevu-sistemi.web.app
- **Firebase Console:** https://console.firebase.google.com/project/online-market-randevu-sistemi/overview
- **Hosting Ayarları:** https://console.firebase.google.com/project/online-market-randevu-sistemi/hosting/main

---

## ✅ Hızlı Kontrol Listesi

- [ ] Site URL'sini tarayıcıda açtım
- [ ] Login/Register sayfası görünüyor
- [ ] Hard refresh yaptım (Ctrl + Shift + R)
- [ ] Console'a erişmek için doğru Google hesabıyla giriş yaptım
- [ ] MFA etkinleştirdim (gerekirse)

