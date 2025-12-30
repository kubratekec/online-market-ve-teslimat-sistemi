# Sorun Giderme Rehberi

## 🔴 "Giriş Başarısız" Hatası

### Olası Sebepler ve Çözümler

#### 1. Kullanıcılar Henüz Oluşturulmamış

**Sorun:** Hiçbir kullanıcı oluşturulmamış.

**Çözüm:**
1. `http://localhost:5173/create-users` adresine gidin
2. "Tüm Kullanıcıları Oluştur" butonuna tıklayın
3. Kullanıcılar oluşturulduktan sonra giriş yapmayı deneyin

#### 2. Firebase Authentication Etkin Değil

**Sorun:** Firebase Console'da Email/Password authentication etkinleştirilmemiş.

**Çözüm:**
1. [Firebase Console](https://console.firebase.google.com/) → Projenizi seçin
2. **Authentication** → **Sign-in method** sekmesine gidin
3. **Email/Password** satırını bulun ve tıklayın
4. **Enable** toggle'ını açın
5. **Save** butonuna tıklayın

#### 3. Firestore Database Oluşturulmamış

**Sorun:** Firestore Database henüz oluşturulmamış.

**Çözüm:**
1. Firebase Console → **Firestore Database**
2. **Create database** butonuna tıklayın
3. **Start in test mode** seçin (geliştirme için)
4. Bir konum seçin (örn: `europe-west3`)
5. **Enable** butonuna tıklayın

#### 4. Yanlış Email veya Şifre

**Sorun:** Email veya şifre yanlış girilmiş.

**Çözüm:**
- Test kullanıcıları için doğru bilgileri kullanın:
  - Admin: `admin@market.com` / `admin123`
  - Müşteri: `musteri1@market.com` / `musteri123`
  - Market Sahibi: `market1@market.com` / `market123`

#### 5. Firestore'da users Koleksiyonu Eksik

**Sorun:** Kullanıcı Authentication'da var ama Firestore'da users koleksiyonunda yok.

**Çözüm:**
1. `/create-users` sayfasından kullanıcıları tekrar oluşturun
2. Veya Firebase Console → Firestore Database → **users** koleksiyonunu kontrol edin
3. Eğer kullanıcı yoksa, manuel olarak ekleyin veya `/create-users` sayfasını kullanın

---

## 🔍 Kontrol Listesi

Giriş yapmadan önce şunları kontrol edin:

- [ ] Firebase Authentication etkinleştirildi (Email/Password)
- [ ] Firestore Database oluşturuldu
- [ ] `/create-users` sayfasından kullanıcılar oluşturuldu
- [ ] Browser console'da hata mesajı var mı kontrol edildi
- [ ] Doğru email ve şifre kullanıldı

---

## 🛠️ Detaylı Hata Mesajları

Browser console'u açın (F12) ve hata mesajlarını kontrol edin. Hata mesajları size daha fazla bilgi verecektir.

### Yaygın Hata Kodları

- `auth/user-not-found`: Kullanıcı bulunamadı
- `auth/wrong-password`: Şifre yanlış
- `auth/invalid-email`: Geçersiz email formatı
- `auth/invalid-credential`: Email veya şifre yanlış
- `auth/too-many-requests`: Çok fazla başarısız deneme
- `permission-denied`: Firestore yetki hatası (Security Rules kontrol edin)

---

## 📞 Hızlı Çözüm

En hızlı çözüm:

1. `/create-users` sayfasına gidin
2. "Tüm Kullanıcıları Oluştur" butonuna tıklayın
3. Tüm kullanıcılar başarıyla oluşturulduktan sonra giriş yapın

Eğer hala sorun yaşıyorsanız, browser console'daki hata mesajını kontrol edin.

