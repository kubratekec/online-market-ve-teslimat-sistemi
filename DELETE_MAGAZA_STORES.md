# "Mağaza" İçeren Kayıtları Silme - Browser Console Scripti

Eğer admin panelindeki buton çalışmıyorsa, bu scripti tarayıcı console'unda çalıştırabilirsiniz.

## Nasıl Kullanılır:

1. Admin Panel sayfasında F12 tuşuna basın
2. **Console** sekmesine gidin
3. Aşağıdaki kodu tamamen kopyalayıp console'a yapıştırın
4. Enter'a basın
5. Onay penceresinde "OK" deyin
6. Script tüm "mağaza" içeren kayıtları silecek

## Script:

```javascript
(async function deleteAllMagazaStores() {
  // Firebase'i import et
  const { initializeApp } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-app.js');
  const { getFirestore, collection, getDocs, doc, deleteDoc } = await import('https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore.js');
  
  // Firebase config - src/firebase/config.js dosyasındaki bilgileri buraya kopyalayın
  const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "your-messaging-sender-id",
    appId: "your-app-id",
  };
  
  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  
  console.log('🚀 "Mağaza" içeren kayıtlar siliniyor...\n');
  
  try {
    // Tüm marketleri al
    const querySnapshot = await getDocs(collection(db, 'stores'));
    const allStores = [];
    querySnapshot.forEach((doc) => {
      allStores.push({ id: doc.id, ...doc.data() });
    });
    
    console.log(`📊 Toplam ${allStores.length} adet market bulundu\n`);
    
    // "Mağaza" içeren kayıtları filtrele
    const storesToDelete = allStores.filter(store => {
      const name = (store.name || '').toLowerCase();
      return name.includes('mağaza');
    });
    
    console.log(`🎯 ${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu\n`);
    
    if (storesToDelete.length === 0) {
      console.log('✅ Silinecek kayıt bulunamadı');
      return;
    }
    
    // Örnekleri göster
    console.log('Silinecek kayıtlar (ilk 10):');
    storesToDelete.slice(0, 10).forEach((store, index) => {
      console.log(`${index + 1}. ${store.name} (ID: ${store.id})`);
    });
    if (storesToDelete.length > 10) {
      console.log(`... ve ${storesToDelete.length - 10} adet daha\n`);
    }
    
    // Onay iste
    const confirmDelete = confirm(
      `${storesToDelete.length} adet "Mağaza" içeren kayıt bulundu.\n\nHepsini silmek istediğinize emin misiniz?\n\nBu işlem geri alınamaz!`
    );
    
    if (!confirmDelete) {
      console.log('❌ İşlem iptal edildi');
      return;
    }
    
    console.log('🗑️ Silme işlemi başlıyor...\n');
    
    let deletedCount = 0;
    let errorCount = 0;
    
    // Her kayıt için silme işlemini gerçekleştir
    for (const store of storesToDelete) {
      try {
        await deleteDoc(doc(db, 'stores', store.id));
        deletedCount++;
        if (deletedCount % 100 === 0) {
          console.log(`✅ ${deletedCount} adet kayıt silindi...`);
        }
      } catch (error) {
        console.error(`❌ Hata (${store.name}):`, error.message);
        errorCount++;
      }
    }
    
    console.log('\n' + '='.repeat(50));
    console.log(`\n✅ ${deletedCount} adet kayıt başarıyla silindi`);
    if (errorCount > 0) {
      console.log(`❌ ${errorCount} adet kayıt silinirken hata oluştu`);
    }
    console.log('='.repeat(50) + '\n');
    
    // Sayfayı yenile
    console.log('🔄 Sayfa yenileniyor...');
    setTimeout(() => {
      window.location.reload();
    }, 2000);
    
  } catch (error) {
    console.error('❌ Kritik hata:', error);
    alert('Hata oluştu: ' + error.message);
  }
})();
```

## Alternatif: Sayfada Yenile Butonu

Admin panelinde "🔄 Yenile" butonuna tıklayarak listeyi manuel olarak yenileyebilirsiniz.

