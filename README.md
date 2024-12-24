# FinalProjek
Final Projek OS Server &amp; Sistem Admin 

# Keterangan
<b>NAMA    : Muhammad Zidan Manulana</b>

<b>NIM     : 23.83.1022</b>

# Spesifikasi Sistem Operasi
<b>Ubuntu Server 22.04.3</b>

<b>Base Memory 8982MB</b>

<b>RAM 4 GiB (memori sestem)</b>

<b>Prosesor inti ganda 2 GHz</b>

<b>Ruang hard drive 25 GB</b>

<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

# Layanan Server
<a href="#ssh">1. SSH</a> <br>
<a href="#apache">2. apache2</a> <br>
<a href="#data">3. database server mariadb, php, phpmyadmin</a> <br>
<a href="#monitoring">4. netdata</a> <br>
<a href="#nextcloud">5. nextcloud</a> <br>


<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

# Langkagh-langkah

<h2> Update and Upgrade</h2>

- <b>1. Open a terminal and run the following commands:</b>
  - `sudo apt update && sudo apt upgrade -y`

<h2 id="ssh"> OPEN SSH</h2>

- <b>1. Install openssh</b>
  - `sudo apt install openssh-server ufw`
 
- <b>2. Periksa status ssh sudah aktif atau tidak:</b>
  - `sudo service sshd status`
 
- <b>3. Mengecek status UFW (firewall) untuk mengetahui apakah firewall aktif atau tidak</b>
  - `sudo service ufw status`
 
- <b>4. Buka port 22 (port default SSH) di firewall</b>
  - `sudo ufw allow ssh`
 
- <b>5. Mengecek firewall yang sedang digunakan</b>
  - `sudo ufw status`
 
- <b>6. Mengaktifkan UFW sebagai firewall utama pada sistem</b>
  - `sudo ufw enable`
 
- <b>7. Mengecek firewall yang sedang digunakan</b>
  - `sudo ufw status`
 
<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

<h2 id="apache"> Install dan Konfigurasi apache2</h2>

- <b>1. Install apache2</b>
  - `sudo apt install apache2 -y`
 
- <b>2. Periksa status apache</b>
  - `sudo systemctl status apache2`
 
- <b>3. Konfigurasi firewall</b>
  - `sudo ufw allow 'Apache Full'`
 
- <b>4. Cek status</b>
  - `sudo ufw status`
 
- <b>5. Buat direktori untuk situs web</b>
   ```
   sudo mkdir -p /var/www/example.com
   sudo chown -R $USER:$USER /var/www/example.com
   sudo chmod -R 755 /var/www/example.com
   ```
 
- <b>6. Buat file konfigurasi virtual host</b>
  - `sudo nano /etc/apache2/sites-available/example.com.conf`
 
- <b>7. Tambahkan konfigurasi berikut</b>
   ```
    <VirtualHost *:80>
      ServerAdmin admin@example.com
      ServerName example.com
      ServerAlias www.example.com
      DocumentRoot /var/www/example.com
      ErrorLog ${APACHE_LOG_DIR}/error.log
      CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>
   ```

-  <b>8. Aktifkan Virtual Host</b>
  - `sudo a2ensite example.com.conf`
  
-  <b>9. Reload Apache</b>
  - `sudo systemctl reload apache2`

<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

<h2 id="data"> Install dan Konfigurasi mingdb, php, phpmyadmin</h2>

- <b>1. Instalasi MariaDB</b>
  - `sudo apt-get install mariadb-server`
 
- <b>2. enable Paket MariaDB</b>
  - `sudo systemctl enable mariadb`
 
- <b>3. Konfigurasi MariaDB</b>
  - `mysql_secure_installation`

- <b>4. Instalasi Php</b>
  - `sudo apt install php php8.3-common php8.3-cli php8.3-mbstring php8.3-imap php8.3-redis php8.3-snmp php8.3-xml php8.3-zip php8.3-curl php8.3-mysql php8.3-gdr`
 
- <b>5. Konfigurasi Php</b>
  - `cd /var/www/html/`
 
- <b>6. lalu Isi file tersebut dengan</b>
  - `sudo vi info.php`
 
- <b>7. Instalasi MariaDB</b>
```
  <?php
phpinfo();
?>
```
 
- <b>8. Instalasi dan Konfigurasi Phpmyadmin</b>
  - `apt-get install phpmyadmin`
 
- <b>9. lalu Restart Layanan Apache2</b>
  - `systemctl restart apache2`

<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

<h2 id="monitoring"> Install dan Konfigurasi netdata</h2>

- <b>1. Install Netdata</b>
  - `sudo apt install netdata -y`
 
- <b>2. Izinkan Firewall untuk tcp default netdata</b>
  - `sudo ufw allow 19999/tcp`
 
- <b>3. konfigurasi netdata</b>
  - `nano /etc/netdata/netdata.conf`
 
- <b>4. systemctl restart netdata</b>
  - `systemctl restart netdata`
  
<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

<h2 id="nextcloud"> Install nextcloud</h2>

- <b>1. Install nextcloud</b>
  - `sudo wget https://download.nextcloud.com/server/releases/latest.zip`
 
- <b>2. install dulu unzip dengan printah</b>
  - `sudo apt install unzip `
 
- <b>3. baru unzip file menggunak printah</b>
  - `sudo unzip letes.zip`
 
- <b>4. ubah kepemilikan menjadi apache</b>
  - `sudo chown -R www-data:www-data nextcloud`
  
- <b>1. buat akun admin nextcloud</b>
  - `192.168.100.71/nextcloud/`
 
- <b>2. install dulu unzip dengan printah</b>
  - `sudo apt install unzip `
 
- <b>3. baru unzip file menggunak printah</b>
  - `sudo unzip letes.zip`
 
- <b>4. ubah kepemilikan menjadi apache</b>
  - `sudo chown -R www-data:www-data nextcloud`
