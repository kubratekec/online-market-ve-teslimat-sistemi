# Firebase Kurulum Rehberi

## 1. Firebase Projesi Oluşturma

1. [Firebase Console](https://console.firebase.google.com/)'a gidin
2. "Add project" butonuna tıklayın
3. Proje adını girin ve "Continue" butonuna tıklayın
4. Google Analytics'i isteğe bağlı olarak etkinleştirin
5. "Create project" butonuna tıklayın

## 2. Authentication Kurulumu

1. Sol menüden "Authentication" seçin
2. "Get started" butonuna tıklayın
3. "Sign-in method" sekmesine gidin
4. "Email/Password" seçeneğini etkinleştirin
5. "Enable" butonuna tıklayın ve kaydedin

## 3. Firestore Database Kurulumu

1. Sol menüden "Firestore Database" seçin
2. "Create database" butonuna tıklayın
3. "Start in test mode" seçeneğini seçin (geliştirme için)
4. Bir konum seçin (örn: europe-west3)
5. "Enable" butonuna tıklayın

### Firestore Security Rules

Geliştirme aşamasında test mode kullanabilirsiniz. Production için aşağıdaki kuralları kullanın:

```javascript
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
```

## 4. Web App Yapılandırması

1. Sol menüden proje ayarlarına (⚙️) gidin
2. "Project settings" seçin
3. Aşağı kaydırın ve "Your apps" bölümünde web simgesine (</>) tıklayın
4. App nickname girin ve "Register app" butonuna tıklayın
5. Firebase yapılandırma bilgilerini kopyalayın
6. `src/firebase/config.js` dosyasındaki `firebaseConfig` objesini bu bilgilerle güncelleyin

## 5. Storage (Opsiyonel - Ürün Görselleri İçin)

1. Sol menüden "Storage" seçin
2. "Get started" butonuna tıklayın
3. Security rules'u kabul edin
4. Bir konum seçin
5. "Done" butonuna tıklayın

## 6. İlk Admin Kullanıcı Oluşturma

1. Uygulamada kayıt olun (admin rolü ile)
2. Firebase Console > Firestore Database > users koleksiyonuna gidin
3. Oluşturduğunuz kullanıcı dokümanını bulun
4. "role" alanını "admin" olarak güncelleyin

## 7. İlk Market Oluşturma (Test İçin)

Firestore'da `stores` koleksiyonuna bir test market ekleyebilirsiniz:

```javascript
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
```

## Koleksiyon Yapısı

### users
- email (string)
- role (string): "customer", "storeOwner", "admin"
- name (string)
- phone (string)
- address (string)
- createdAt (timestamp)

### stores
- name (string)
- address (string)
- district (string)
- phone (string)
- ownerId (string)
- workingHours (map)

### products
- name (string)
- price (number)
- unit (string): "adet", "kg", "gram", "litre"
- category (string)
- subcategory (string)
- storeId (string)
- image (string, optional)

### orders
- userId (string)
- storeId (string)
- items (array)
- totalPrice (number)
- deliveryDate (string)
- deliveryTimeSlot (string)
- address (string)
- phone (string)
- status (string)
- createdAt (timestamp)
- paymentStatus (string)

### carts
- userId (string)
- storeId (string)
- items (array)
- updatedAt (timestamp)

## Notlar

- Development aşamasında Firestore rules'ları test mode'da bırakabilirsiniz
- Production'a geçmeden önce security rules'ları mutlaka güncelleyin
- Storage kullanmıyorsanız, ürün görselleri için URL kullanabilirsiniz
- İlk admin kullanıcıyı manuel olarak Firestore'da oluşturmanız gerekebilir

