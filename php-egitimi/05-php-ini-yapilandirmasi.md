### 🧠 `php.ini` Nedir?

`php.ini`, PHP çalıştırıldığında yüklenen **ana konfigürasyon dosyasıdır**. PHP’nin davranışlarını ve ortam ayarlarını belirler:

* Hangi eklentilerin yükleneceği
* Bellek sınırı
* Maksimum dosya boyutu
* Hata gösterim düzeyi
* Zaman dilimi (timezone)
  ve daha fazlası…

---

## 🔍 Nerede Bulunur?

**XAMPP Kullanıcıları için:**

```
C:\xampp\php\php.ini
```

**Linux/Mac Terminal:**

```bash
php --ini
```

**Çıktı:**

```
Loaded Configuration File => /etc/php/8.2/apache2/php.ini
```

**PHP'de Kodla Gösterim:**

```php
phpinfo(); // Çalıştır ve "Loaded Configuration File" satırını kontrol et.
```

---

## 🔧 Sık Değiştirilen `php.ini` Ayarları

| Ayar Adı | Açıklama | Örnek Değer |
| - | - | - |
| `display_errors` | Hata mesajları tarayıcıda gösterilsin mi? | `On` / `Off` |
| `error_reporting` | Hangi hata seviyeleri gösterilsin? | `E_ALL & ~E_NOTICE` |
| `memory_limit` | Maksimum bellek kullanımı | `128M`, `512M` |
| `max_execution_time` | Bir script’in çalışabileceği maksimum süre (saniye) | `30` |
| `post_max_size` | POST verilerinin maksimum boyutu | `8M`, `100M` |
| `upload_max_filesize` | Dosya yüklemede maksimum boyut | `2M`, `100M` |
| `date.timezone` | Varsayılan zaman dilimi | `Europe/Istanbul` |
| `session.gc_maxlifetime` | Oturum süresi (saniye) | `1440` |
| `file_uploads` | Dosya yükleme izinli mi? | `On` / `Off` |
| `extension_dir` | Eklenti (.dll/.so) klasörünün yolu | `ext/`, `/usr/lib/php/extensions/...` |
| `extension=` | Yüklenecek PHP modülleri | `extension=pdo_mysql` |

---

## 📁 php.ini’yi Düzenleme Adımları

### ✏️ Windows/XAMPP için:

1. `C:\xampp\php\php.ini` dosyasını aç (Notepad++, VS Code önerilir).

2. Satır başındaki `;` yorum anlamına gelir → kaldırarak aktif edebilirsin.

3. Örnek:

```ini
;extension=pdo_mysql   ; bu pasif
extension=pdo_mysql    ; bu aktif
```

4. Değişiklik sonrası Apache’yi **yeniden başlat**.

### 🐧 Linux İçin:

```bash
sudo nano /etc/php/8.2/apache2/php.ini
# veya CLI kullanıyorsan
sudo nano /etc/php/8.2/cli/php.ini
```

Arama yapmak için: `CTRL + W` → ayar adını yaz (örneğin `upload_max_filesize`)

---

## 📎 Hata Ayıklama İçin Önerilen Ayarlar (Geliştirme Ortamı)

```ini
display_errors = On
display_startup_errors = On
error_reporting = E_ALL
log_errors = On
```

> ⚠️ **Üretim ortamında `display_errors` kesinlikle kapalı olmalıdır!**

---

## 🧪 Uygulama Örneği

1. `php.ini` içinde:

   ```ini
   date.timezone = Europe/Istanbul
   upload_max_filesize = 100M
   post_max_size = 100M
   ```

2. Ardından terminalde kontrol:

   ```bash
   php -i | grep upload_max_filesize
   ```

3. Tarayıcıdan da `phpinfo()` ile kontrol edebilirsin.

---

## 🛠️ php.ini Alternatifleri

* Proje bazlı `.user.ini` dosyası kullanarak yerel ayarlar yapılabilir (shared hostinglerde kullanılır).
* Komut satırında geçici olarak override edebilirsin:

  ```bash
  php -d memory_limit=512M script.php
  ```

---

## 🎓 Ne Öğrendik?

* `php.ini`, PHP davranışlarını kontrol eden temel ayar dosyasıdır.
* Hata ayarları, bellek sınırları, dosya yükleme limitleri gibi birçok parametre buradan yönetilir.
* Geliştirme ve canlı ortamlar için farklı ayar tercih edilmelidir.