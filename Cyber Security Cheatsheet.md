# GNU/Linux
=======================================================

## Linux Tarihi:

1972 yılında Bell Laboratuvarları'nda Dennis Ritchie ve Ken Thompson tarafından C programlama dili ile UNIX işletim sistemi geliştirildi.

1973 yılında bir sonraki sürümde kaynak kodları kapalı hale getirildi.

1983 yılında Richard Stallman GNU (GNU is Not an UNIX) (açık kaynak lisansı felsefesi) ile UNIX çekirdeğini kullanarak bir işletim sistemi ortaya çıkardı.

1991 yılında Linus Torvalds, ilk Linux çekirdeğini derledi. 

Açık kaynak kodlu bir işletim sistemidir. TCP/IP protokolü desteği vardır.

Bir Linux işletim sisteminin yapısı: 
- DONANIM -> KERNEL -> DAGITIM -> SHELL -> Desktop Environment (opsiyonel)

Bilindik Kabuklar -> ==Bash==, Z Shell, Fish, KornShell

Bir Windows işletim sisteminin yapısı:
- DONANIM -> Windows -> GUI - PowerShell

## Linux Bash Komutları 

pwd = hangi dizinde olduğumuzu gösterir
ls = dizinin içindeki dosya ve alt klasörleri gösterir
cd = klasör içine girmek için
touch =  yeni dosya oluşturur
cd .. = bi önceki klasöre döner
cat = dosyanın içini okumak için
cp = dosyayı kopyalar
rm -rf = dosyayı silmek için
mv = dosyayı taşır
mkdir = klasör oluşturur.
rm = klasörü kaldırır
ls -la = klasörleri liste halinde detaylıca sıralar ve gizli klasörleri de gösterir(gizli klasörler nokta ile başlar)
sudo su = root moda geçer
su = kullanıcı değiştirmek için
nano = dosyanın içine yazmamızı sağlar (text editor)




## Linux'ta Dosya Yapısı:

En sık kullanılan dosya sistemleri:

1. **EXT4**: Günümüz Linux dağıtımlarında en yaygın kullanılan dosya sistemidir ve yüksek performans ile güvenilirlik sunar.
2. **XFS**: Büyük dosyalar ve yüksek performans için optimize edilmiş, özellikle sunucular için ideal bir dosya sistemidir.
3. **Btrfs**: Gelişmiş özellikler (snapshot, denetim noktaları, veri bütünlüğü) sunan modern bir dosya sistemidir.
4. **ZFS**: Veri bütünlüğü, sıkıştırma ve geniş depolama yönetimi sunan, genellikle veri depolama çözümlerinde kullanılan bir dosya sistemidir.

Linux işletim sistemlerinde dosya dizinleri, Windows sistemlerin aksine diskte değil, root dizinin altında bulunur.

**/:** Kök dizindir.

**/bin:** Yürütülebilir dosyaların bulunduğu yerdir. Bu dosyalar tüm kullanıcılar tarafından kullanılabilir. Linux çekirdek komutlarının ls, mv gibi bulunur.

**/boot**: Önyükleyici ve önyükleme dosyalarının bulunduğu yerdir. Sistem kurulumu için gereken dosyaları içerir.

**/dev:** Tüm fiziksel sürücülerin, USB, CD gibi cihazların bağlandığı dizindir.

**/etc:** Kurulu paketler için konfigürasyonları içerir.

**/home:** Oluşturulan kullanıcıların kişisel dizinidir.

**/lib:** Paylaşılan kitaplık dosyalarını ve bazen de çekirdekle ilgili diğer dosyaları içerir. Uygulamaların kullanabileceği kodları içeren dosyalardır.

**/media:** DVD'ler ve USB bellekler gibi harici aygıtlar ve dosyalarına buradan erişilebilir.

**/mnt:** Depolama aygıtlarını veya bölümlerin manuel olarak bağlandığı yerdir. 

**/opt:** Bazı isteğe bağlı paketler burada bulunur ve paket yöneticisi tarafından yönetilir.

**/root:** Yönetici, süper kullanıcı kullanıcının ana klasörüdür.

**/run:** Geçici verileri depolamak için kullanılır.

**/sbin:** Genellikle sistem yönetimi ve düzenlemesi için bir şeyler yükleyebilen, silebilen ve biçimlendirebilen araçlar içerir. -> fdisk, ifconfig 

**/tmp:** Sistem önyüklemeleri arasında kullanılan geçici dosyaları içerir. 

**/usr:** Linux'ta kullanıcılar arasında paylaşılan yardımcı programların ve dosyaların bulunduğu yerdir.  -> /usr/share/wordlists

