# 🚀 Hızlı Başlangıç - Test Kullanıcıları Oluşturma

## Test Kullanıcılarını Oluşturmak İçin:

### Yöntem 1: Web Sayfası (ÖNERİLEN - En Kolay)

1. **Uygulamayı başlatın:**
   ```bash
   npm run dev
   ```

2. **Tarayıcıda şu adrese gidin:**
   ```
   http://localhost:5173/create-users
   ```

3. **"Tüm Kullanıcıları Oluştur" butonuna tıklayın**

4. **Sonuçları bekleyin** (10-15 saniye)

5. **Artık giriş yapabilirsiniz!**

---

## 📋 Oluşturulacak Kullanıcılar

| Rol | Email | Şifre |
|-----|-------|-------|
| Admin | admin@market.com | admin123 |
| Market Sahibi 1 | market1@market.com | market123 |
| Market Sahibi 2 | market2@market.com | market123 |
| Müşteri 1 | musteri1@market.com | musteri123 |
| Müşteri 2 | musteri2@market.com | musteri123 |
| Müşteri 3 | musteri3@market.com | musteri123 |

---

## ✅ Giriş Yapma

1. `http://localhost:5173/login` adresine gidin
2. Yukarıdaki email ve şifrelerden birini kullanın
3. Giriş yapın!

---

## ⚠️ ÖNEMLİ: Önce Kontrol Edin

Kullanıcıları oluşturmadan önce şunların hazır olduğundan emin olun:

- [ ] Firebase Authentication etkinleştirildi (Email/Password)
- [ ] Firestore Database oluşturuldu
- [ ] `npm run dev` ile uygulama çalışıyor

**Sorun mu yaşıyorsunuz?** → `TROUBLESHOOTING.md` dosyasına bakın.

