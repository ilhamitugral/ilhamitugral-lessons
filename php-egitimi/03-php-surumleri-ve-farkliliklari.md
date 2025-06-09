### 🧩 Giriş: Neden Sürümler Önemlidir?

PHP, zaman içinde hem **performans** hem de **özellikler** bakımından büyük evrim geçirmiştir. Her sürümle birlikte programcıların eline daha güçlü araçlar verilmiş, yazılım mimarileri daha sağlam hale gelmiştir. Bu derste, PHP’nin 5.x, 7.x ve 8.x sürümlerini karşılaştırmalı olarak inceleyeceğiz.

---

## 🕰️ PHP 5.x Serisi (2004 - 2015)

### ⚙️ Temel Özellikler:

* **Gerçek nesne yönelimli programlama (OOP) desteği** geldi.
* `try/catch` ile istisna yönetimi kullanılabilir hale geldi.
* **PDO (PHP Data Objects)** ile güvenli veritabanı bağlantıları sağlandı.
* `interface`, `abstract`, `visibility` (public, private, protected) kavramları tanıtıldı.
* `__autoload()` fonksiyonu ile sınıf yükleme kolaylaştırıldı.

### ⛔️ Eksiklikler:

* Performans düşüktü.
* Type safety (tip güvenliği) zayıftı.
* Modern framework’lerde yavaşlamaya neden oluyordu.

---

## 🚀 PHP 7.x Serisi (2015 - 2020)

### ⚡ Performans Devrimi:

* Yeni **Zend Engine 3.0** ile PHP 5'e kıyasla 2–3 kat daha hızlı.
* Bellek kullanımı optimize edildi.

### 🆕 Yeni Özellikler:

* **Scalar type declarations**: `function add(int $a, int $b): int`
* **Return type declarations**
* **Null coalescing operator (`??`)**
* **Spaceship operator (`<=>`)**
* **Anonymous classes**
* **Group use declarations** (`use A\{B, C, D};`)
* **Throwable** ve yeni hata sınıfları (`Error`, `Exception`)

### 🔐 Güvenlik Geliştirmeleri:

* `random_bytes()`, `random_int()` gibi kriptografik güvenli fonksiyonlar geldi.
* Gelişmiş password hashing (`password_hash`, `password_verify`)

---

## ⚙️ PHP 8.x Serisi (2020 - Günümüz)

### 🚀 Performans:

* **JIT (Just-In-Time Compilation)**: Derleme zamanında bytecode → makine koduna çevrilir.
* Mikroservis yapılarında PHP'nin Node.js'e rakip olmasını sağladı.

### 🆕 Öne Çıkan Özellikler:

#### ✅ PHP 8.0

* **Constructor Property Promotion**

  ```php
  class User {
      public function __construct(private string $name) {}
  }
  ```
* **Match Expression**

  ```php
  match($statusCode) {
      200 => 'OK',
      404 => 'Not Found',
  }
  ```
* **Named Arguments**

  ```php
  foo(height: 100, width: 200);
  ```
* **Union Types**

  ```php
  function log(int|string $value) {}
  ```
* **Attributes (Annotations)**

  ```php
  #[ORM\Entity]
  class Product {}
  ```

#### ✅ PHP 8.1

* **Readonly properties**
* **Enums** (çok istenen bir özellik!)
* **First-class callables**
* **`never` return type**

#### ✅ PHP 8.2

* `readonly` class
* `disjunctive normal form` types (DNF)
* Yeni deprecated uyarılar

---

## 🔍 Karşılaştırmalı Tablo

| Özellik / Sürüm | PHP 5.x | PHP 7.x | PHP 8.x |
| - | - | - | - |
| Yayın Tarihi | 2004 | 2015 | 2020                     |
| Performans | Düşük | Yüksek | Çok Yüksek (JIT ile)     |
| Tip Belirtimi | Yok | Kısmen (Scalar types) | Tam (Union, Mixed, etc.) |
| JIT Desteği | ❌ | ❌ | ✅ |
| Enums | ❌       | ❌ | ✅ (8.1+) |
| Named Arguments | ❌ | ❌ | ✅ |
| Match Expression | ❌ | ❌ | ✅ |
| Attributes | ❌ | ❌ | ✅ |
| Modern Framework Uyumu | Sınırlı | Laravel 5.x-6.x | Laravel 8-11 |

---

## 🧠 Ne Öğrendik?

* PHP 5, dilin olgunlaştığı ilk dönemdir ancak artık **desteklenmemektedir.**
* PHP 7 ile birlikte **gerçek bir performans artışı** yaşanmıştır ve çoğu projede hâlen kullanılmaktadır.
* PHP 8 ile dil, **modern yazılım mimarilerine uyumlu hale gelmiş**, neredeyse TypeScript veya Java kadar güçlü hale gelmiştir.

---

## 🧭 Hangi Sürümle Başlamalı?

* **Yeni başlayanlar için:** PHP 8.1 veya PHP 8.2 önerilir.
* **Laravel kullanacaklar için:** Laravel 10 ve sonrası PHP 8.1+ gerektirir.
* **Projeni yayına alacaksan:** Hosting’in PHP 8 desteklediğinden emin ol.
