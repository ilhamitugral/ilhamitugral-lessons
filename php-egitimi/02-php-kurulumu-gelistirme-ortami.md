### 🔹 PHP Dosyaları Nasıl Çalışır?

PHP dosyaları `.php` uzantılıdır ve tarayıcıda doğrudan çalışmaz. Sunucu tarafında işlenip tarayıcıya **HTML çıktısı** gönderilir.

Bu nedenle PHP ile çalışmak için bir **yerel sunucu ortamına** ihtiyacımız vardır.

---

### 🔹 Yerel Sunucu Kurulumu

PHP kodlarını bilgisayarımızda çalıştırmak için Apache + PHP + MySQL gibi bileşenleri içeren paketler kullanılır.

#### 💻 Windows için:

* **XAMPP** – En popüler çözümlerden biri
  🔗 [https://www.apachefriends.org/index.html](https://www.apachefriends.org/index.html)

#### 🍏 macOS için:

* **MAMP** – Mac kullanıcıları için ideal
  🔗 [https://www.mamp.info/](https://www.mamp.info/)

#### 🐧 Linux için:

* Paket yöneticisi ile kurulum:

```bash
sudo apt update
sudo apt install apache2 php mysql-server
```

---

### 🔹 XAMPP Kurulumu (Windows Örneği)

1. [XAMPP İndir](https://www.apachefriends.org/index.html) ve yükle
2. Kurulumdan sonra **XAMPP Control Panel**'i aç
3. **Apache** ve **MySQL** servislerini başlat
4. Tarayıcında `http://localhost` adresine git

> Artık yerel sunucun çalışıyor!

---

### 📁 Htdocs Klasörü

XAMPP kurulumu sonrasında PHP dosyalarını şu klasöre koyman gerekir:

```
C:\xampp\htdocs
```

> Bu klasöre koyduğun dosyaları `http://localhost/dosya_adi.php` şeklinde çalıştırabilirsin.

---

### 📝 İlk PHP Dosyası

1. `C:\xampp\htdocs` içine `merhaba.php` dosyasını oluştur
2. İçine şu kodu yaz:

```php
<?php
echo "PHP başarılı şekilde çalışıyor!";
?>
```

3. Tarayıcıdan çalıştır:
   `http://localhost/merhaba.php`

Eğer bu yazıyı görüyorsan her şey doğru kurulmuş demektir ✅

---

### 🔍 Kurulumda Sık Karşılaşılan Sorunlar

| Sorun                    | Çözüm                                                 |
| ------------------------ | ----------------------------------------------------- |
| Apache başlamıyor        | Skype gibi port 80 kullanan uygulamaları kapat        |
| PHP çalışmıyor           | Dosya uzantısının `.php` olduğundan emin ol           |
| Tarayıcıda kod görünüyor | PHP dosyasını `htdocs` klasörüne koymamış olabilirsin |

---

### 🧠 Özetle:

> PHP dosyalarının çalışabilmesi için bir yerel sunucu gerekir. XAMPP gibi araçlar, hızlı ve kolay kurulum sağlar. İlk PHP dosyanı yazarak kurulumu test edebilirsin.