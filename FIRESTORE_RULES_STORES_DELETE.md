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

