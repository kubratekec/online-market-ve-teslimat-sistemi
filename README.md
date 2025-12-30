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
