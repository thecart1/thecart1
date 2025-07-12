# INSTALL

* This is for __new installation only__
* These instructions are for a manual installation using FTP, cPanel or other web hosting Control Panel.


If you are __upgrading your existing cart__, be sure to read the [upgrade instructions](UPGRADE.md) instead

## Windows Install

1. Upload all the files and folders to your server from the "Upload" folder. This can be to anywhere of your choice. e.g. ```/wwwroot/store``` or ```/wwwroot```
2. Rename ```config-dist.php``` to ```config.php``` and ```admin/config-dist.php``` to ```admin/config.php```
3. For Windows make sure the following folders and files permissions allow Read and Write.

		config.php
		admin/config.php

4. Make sure you have installed a MySQL Database which has a user assigned to it
	* do not use your ```root``` username and ```root``` password
5. You should be taken to the installer page. Follow the on screen instructions.
6. After successful install, delete the ```/install/``` directory.

7. Make sure the following extensions are enabled in php.ini:

extension=curl;
extension=gd;
extension=zip;

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

## Going live
When your site is ready to go live open file ```system/config/default.php``` 

**Find:**

`$_['error_display'] = true;`

**Replace with:**

`$_['error_display'] = false;`
