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

