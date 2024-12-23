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
<a href="#apache">1. apache2</a> <br>
<a href="#ssh">1. SSH</a> <br>
<a href="#ssh">1. SSH</a> <br>
<a href="#ssh">1. SSH</a> <br>


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
  - `sudo mkdir -p /var/www/example.com'
  - 'sudo chown -R $USER:$USER /var/www/example.com'
  - 'sudo chmod -R 755 /var/www/example.com`
 
- <b>6. Buat file konfigurasi virtual host</b>
  - `sudo nano /etc/apache2/sites-available/example.com.conf`
 
- <b>7. Tambahkan konfigurasi berikut</b>
  - `<VirtualHost *:80>
    ServerAdmin admin@example.com
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/example.com
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>`

-  <b>8. Aktifkan Virtual Host</b>
  - `sudo a2ensite example.com.conf`
  
-  <b>9. Reload Apache</b>
  - `sudo systemctl reload apache2`