**/var:** Sistem günlüklerini ve diğer değişken verileri içerir. Genellikle günlük ve yazdırma dosyaları gibi değişken uzunlukta dosyalar ve değişken miktarda veri içerebilecek diğer dosya türleri içerir.

**/srv:** Sunuculara ilişkin verileri içerir. -> /srv/http , /srv/www, /srv/ftp 

**/sys:** Sanal bir dizindir, bilgisayara bağlı cihazlardan gelen bilgileri içerir.

**/kernel**: Çekirdek dosyalarıni içerir.


*Linux sistemlerde kullanıcı veritabanı: PAM

*Parolaları içeren dosya: /etc/shadow

*Grup bilgilerinin saklandığı dosya: /etc/group

*Root yetkisi olan birimleri içeren dosya: /etc/sudoers

*Kullanıcı veritabanını içeren dosya: /etc/passwd
* /etc/passwd altındaki root ve standart kullanıcı hesapları dışındakı diğer hesaplar servis hesaplarıdır. 
* Sisteme bir uygulama veya servis eklendiğinde bu hesaplar oluşur ve servis & uygulama çalıştığında bu hesaplar ile çalışılır. 

mert:x:1000:1000:mert:/home/mert:/bin/bash
* mert: kullanıcı adı
* x: parolanın /etc/shadow a taşındığını belirtir.
* 1000: kullanıcı idsi
* 1000: kullanıcının grup idsi
- mert:/home/mert: mert kullanıcısının dizini
* /bin/bash: mert kullanıcısının bash kullanım hakkı 

Servis hesaplarında /nologin olduğundan ve /bin/bash olmadigindan güvenlik açığı oluşturmaz.

Kullanıcı & servis hesabı oluşturmak için:
* sudo useradd mert
	* useradd komutu ile şifre, home dizini oluşturulmaz ve bash erişimi verilmez. doğrudan kullanıcı oluşturulur.
* sudo adduser mert
	* Parola, kullanıcı bilgileri, /home dizini oluşturulur. Kısacası daha detaylıdır.

Grup oluşturmak için:
* groupadd grup1
* usermod -aG grup1 mert
	* a yeni grup oluşturmadan mevcut gruba ekleme
	- G grup belirtir.

su: switch user -> su deneme1 -> deneme1 kullanıcısı ile oturum açma
su root, sudo su: root kullanıcısı ile giriş yapma

 - *Linuxta oluşturulan her kullanıcı default olarak kendi grubuyla gelir.*
 
- *Bir satırın başında "%" varsa grup olduğunu belirtir.*

- *Linuxlarda sudo servisi kurulu gelir. root olarak giriş  yapmadığımızda bile sudo grubuna dahilse her şeyi yönetebilir.*


## Linux'ta dosya izinleri:


**3 tür grup vardır:**
- 1- Owner
- 2- Group
- 3- Others

**3 tür izin vardır:**
- 1- Read (r - 4)
- 2- Write (w - 2)
- 3- Execute (x - 1)


**İzinler, rakamlar ya da harfler ile değiştirilebilir.*
* İlk 3 harf ownerın izinlerini belirtir.
* İkinci 3 harf grubun izinlerini belirtir.
* Son 3 harf othersın izinlerini belirtir.
-  Read = 4, Write = 2, Execute = 1

**ls -l** = mevcut dosya izinlerini ve bir dosya hakkındaki tüm detayları gösterir

**chmod** = dosya izinlerini değiştirmek için kullanılan komuttur. ( chmod 754 /mnt/test1.txt )

**chown** =  bir dizinin ya da dosyanın ownerını değiştirmeye yarar.( chown cem /mnt/test1.txt) (chown cem:cem hem ownerı hem de grubu belirtir)

**find / -perm 777** = 777 yetkilerini sahip herkesi tarar


## Linux'ta Disk Yönetimi

Diskler /dev dizinin altına mount olur.

fdisk ( -l ) = sisteme bağlı diskler hakkında temel bilgi verir.
df -h = sistemde sadece mount edilmiş diskleri ve disklerin doluluk oranını gösterir.
lsblk = sisteme bağlı diskleri göstermek için farklı bir seçenek.
blkid = Diskin uid sini verir.
- blkid /dev/sdx
uid(Unique Identifier): Disklerin değişmez belirtecidir.

/etc/fstab: Sisteme bağlı diskler hakkında kalıcı konfigürasyon bilgilerini tutar.
* Örneğin sistem boot olurken bir diskin otomatik boot olması gibi.
* /dev/sdx /mnt/sdx ext4 defaults 0 2
* uid ile mount: 
	* UUID=b263c123-6659-4def-a507-eca731584abe /mnt/sdx ext4 defaults 0 2
- Hata kontrolü için sudo mount -a

###### Disk Formatlama

