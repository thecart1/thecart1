# INSTALL

## OpenCart’ı İndir

* Resmi site: [https://github.com/opencart/opencart](https://github.com/opencart/opencart/releases/tag/3.0.3.8)
* “Download” bölümünden en son sürümü indir (.zip dosyası)
* Zip dosyasını aç, içindeki `upload` klasörünü çıkar

* This is for __new installation only__
* These instructions are for a manual installation using FTP, cPanel or other web hosting Control Panel.

## Windows Install

1. Upload all the files and folders to your server from the "Upload" folder. This can be to anywhere of your choice. e.g. ```/wwwroot/opencart``` or ```/wwwroot```
2. Rename ```config-dist.php``` to ```config.php``` and ```admin/config-dist.php``` to ```admin/config.php```
3. For Windows make sure the following folders and files permissions allow Read and Write.

		config.php
		admin/config.php

4. phpMyAdmin ya da terminal üzerinden bir MySQL veritabanı oluştur:
	* Veritabanı adı: `opencart_db` Kullanıcı: `root` Şifre: (boş bırak – yerel geliştirme için)
5. Make sure you have installed a MySQL Database which has a user assigned to it
	* do not use your ```root``` username and ```root``` password
6. Tarayıcıda şu adrese git: http://localhost/opencart/
	* Kurulum ekranı açılır, adımları takip et:
7. Lisans sözleşmesini kabul et → Devam
8. You should be taken to the installer page. Follow the on screen instructions.
9. `install/` klasörünü sil
	* `config.php` ve `admin/config.php` dosyalarını aç, klasör yollarını ve URL’leri kontrol et/düzelt:

	```php
	// config.php (örnek)
	define('HTTP_SERVER', 'http://localhost/opencart/');
	define('HTTPS_SERVER', 'http://localhost/opencart/');
	define('DIR_APPLICATION', 'C:/xampp/htdocs/opencart/catalog/');
	define('DIR_SYSTEM', 'C:/xampp/htdocs/opencart/system/');
	// ...
	```

10. Make sure the following extensions are enabled in php.ini:

extension=curl;
extension=gd;
extension=zip;

## Veritabanı Ayarları

1. Database Host: `localhost`
2. Username: `root`
3. Password: (boş bırak)
4. Database Name: `opencart_db`

## Yönetici Hesabı Oluştur

1. Kullanıcı Adı: `admin`
2. Şifre: `admin123` (güvenlik için sonradan değiştirin)
3. E-posta: `admin@example.com`

## Local Install

There are many all-in-one web servers out there and most of them should work with OpenCart out of the box.

Some examples...

* https://www.apachefriends.org/
* http://www.ampps.com/
* http://www.usbwebserver.net
* http://www.wampserver.com/en/

## Notes

Godaddy Issues

If your hosting on godaddy you might need to rename the ```php.ini``` to ```user.ini```

It seems godaddy has started changing the industry standard names of files.

----------------------------

## ⚙️ Örnek Sorunlar ve Çözümler

| Sorun                | Çözüm                                                            |
| -------------------- | ---------------------------------------------------------------- |
| `mod_rewrite` hatası | Apache `mod_rewrite` aktif mi? `.htaccess` dosyası doğru mu?     |
| Beyaz ekran          | PHP hata raporlamasını aç (`php.ini` içinde `display_errors=On`) |
| Resim yüklenmiyor    | `/image` klasör izinlerini kontrol et (örneğin 755 ya da 775)    |

## Going live
When your site is ready to go live open file ```system/config/default.php``` 

**Find:**

`$_['error_display'] = true;`

**Replace with:**

`$_['error_display'] = false;`


## Yönetici Paneline Giriş

* Adres: `http://localhost/opencart/admin`
* Kullanıcı: `admin`
* Şifre: `admin123`


### 🧪 Kurulumu Test Et

* Ürün eklemeyi, kategorileri, temayı ve ödeme yöntemlerini test edebilirsin.
* Eklenti kurmak, temayı değiştirmek için "Extensions" menüsünü kullan.

