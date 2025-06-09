### 🎯 Hedef:

Bu derste PHP geliştirme ortamını kurmanın 4 farklı yöntemini öğreneceksin:

1. XAMPP (Windows & Linux)
2. MAMP (macOS)
3. Docker (her platform için ileri düzey)
4. Manuel kurulum (sadece PHP CLI veya özel yapılandırma isteyenler için)

---

## 🧰 1. XAMPP ile Kurulum (Windows / Linux İçin Kolay Yöntem)

### 🔹 Nedir?

XAMPP; Apache + MySQL (MariaDB) + PHP + Perl içeren, tek tıklamayla kurulan bir pakettir.

### 🔧 Kurulum Adımları:

1. [https://www.apachefriends.org](https://www.apachefriends.org) adresine git.
2. İşletim sistemine uygun XAMPP paketini indir (Windows için `xampp-windows-x64-x.x.x.exe`).
3. Kurulum sırasında PHP, Apache ve MySQL kutucuklarını seç.
4. Kurulumu tamamla ve **XAMPP Control Panel**'den Apache + MySQL servislerini başlat.
5. Tarayıcıya `http://localhost` yazarak kontrol et.

### 🗂️ PHP Dosyaları Nereye Yazılır?

* `C:\xampp\htdocs` dizinine `.php` dosyalarını koy.
* Örnek dosya:

  ```php
  <?php echo "Merhaba, PHP!"; ?>
  ```

---

## 🍏 2. MAMP ile Kurulum (macOS İçin Kolay Yöntem)

### 🔹 Nedir?

MAMP, özellikle macOS kullanıcıları için hazırlanmış bir Apache + MySQL + PHP paketidir.

### 🔧 Kurulum Adımları:

1. [https://www.mamp.info](https://www.mamp.info) adresine git.
2. MAMP Free sürümünü indir.
3. Kurulumu tamamla ve uygulamayı aç.
4. **Start Servers** diyerek Apache ve MySQL başlat.
5. Tarayıcıdan `http://localhost:8888` adresine gir.

### 🗂️ PHP Dosyaları Nereye Yazılır?

* `Applications/MAMP/htdocs` klasörüne `.php` dosyası koy.
* `http://localhost:8888/deneme.php` gibi çalıştırılır.

---

## 🐳 3. Docker ile Kurulum (Platform Bağımsız ve Gelişmiş Kullanım)

### 🔹 Nedir?

Docker, uygulamaları sanal makineler olmadan çalıştırmanı sağlayan bir konteyner teknolojisidir.

### 🧪 Avantajı:

* Her şey izole çalışır.
* Proje bağımlılıkları birbirine karışmaz.
* CI/CD süreçlerinde idealdir.

### 🐳 Dockerfile ile Basit PHP Kurulumu:

```Dockerfile
FROM php:8.2-apache
COPY ./src /var/www/html/
EXPOSE 80
```

### 🔧 Kullanım Adımları:

1. Docker Desktop kur.
2. Projeyi `src` klasörüyle oluştur.
3. Terminal'de:

   ```bash
   docker build -t my-php-app .
   docker run -p 8080:80 my-php-app
   ```
4. Tarayıcıdan `http://localhost:8080` adresine git.

---

## 🔨 4. Manuel PHP Kurulumu (CLI veya Özel Sunucu)

### 📦 PHP CLI (sadece yorumlayıcı):

#### Windows:

1. [https://windows.php.net/download/](https://windows.php.net/download/) adresinden PHP zip dosyasını indir.
2. `C:\php` gibi bir klasöre çıkar.
3. Ortam değişkenlerine (`PATH`) PHP klasörünü ekle.
4. `cmd` aç ve `php -v` komutunu çalıştır.

#### Linux / macOS:

```bash
sudo apt update && sudo apt install php
# veya
brew install php
```

### 🧪 Kontrol:

```bash
php -v
```

### 🧪 İlk Komut Satırı Dosyası:

```bash
echo "<?php echo 'Merhaba CLI';" > test.php
php test.php
```

---

## 📝 Karşılaştırma Tablosu

| Kurulum Türü | Kolaylık | Hedef Kullanıcı | Platform | Avantaj |
| - | - | - | - | - |
| **XAMPP** | ✅ Çok Kolay | Başlangıç | Win/Linux | Her şey hazır gelir |
| **MAMP** | ✅ Çok Kolay | Başlangıç | macOS | macOS için optimize |
| **Docker** | ⚠️ Orta/Zor | Orta/İleri Seviye | Tümü | İzolasyon, otomasyon |
| **Manuel** | ⚠️ Orta | İleri Seviye | Tümü | Hafif yapı, özelleştirilebilir |

---

## 🎓 Ödev / Uygulama

1. Yukarıdaki yöntemlerden birini kullanarak PHP kurulumunu yap.
2. `hello.php` adında bir dosya oluştur:

   ```php
   <?php echo "PHP başarıyla kuruldu!"; ?>
   ```
3. Tarayıcında çalıştır ve ekranda mesajı gördüğünde ilk PHP dosyan başarıyla çalışmış olacak!