fdisk veya cfdisk ile formatlama:
- fdisk /dev/sdx : Arayüz yardımıyla disk bölümlendirilir. (Disk yazılabilir hale gelir.)
- Diske dosya sistemi tanımlanır. mkfs.*dosyasistemi /dev/sdx (ext4,btrfs,ext3,xfs)
* Disk kullanılmak üzere mount edilir: 
	- cd /mnt
	- mkdir sdx
	- mount /dev/sdx /mnt/sdx

Mount edilmiş herhangi bir diskin bağlantısını koparmak için: 
* umount /mnt/sdx

*Bu işlemlerin kalıcı olabilmesi için FSTAB'a yazmamız lazım.*


###### Disk Genişletme & Küçültme

Disk küçültme risklidir, tavsiye edilmez. Veri kaybı yaşanabilir.

cfdisk aracı ile genişletme:
- Diskin bitiş noktasından sonra boş alan var ise disk genişleyebilir.
- Disk genişledikten sonra dosya sistemi de genişlemelidir.
	- ext için: resize2fs /dev/sdx
	- xfs için: xfs_growfs /dev/sdx


#### LVM

LVM = Logical Volume Management.

Birden fazla diski tek bir ortak havuzda toplayıp, bu havuzdan logical volumelar oluşturabiliriz. Bu bize dinamik ve güvenli bir yapı sağlar.

###### LVM kullanım adımları:

- LVM de kullanılacak diskler tanımlanır.
- LVM havuzu oluşturulur ve tanımlanan diskler havuza eklenir.
- Havuz içinden volume'lar oluşturulur.
- Volume'ların dosya sistemleri oluşturulur.
- Volumelar mount edilir.

###### LVM komutları:

pvcreate: Diskleri physical volume a çevirme.
- pvcreate /dev/sdc /dev/sdd

vgcreate: volumegroup oluşturma.
- vgcreate volumegroup10 /dev/sdc /dev/sdd

lvcreate: logical volume oluşturma.
- lvcreate -L 500G -n lvm10 volumegroup10

volumegroup formatlama ve mount etme (dosya sistemi):
- mkfs.ext4  /dev/mapper/volumegroup10-lvm10
- mount /dev/mapper/volumegroup10-lvm10 /mnt/lvmtest

vgs: LVM havuzlarını (volume gruplarını) listeler.

vgextend: volumegroup'ları genişletme.
* vgextend *volumegroup1 /dev/sdc

lvextend: logical volume'ları genişletme
- Logical volume, lvextend ile genişletilir.
	- lvextend -l +100%FREE /dev/mapper/volumegroup10-lvm10
- Dosya sistemi genişletilir.
	- resize2fs /dev/mapper/volumegroup10-lvm10



SCP = windowsdan shell ekranı ile linuxa dosya transferi protokolü

`scp C:\Users\Ali Asker\Desktop\ubuntu-22.04.3-live-server-amd64.iso ali@192.168.17.177/linuxta_istenilen_yer` 
 windowstaki bir dosyayı scp ile linuxa gönderir.


## Linux'ta Firewall 

Bir firewall, ağ trafiğini kontrol ederek yetkisiz erişimleri engelleyen bir güvenlik sistemidir. Linux'ta firewall genellikle kernel seviyesinde çalışır.

**En bilindik firewall isimleri:** 
-  Ufw
-  Firewalld
-  Iptables
-  Nftables



##### Ubuntu'da Firewall

Ubuntu, güvenlik duvarı yönetimi için varsayılan olarak **UFW (Uncomplicated Firewall)** aracını kullanır.


**Basit Komutlar :** 
- `sudo ufw enable` = firewallu aktif eder.
- `sudo ufw disable` = firewallu deaktif eder.
- `sudo ufw status numbered` = firewallda açık portları gösterir.
- `sudo ufw allow ssh(ya da portun numarası yazılır)` = ssh(22) portunu açar.
-  `sudo ufw allow from 192.168.203.1 to any port 22` = ipye özel ssh portunu açar ve      filtrelemiş olur. 




##### Centos'ta Firewall

CentOS, güvenlik duvarı yönetimi için varsayılan olarak **firewalld** adlı dinamik bir güvenlik duvarı yönetim aracını kullanır.


**Basit Komutlar :**
* `sudo systemctl enable firewalld` = firewallu aktif eder.
* `sudo systemctl disable firewalld` = firewallu deaktif eder.
* `sudo firewall-cmd --list-all` = firewall tarafından tanımlanan tüm kuralları ve yapılandırmaları ayrıntılı bir şekilde listeleyen bir komuttur.
* `sudo firewall-cmd --zone=public --add-service=ssh --permanent` = ssh(22) portunu açar.
* `sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.203.1" port port=22 protocol=tcp accept' --permanent` = ipye özel ssh portunu açar ve  filtrelemiş olur. 



