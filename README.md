# FinalProjek
Final Projek OS Server &amp; Sistem Admin 

# Keterangan
<b>NAMA    : Muhammad Zidan Manulana</b>

<b>NIM     : 23.83.1022</b>

<b>Tanggal : 5 Desember 2024</b>

# Spesifikasi Sistem Operasi
<b>Ubuntu Server 22.04.3</b>

<b>Base Memory 8982MB</b>

<b>RAM 4 GiB (memori sestem)</b>

<b>Prosesor inti ganda 2 GHz</b>

<b>Ruang hard drive 25 GB</b>

<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

# Langkagh-langkah

<h2> Update and Upgrade</h2>

- <b>1. Open a terminal and run the following commands:</b>
  - `sudo apt update && sudo apt upgrade -y`

<h2> OPEN SSH</h2>

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
 

<h2> Download dan Konfigurasi apache</h2>
