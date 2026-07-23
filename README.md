# Seyir Defteri — Selim & Cenk

Atina–Paros tatili için gerçek zamanlı senkron harcama takip uygulaması.
Selim veya Cenk hangi cihazdan harcama girerse girsin, diğerinde anında görünür (Firebase Firestore ile).

## 1. Firebase projesi oluştur (ücretsiz)

1. https://console.firebase.google.com adresine git, Google hesabınla giriş yap.
2. **"Proje ekle"** → bir isim ver (örn. `tatil-hesabi`) → devam et → Google Analytics'i kapatabilirsin → **Proje oluştur**.
3. Sol menüden **Build → Firestore Database** → **Veritabanı oluştur**.
   - Konum seç (herhangi biri olur, örn. `eur3 (europe-west)`).
   - **Test modunda başlat**'ı seç (30 gün boyunca herkese açık okuma/yazma — bu küçük, 2 kişilik kullanım için yeterli ve pratik).
4. Sol üstteki dişli ikonu → **Proje ayarları** → aşağı kaydır → **"Web uygulaması ekle"** (</> simgesi).
   - Bir takma ad ver (örn. `tatil-hesabi-web`), Firebase Hosting'i işaretlemene gerek yok.
   - Karşına çıkan `firebaseConfig` nesnesini kopyala.

## 2. Config'i dosyaya yapıştır

`index.html` içinde şu bölümü bulup kendi bilgilerinle değiştir:

```js
const firebaseConfig = {
  apiKey: "BURAYA_YAPISTIR",
  authDomain: "BURAYA_YAPISTIR.firebaseapp.com",
  projectId: "BURAYA_YAPISTIR",
  storageBucket: "BURAYA_YAPISTIR.appspot.com",
  messagingSenderId: "BURAYA_YAPISTIR",
  appId: "BURAYA_YAPISTIR"
};
```

## 3. GitHub'a yükle ve yayınla

1. GitHub'da yeni repo oluştur (örn. `tatil-hesabi`).
2. `index.html` dosyasını repoya yükle.
3. **Settings → Pages** → "Deploy from a branch" → `main` / `root` → kaydet.
4. Birkaç dakika içinde `https://KULLANICI_ADIN.github.io/tatil-hesabi/` adresinde canlı olur. Linki Selim ve Cenk'e gönder — ikisi de aynı veriyi görür.

## Güvenlik notu

Test modu, veritabanına linki/proje bilgilerini bilen herkesin okuma-yazma yapmasına izin verir — 30 gün sonra otomatik kapanır. Sadece siz ikinizin kullanacağı, hassas olmayan bir tatil hesaplaşması için bu yeterli. Daha uzun süreli veya daha güvenli kullanım istersen, Firestore kurallarını daraltıp basit bir şifre/kod kontrolü eklenebilir — istersen onu da ayarlarım.
