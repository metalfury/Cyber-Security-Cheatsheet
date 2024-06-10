# NETWORK

## Network Nedir ?
- Bir bağlam yardımıyla (kablo, wireless) cihazların birbiriyle iletişim kurmasını sağlayan ortam. Temelleri, Amerikan Savunma Bakanlığı Hava Kuvvetleri tarafından geliştirilen ARPANET ile atılmıştır.
- Fiziksel ve yazılımsal olmak üzere 2 boyuttan oluşur. 
	- **Fiziksel Network:** Network topolojisi, kablolar, switchler kısacası network cihazları.
	- **Yazılımsal Network:** Protokoller.

**Paket:** Ağ iletişiminde verilerin taşınması için kullanılan temel birimdir.

**Hub:** Paketleri, üzerinde bağlı olan tüm hostlara ileten network cihazlarıdır.

**Switch:** Paketleri, ARP tablosuna göre istenilen hedefe yönlendiren network cihazlarıdır.

**Gateway:** Cihazların farklı networklere giderken kullandıkları geçit.

**Router:** Farklı networkler arası iletişimi sağlayan network cihazlarıdır.

**Firewall:** Gelen ve giden trafiği filtreleyen, denetleyen, ağ katmanında çalışan cihazlardır.

**NIC(Network Interface Card):** Cihazların ethernet ağına bağlanmasını sağlayan donanım.

**MAC Adresi:** NIC(network kartları)lerin sahip olduğu üreticiler tarafından sağlanan pratikte değişmez olan numaralardır.

**Port:** Bilgisayar ağlarında belirlenmiş numaralı adreslerdir ve her biri belirli bir uygulamanın iletişim kurduğu noktayı temsil eder.

**TCP(Transmission Control Protocol):** İnternet üzerinden veri iletimini sağlamak için kullanılan bir iletişim protokolüdür.  

**UDP(User Datagram Protocol):** Veri bütünlüğünü garanti etmeyen, TCP/IP protokolüne göre daha hızlı iletim sağlayan bir iletişim protokolüdür. 

**DNS(Domain Name System):** İsimleri IP adresine dönüştüren servis.

**NAT(Network Address Translation):** Private IP adreslerinin dış ağa erişebilmesi için public IP adresine çevrilmesi işlemi.

**PAT(Port Address Translation):** Ağdaki private IP adreslerinin tek bir genel IP adresine dönüştürürken, TCP veya UDP port numaralarının değiştirilmesi işlemi.

## Network Topolojileri 
> Ring, Bus, Star, Mesh
- **Ring Topoloji:** Cihazlar birbirine halka şeklinde bağlanmıştır. Bir paket yollandığında, paket hedef cihaza ulaşana kadar tüm cihazlara uğrar. (Tokenli mimaride tokene sahip cihaz paketi alır.)

- **Bus Topoloji:** Bütün cihazlar tek bir hat üzerinde birbirine bağlıdır. Bir cihaz diğer cihaza paket yollamadan önce hattın boş olduğuna emin olmak zorundadır, aksi halde çakışma yaşanacaktır. Veri tüm cihazlara yollanır fakat sadece hedef makineye ulaşır. Düşük performanslı bir topolojidir.

- **Star Topoloji:** Cihazlar bir hub veya switch yardımıyla birbirlerine bağlanırlar. 
	Hub ile oluşturulan topolojiler:
		Gelen paketleri tüm portlara yollar.
		Herkesin paketi herkese gidebilir.
		Yoğun bir trafik oluşur. 
		Güvenlik zafiyetleri oluşur.
	Switch ile oluşturulan topolojiler:
		Switch üzerinde yazılım çalışır.
		Bu sebeple paketler herkese gönderilmez. Paketin gideceği cihazlar tanınır.
		Zafiyetler kısmen çözülmüş olur.

- **Mesh Topoloji:** Bütün cihazlar birbiriyle bağlıdır. Herhangi bir kablo koparsa sistem çökmez. Paketler sadece alıcısına ulaşır. Bir arıza oluştuğunda tespiti kolaydır.

> Network Hablerleşmesinde Kullanılan Protokoller: NETBUI, IPX/SPX, TCP/IP

## IP Subnetting

**Subnet Mask:** Cihazların hangi ağ bloğunda bulunduğunu öğrenmemizi sağlayan tanımlayıcıdır.

**Network ID:** Makinelerin bulunduğu networkün adresini belirler. IP adresinin alt ağ maskesi ile and işlemi kullanılarak elde edilir.

**IP Adresi:** TCP/IP protokolüne göre network haberleşmesi yapacak cihazların alması gereken numaralardır. Bu numaralar ağdaki diğer cihazlarla çakışmamalıdır. 
- 4 oktetten oluşur. (Böyle geliştirildi.)
- Her oktet 8 bitten oluşur.
- IPv4 adresleri, private ve public olmak üzere 2 bölümden oluşur.
- Private Blok: Sadece iç network haberleşmesinde kullanılan ip adreslerini içerir.
	- 10.0.0.0/8 – 10.255.255.255 
	- 172.16.0.0/12 – 172.31.255.255
	- 169.254.0.0/16 - 169.254.255.255 -> Link Local
	- 192.168.0.0/24 – 192.168.255.255
* Public Blok: Dış network haberleşmesinde kullanılan ip adreslerini içerir.
* IP Adresleri bloklarına göre ve kullanım senaryolarına göre sınıflara ayrılmıştır.
* Class A: 0.0.0.0 - 127.255.255.255
* Class B: 128.0.0.0 - 191.255.255.255
* Class C: 192.0.0.0 - 223.255.255.255
* Class D: 224.0.0.0 - 239.255.255.255 -> (Özel kullanım)
* Class E: 240.0.0.0 - 255.255.255.255 -> (Bilimsel araştırmalar için ayrılmıştır, internet ortamında kullanılmazlar.)

10.10.0.0, 0.0.255.255
Bir Networkte Bulunan Host Sayısı: 
- (2^n - 2) 
- 2 -> 2lik sistem
- n -> Subnet Mask de 0 olan bit sayısı
* 2 -> 1. Network ID | 2. Broadcast IP

## Paket İletim Türleri

- **Unicast:** Paket bir kaynaktan sadece tek bir hedefe gider.
- **Multicast:** Paket bir kaynaktan belirli bir gruba gider.
- **Broadcast:** Paket bir kaynaktan bütün hedeflere gider.

## OSI Referans Modeli
> Ağlar üzerinde çalışan cihazların birbirleriyle iletişimini nasıl kuracağını tanımlayan standart model.

- **7. Application - Uygulama** : Kullanıcıların doğrudan etkileşimde bulunduğu katmandır
	-  Web tarayıcı, e-posta, dosya aktarımı
- **6. Presentation - Sunum** : Veri formatlama, şifreleme ve sıkıştırma gibi işlemlerden sorumlu katman.
	- ASCII-Unicode dönüşümü, SSL/TLS
- **5. Session - Oturum** : Oturumlar arasındaki ilişkiyi yönetir.
	- Sosyal medya hesaplarında oturumun açık/kapalı durması.
- **4. Transport - İletim** : Veri paketlerinin kaynak ve hedef arasında güvenilir bir şekilde iletilmesini sağlar.
   	- Paketlere port numarası ve sıra numarasınin eklenmesi.
- **3. Network - Ağ** : Paketlerinin kaynak ve hedef arasında yönlendirilmesini ve iletilmesini sağlar.
	- Paketlere IP adresi bilgileri verilir.
 	- **L3 SWITCH VE ROUTER BURADA ÇALIŞIR**
- **2. Data-Link - Veri Bağlantı** : Ağdaki cihazlar arasında doğrudan veri transferini yönetir ve hataları düzeltir.
	- Paketlere MAC adresi verilir ve kuyruk kısmına hata kontrol değeri yazılır.
 	- **L2 SWITCH BURADA ÇALIŞIR**
- **1. Physical - Fiziksel** : Verinin fiziksel ortamda nasıl iletileceğini belirler.
	- Data bitlere dönüştürülür ve iletim sağlanır.
 	- **HUB BURADA ÇALIŞIR**


# GNU/Linux


## Linux Tarihi:

1972 yılında Bell Laboratuvarları'nda Dennis Ritchie ve Ken Thompson tarafından C programlama dili ile UNIX işletim sistemi geliştirildi.

1973 yılında bir sonraki sürümde kaynak kodları kapalı hale getirildi.

1983 yılında Richard Stallman GNU (GNU is Not an UNIX) (açık kaynak lisansı felsefesi) ile UNIX çekirdeğini kullanarak bir işletim sistemi ortaya çıkardı.

1991 yılında Linus Torvalds, ilk Linux çekirdeğini derledi. 

Açık kaynak kodlu bir işletim sistemidir. TCP/IP protokolü desteği vardır.

Bir Linux işletim sisteminin yapısı: 
- DONANIM -> KERNEL -> DAGITIM -> SHELL -> Desktop Environment (opsiyonel)

Bilindik Kabuklar -> **Bash**, Z Shell, Fish, KornShell

Bir Windows işletim sisteminin yapısı:
- DONANIM -> Windows -> GUI - PowerShell

## Linux Bash Komutları 

- **pwd**: Geçerli çalışma dizinini gösterir.
- **ls**: Dizinin içindeki dosya ve alt klasörleri gösterir.
- **ls -la**: Klasörleri liste halinde detaylıca sıralar. Gizli klasörler listelenir. (gizli klasörler nokta ile başlar)
- **cd**: Dizin değiştirmek için kullanılır.
	- **cd** /home
- **cd ..**: Bir üst dizine dönmemizi sağlar.
- **touch**: Yeni dosya oluşturur.
	- **touch** dosya.txt
- **mkdir**: Yeni bir dizin oluşturur.
	- **mkdir** /home/dizin
- **cat**: Dosya içeriğini gösterir.
	- **cat** dosya.txt   
- **cp**: Dosya veya dizini kopyalar
	- **cp** /home/dosya.txt /downloads/dosya.txt
- **mv**: Dosyayı ve dizini taşır.
  	- **mv** /home/dosya.txt /downloads/dosya.txt
- **rm**: Dosya ve veya dizin siler.
	- **rm** dosya.txt
- **rm -rf**: Dizin ve içindeki tüm alt dosyaları siler.
	- rm -rf /downloads
- **su**: Kullanıcı değiştirir.
	- **su** kullanici_2
- **sudo su**: root kullanıcıya geçer.
- **nano**: Komut satırı tabanlı basit bir metin düzenleyici. (text editor)
	- **nano** dosya.sh

## Linux'ta Dosya Yapısı:

En sık kullanılan dosya sistemleri:

1. **EXT4**: Günümüz Linux dağıtımlarında en yaygın kullanılan dosya sistemidir ve yüksek performans ile güvenilirlik sunar.
2. **XFS**: Büyük dosyalar ve yüksek performans için optimize edilmiş, özellikle sunucular için ideal bir dosya sistemidir.
3. **Btrfs**: Gelişmiş özellikler (snapshot, denetim noktaları, veri bütünlüğü) sunan modern bir dosya sistemidir.
4. **ZFS**: Veri bütünlüğü, sıkıştırma ve geniş depolama yönetimi sunan, genellikle veri depolama çözümlerinde kullanılan bir dosya sistemidir.

> Linux işletim sistemlerinde dosya dizinleri, Windows sistemlerin aksine diskte değil, root dizinin altında bulunur.

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

***
- Linux sistemlerde kullanıcı veritabanı: *PAM*

- Parolaları içeren dosya: */etc/shadow*

- Grup bilgilerinin saklandığı dosya: */etc/group*

- Root yetkisi olan birimleri içeren dosya: */etc/sudoers*

- Kullanıcı veritabanını içeren dosya: */etc/passwd*

> /etc/passwd altındaki root ve standart kullanıcı hesapları dışındakı diğer hesaplar servis hesaplarıdır. 
> Sisteme bir uygulama veya servis eklendiğinde bu hesaplar oluşur ve servis & uygulama çalıştığında bu hesaplar ile çalışılır. 
***
mert:x:1000:1000:mert:/home/mert:/bin/bash
- **mert**: kullanıcı adı
- **x**: parolanın /etc/shadow a taşındığını belirtir.
- **1000**: kullanıcı idsi
- **1000**: kullanıcının grup idsi
- **mert:/home/mert**: mert kullanıcısının dizini
- **/bin/bash**: mert kullanıcısının bash kullanım hakkı 

> Servis hesaplarında /nologin olduğundan ve /bin/bash olmadığından güvenlik açığı oluşturmaz.
***

## Linux'ta Kullanıcı ve Grup İşlemleri
Kullanıcı & servis hesabı oluşturmak için:
- `sudo useradd mert`
	- useradd komutu ile şifre, home dizini oluşturulmaz ve bash erişimi verilmez. doğrudan kullanıcı oluşturulur.
- `sudo adduser mert`
	- Parola, kullanıcı bilgileri, /home dizini oluşturulur. Kısacası daha detaylıdır.

Grup oluşturmak için:
- `groupadd grup1`
- `usermod -aG grup1 mert`
	- a yeni grup oluşturmadan mevcut gruba ekleme
	- G grup belirtir.

su: switch user
- `su deneme1`
	- deneme1 kullanıcısı ile oturum açma
- `su root`, `sudo su`
	- root kullanıcısı ile giriş yapma

> *Linuxta oluşturulan her kullanıcı default olarak kendi grubuyla gelir.*
 
> *Bir satırın başında "%" varsa grup olduğunu belirtir.*

> *Linuxlarda sudo servisi kurulu gelir. root olarak giriş  yapmadığımızda bile sudo grubuna dahilse her şeyi yönetebilir.*


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

- **fdisk ( -l )**: sisteme bağlı diskler hakkında temel bilgi verir.
- **df -h**: sistemde sadece mount edilmiş diskleri ve disklerin doluluk oranını gösterir.
- **lsblk**: sisteme bağlı diskleri göstermek için farklı bir seçenek.
- **blkid**: Diskin uid sini verir.
	- `blkid /dev/sdx`
- **uid (Unique Identifier)**: Disklerin değişmez belirtecidir.

***
> **/etc/fstab**: Sisteme bağlı diskler hakkında kalıcı konfigürasyon bilgilerini tutar.
- Sistem boot olurken bir diskin otomatik mount olması, diskin bilgilerinin /etc/fstab a girilmesi ile mümkün olur.
	- `/dev/sdx /mnt/sdx ext4 defaults 0 2`
- uid ile mount: 
	- `UUID=b263c123-6659-4def-a507-eca731584abe /mnt/sdx ext4 defaults 0 2`
- Hata kontrolü
	- `sudo mount -a`
***
### Disk Formatlama

fdisk veya cfdisk ile formatlama:
- Arayüz yardımıyla disk bölümlendirilir. (Disk yazılabilir hale gelir.)
	- `(c)fdisk /dev/sdx`
- Diske dosya sistemi tanımlanır.
	- `mkfs.*dosyasistemi /dev/sdx (*ext4,btrfs,ext3,xfs)`
- Disk kullanılmak üzere mount edilir: 
	- `cd /mnt`
	- `mkdir sdx`
	- `mount /dev/sdx /mnt/sdx`

Mount edilmiş herhangi bir diskin bağlantısını koparmak için: 
- `umount /mnt/sdx`

*Diskin kalıcı olarak mount olması için FSTAB a kayıt edilmesi gerekmektedir.*


### Disk Genişletme & Küçültme

Disk küçültme risklidir, tavsiye edilmez. Veri kaybı yaşanabilir.

cfdisk aracı ile genişletme:
- Diskin bitiş noktasından sonra boş alan var ise disk genişleyebilir.
- Disk genişledikten sonra dosya sistemi de genişlemelidir.
	- **ext** için: `resize2fs /dev/sdx`
	- **xfs** için: `xfs_growfs /dev/sdx`


### LVM

**LVM** = Logical Volume Management.

LVM yapısı ile birden fazla diski tek bir ortak havuzda toplayıp, bu havuzdan logical volumelar oluşturabiliriz. Bu bize dinamik ve güvenli bir yapı sağlar.

#### LVM kullanım adımları ve komutları:

1. LVM de kullanılacak diskler tanımlanır.
	- **pvcreate**: Diskleri physical volume a çevirme.
		- `pvcreate /dev/sdc /dev/sdd`
2. LVM volume group havuzu oluşturulur ve tanımlanan diskler havuza eklenir.
	- **vgcreate**: volumegroup oluşturma.
		- `vgcreate volumegroup10 /dev/sdc /dev/sdd`
3. Havuz içinden logical volume'lar oluşturulur.
   	- **lvcreate**: logical volume oluşturma.
		- `lvcreate -L 500G -n lvm10 volumegroup10`
4. Volume group'un dosya sistemi oluşturulur.
	- `mkfs.ext4  /dev/mapper/volumegroup10-lvm10`
5. Volume group mount edilir.
	- `mount /dev/mapper/volumegroup10-lvm10 /mnt/lvmtest`

***
> - **vgs**: LVM havuzlarını (volume gruplarını) listeler.
> - **lvs**: LVM'deki logical volume'ları listeler.
***

#### LVM Disk Genişletme

1. Eklenecek disk **pvcreate** ile physical volume a çevrilir.
	- `pvcreate /dev/sdc`
2. Volume group'a **vgextend** ile disk eklenir ve genişletme yapılır.
	- `vgextend volumegroup1 /dev/sdc`
3. Logical volume, lvextend ile genişletilir.
	- `lvextend -l +100%FREE /dev/mapper/volumegroup10-lvm10`
4. Dosya sistemi, türüne göre genişletilir. (rfs,ext4)
	- `resize2fs /dev/mapper/volumegroup10-lvm10`

## Linux'ta Firewall 

Bir firewall, ağ trafiğini kontrol ederek yetkisiz erişimleri engelleyen bir güvenlik sistemidir. Linux'ta firewall genellikle kernel seviyesinde çalışır.

**En bilindik firewall isimleri:** 
-  Ufw
-  Firewalld
-  Iptables
-  Nftables


#### Ubuntu'da Firewall

Ubuntu, güvenlik duvarı yönetimi için varsayılan olarak **UFW (Uncomplicated Firewall)** aracını kullanır.


**Basit Komutlar :** 
- `sudo ufw enable`: firewallu aktif eder.
- `sudo ufw disable`: firewallu deaktif eder.
- `sudo ufw status numbered`: firewallda açık portları gösterir.
- `sudo ufw allow ssh(ya da portun numarası yazılır)`: ssh(22) portunu açar.
- `sudo ufw allow from 192.168.203.1 to any port 22`: ipye özel ssh portunu açar ve filtrelemiş olur. 


#### CentOS'ta Firewall

CentOS, güvenlik duvarı yönetimi için varsayılan olarak **firewalld** adlı dinamik bir güvenlik duvarı yönetim aracını kullanır.


**Basit Komutlar :**
- `sudo systemctl enable firewalld`: firewallu aktif eder.
- `sudo systemctl disable firewalld`: firewallu deaktif eder.
- `sudo firewall-cmd --list-all`: firewall tarafından tanımlanan tüm kuralları ve yapılandırmaları ayrıntılı bir şekilde listeler.
- `sudo firewall-cmd --zone=public --add-service=ssh --permanent`: ssh(22) portunu açar.
- `sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address: "192.168.203.1" port port=22 protocol=tcp accept' --permanent` = ipye özel ssh portunu açar ve filtrelemiş olur. 


## Dosya Aktarımı 

### SCP (Secure Copy Protocol)
- SSH protokolü üzerinden güvenli dosya transferi sağlar.
	- `scp C:\Users\Ali Asker\Desktop\ubuntu-22.04.3-live-server-amd64.iso ali@192.168.17.177/linux_path`: Windowstaki bir dosyayı scp protokolü ile Linuxa gönderir.

### Samba 
- SMB protokolü üzerinden Linux cihazlarda dosya paylaşımını sağlar. 

#### Samba Server Kurulumu ve Dizin Paylaşımı:
1. Samba servisi kurulur.
	- `apt install samba`
2. Paylaşım yapılacak dizin oluşturulur.(opsiyonel)
	- `mkdir /home/share`
3. Paylaşılacak dizine, erişim yapılacak kullanıcı için sahiplik ve izin atamaları yapılır.
	- `chown mert:mert /home/share`
	- `chmod 775 /home/share`
4. Dizine erişecek kullanıcıya samba parolası tanımlanır.
	- `smbpasswd -a mert` (-a parametresi ile kullanıcı samba veritabanına eklenir.)
5. Samba config dosyasında düzenlemeler yapılır.
   	- `nano /etc/samba/smb.conf`
	- **`interface` konfigürasyonu**
		- `interfaces = 127.0.0.0/8 ens33`
			- `interfaces`: Samba sunucusunun dinleyeceği arayüzleri tanımlar.
			- `127.0.0.0/8`: Samba sunucusunun 127.0.0.0/8 ip bloğuna gelen istekleri dinleyeceği belirtilir.
 			- `ens33`: Samba sunucusunun ens33 network arayüzüne gelen istekleri dinleyeceğini belirtir.
	- **Dizin tanımlaması**
		- ```
    			[sambashare]
    			comment = Samba on Ubuntu
    			path = /home/share
    			read only = no
    			writable = yes
    			browsable = yes
    			guest no
    			valid users = @mert, @ali 		
		- **comment**: Dizin paylaşımı hakkında bilgi verici yorum.
		- **path**: Paylaşım yapılacak dizin belirtilir.
		- **read only = no**: Dizinde okuma işlemi yapılabileceği belirtilir.
		- **writable = yes**: Dizinde yazma işlemi yapılabileceği belirtilir.
		- **browsable = yes**: Dizinin kendisinin ve alt dizinlerinin görüntülenebileceği belirtilir.
		- **guest no**: Misafir kullanıcılara izin verilmeyeceği belirtilir.
  		- **valid users = @mert, @ali**: Belirlenen kullanıcılara erişim izni verileceği belirtilir.	 
6. Firewall üzerinden erişim izni verilir.
   	- `ufw allow samba`

> Bu adımlardan sonra belirlenen dizin (/home/share) Samba servisi ile paylaşılmış olur.

#### Paylaşılan dizine erişmek için:
##### Windows
1. Çalıştır aracı açılır.  
2. Paylaşım yapılan cihazın IP adresi yazılır.
	- `\\192.168.234.167`
3. Dizin görüntülenir.

##### Linux
1. Paylaşılan dizine erişmek için smbclient aracı yüklenir.
	- `apt install smbclient`
2. Erişilmek istenen dizin ve erişecek kullanıcı belirtilir.
  	- `smbclient //192.168.234.135/sharing -U mert`
  		- **smbclient**: Kullanılacak servis.
  		- **//192.168.234.135/sharing**: Erişilecek dizin.
   		- **-U**: Kullanıcı parametresi.
   		- **mert**: Dizine erişecek kullanıcı.

> Bu adımlardan sonra, işletim sistemleri üzerinden belirlenen dizine (/home/share) Samba servisi üzerinden erişim sağlanmış olur.

### NFS
- Samba alternatifi bir servistir. Genellikle Linux ve UNIX işletim sistemlerinde kullanılır. 2016 yılından sonra Windows cihazlarda kullanılabilir hale gelmiştir.
- Paylaşılan dizinlerin, cihazlara mount edilmesiyle okuma/yazma işlemleri yapılır.

#### NFS Server Kurulumu ve Dizin Paylaşımı
1. NFS Server servisi kurulur.
	- `apt install nfs-server-kernel`
2. Paylaşılacak dizin oluşturulur. (opsiyonel)
   	- `mkdir /home/sharing`
3. Paylaşılacak dizine, erişim yapılacak kullanıcı için sahiplik ve izin atamaları yapılır.
	- `chown mert:mert /home/sharing`
	- `chmod 775 /home/sharing`
4. NFS config dosyası düzenlenir. Bu dosyada dizinlerin hangi özelliklerle paylaşılacağı belirlenir.
   	- `nano /etc/exports`
   		-  /home/sharing  *(rw,sync,no_subtree_check)
   	 		- **/home/sharing**: Paylaşılacak dizin.
   	    		- **\***: Gelen her isteğin kabul edileceği belirtilir. IP adresi veya network ID yazılabilir.
   	      		- **rw**: Dizine yazma işlemi yapılabileceği belirtilir.
   	        	- **sync**: Dizinde olan değişiklerin, mount olduğu diğer dizinlere de senkronize olması sağlanır.
   	         	- **no_subtree_check**: Alt ağaç yapısının taramasının yapılmayacağı belirtilir.
5. NFS config dosyası ayarları aktif edilir.
   	- `exportfs -a`
6. NFS servisi yeniden başlatılır.
   	- `systemctl restart nfs-server`
7. Firewall üzerinden NFS servisine izin verilir.
   	- `ufw allow nfs`
   	- `ufw allow nfs/tcp`
   	- `ufw allow nfs/udp`
   
> Bu adımlardan sonra belirlenen dizin (/home/sharing) NFS servisi ile paylaşılmış olur.

#### Paylaşılan dizine erişmek için:
##### Linux
1. NFS Client servisi kurulur.
	- `apt install nfs-common`
2. Erişilmek istenen dizin, belirlenen dizine mount edilir.
	- `mount -t nfs 192.168.234.135:/home/sharing /mnt/share`
		- **mount -t nfs**: NFS protokolü ile paylaşılan dizini mount et.
 		- **192.168.234.135:/home/sharing**: Paylaşılan dizin belirtilir.
   		- **/mnt/share**: Mount edilecek dizin belirtilir.

##### Windows
1. NFS Client servisi kurulur. (powershell veya windows eklentileri üzerinden.)
2. Erişilmek istenen dizin, belirlenen dizine mount edilir.
	- `mount 192.168.234.134:/home/sharing F:`
		- **mount**: Mount parametresi.
		- **192.168.234.134:/home/sharing**: Paylaşılan dizin.
		- **F:**= Mount edilecek dizin.

> Bu adımlardan sonra, işletim sistemleri üzerinden belirlenen dizine (/home/sharing) NFS servisi üzerinden erişim sağlanmış olur.



# RAID

##### SUNUCU TÜRLERİ
-  Tower Sunucular
-  Rack Sunucular
-  Blade Sunucular

---

>**SPARE DISK**
  Volumeden ayrı tutulan boş disktir ve eğer bir disk bozulursa onun yerine geçer. İsteğe göre spare disk ayrılabilir.


>**VOLUME** 
  Raidlerin kendi kurallarına uygun özellikleri ile birleşip tek bir depolama alanı ortaya çıkarmasına denir.


>**HOT PLUG**
  Sunucuya bağlı olan bir donanım bileşeninin, sistemin çalışır durumdayken çıkarılıp takılabilme özelliğini ifade eder.


>**RAID KARTI** 
  Sunucularda hem disklerin yedeklenmesini, hem de daha performanslı çalışmasını sağlar. Raid yapabilmek için sunucuda raid kartı olması şarttır.


---


**RAID 0** 

-  2 ya da daha çok diskin bir araya getirilmesiyle yapılır.
-  Performans amaçlıdır. Ne kadar çok disk bir araya getirilirse performans da o kadar artar.
-  Yedeklilik sağlamaz. Yüksek performans sağlar.
-  Bir diskte bir arıza meydana gelirse diskteki veri erişilemez hale gelir.


**RAID 1**

-  2 diskin birleştirilmesiyle yapılır.
-  Diskler birbirinin klonu durumundadır. Diskin biri kaybedilse bile diğer diskle devam edilir.
-  Performans artışı sağlamaz. Sadece yedeklilik sağlar.


**RAID 5**

-  3 ya da daha fazla diskle yapılabilir.
-  En çok kullanılan raid türüdür.
-  Hem performans hem de yedeklilik sağlar.
-  Her 2 diskin doğruluk bilgisi 3. diskte yedeklenir. Bir disk bozulursa 3. diskteki doğrulama bilgisi ile veri tekrardan olusturulmaya çalışılır.
-  Toplam boyutun 3 te 1 i disk doğrulamasına gider.
-  Veri kaybı 2 diskin bozulmasıyla gerçekleşir.


**RAID 10(1+0)**

-  En az 4 disk olabilir ve çift sayılarla artabilir (6-8-10)
-  Önce her 2 disk kendi içinde RAID 1 yapılır.
-  Sonra bu gruplanan diskler bir araya getirilir ve RAID 0 yapılır.
-  Hem performans hem de yedeklilik için kullanılır.
-  Aynı RAID den 2 disk bozulursa veri kaybı yaşanır.
-  Bir grupta bir disk toleransı vardır.


**RAID 50(5+0)****

-  En az 6 disk ile yapılır.
-  Önce her 3 disk kendi içinde RAID 5 yapılır.
-  Sonra bu gruplanan diskler bir araya getirilir ve RAID 0 yapılır.
-  Aynı RAID den 2 disk bozulursa veri kaybı yaşanır.
-  En az 1 disk toleransı vardır.



--- 


# Storage Sistemleri

>Dijital dünyada verinin tutulması için geliştirilmiş alanlardır.


1- **Local Diskler**

2- **Remote Storage**

- 2.2- NAS(Network Attached Storage) Üniteleri

- 2.3- SAN (Network Area Storage) Üniteleri

- 2.4- VSAN Üniteleri(VmWare'a ait teknoloji)


--- 


**2.2 - NAS(Network Attached Storage) Üniteleri :**

Üzerine çokca disk takabileceğiniz ve bu disklere uzaktan erişebileceğiniz sistemlerdir. Bir yazılımla diskleri konfigüre eder ve TCP/IP networkleri üzerinden sunuculara bağlanmasını sağlar. Diskleri konfigüre edebilmek için NAS yazılımı vardır. Örneğin Win2019'da NAS yazılımı birlikte gelir ve OpenSource NAS yazılımları sunuculara kurulabilir. 

NAS'lar, disk entegre etme ve disk boyutları konusunda çok esnektir. Maliyet ve performans açısından ve kullanımı kolay olduğundan günümüzde fazlaca kullanılır. TrueNAS ürünü istenilen sunucuya işletim sistemi gibi kurulup, o server NAS storage gibi kullanılabilir. TCP/IP networkleri üzerinden çalışılabilir ve ip ile erişilebilir. NAS ünitelerinde RAID yapıları kullanılabilir.


**NAS Teknolojisinin Alt Protokolleri :**

  
**1.ISCSI**

- NAS ünitelerinde bulunan lunların TCP/IP network üzerinden storage sunuculara tanımlanabilmesi için kullanılan BLOKSTORAGE TEKNOLOJİSİDİR.
- KVM, ESXI, HypverV de kullanılır ve oldukça popülerdir.
- Sunucularda storagelar istenilen dosya sistemiyle formatlanıp istenildiği gibi kullanılabilir.
- Makineye takılan fiziksel bir disk ile NAS üzerinden makineye ayrılan LUN(Logical Unit Number) aynı şeydir.
- Blokstorage olmasından ötürü çok hızlıdır.
- 3260 portundan çalışır.


>**LUN** = *NAS üniteleri, bir dizi disk sürücüsünden oluşan depolama birimleridir ve bu depolama birimleri üzerinde mantıksal birimlere bölünebilen alanlara sahiptir. Bu mantıksal birimlere LUN (Logical Unit Number) denir.*

>**BLOKSTORAGE =** *Veriyi sabit boyutlu bloklar halinde düzenleyen bir depolama yöntemidir. Her bir blok, belirli bir sabit boyutta veriyi temsil eder ve birbirinden bağımsızdır. Blok depolama genellikle yüksek performans ve esneklik gerektiren uygulamalarda kullanılır.*

  

**2.NFS**

- Open sourcedur.
- Genelde Linuxlarda veya Unixte kullanılır, bir dosya paylaşım protokolüdür.

  

**3.SMB**

- Bir microsoft protokolüdür ve endüstri standartı olarak yerleşmiştir.
- NFS'in alternafidir ve dosya paylaşım teknolojisidir.
- Windows tarafından geliştirilmiştir ve Windowslarda kullanılır.
- Fakat günümüzde samba servisi ile birlikte Linuxlarda da kullanılabilir hale gelmiştir.

  

**4.S3**

- Amazon tarafından geliştirilmiştir.
- Storage tarafında cloud gibi hizmet vermek zorundaysak kullanılır.
- Son kullanıcıya bir disk alanını kullandırır.
- Onedrive ve googledrive'ın alternatifi olabilir.




**2.3 - SAN (Storage Area Network) Üniteleri :**

Çok sayıda diski bir araya getirebilir fakat NAS kadar esnek değildir. Sadece fiber kanal ile çalışır. TCP/IP protokolü ile çalışamaz. Kendine özgü SAN protokolü vardır. SAN switchleri ve HBA adlı sunuculara ve storagelara takılmış olan ethernet kartlarına benzer kartları vardır. 

Bağlantı bu şekilde sağlanır. Eğer SAN'a bağlanılacaksa sunucularda da mutlaka HBA kartları olmalıdır. Performansı yüksek, hızlı ve güvenliği üst seviyededir bu nedenle büyük yapılarda kullanılır. TCP/IP kullanmadığı için ekstra güvenlidir. 25 yıldır var olan eski ve stabil bir sistemdir.

>**HBA(Host Bus Adapter)=** *Bir bilgisayar sistemini veya sunucuyu bir Storage Area Network (SAN) üzerindeki depolama aygıtlarına bağlamak için kullanılan bir adaptördür.*

# WINDOWS

#### Client OS
Son kullanıcı için geliştirilen işletim sistemleridir.

- **WINDOWS 3.1**
  - İlk kullanıcı arayüzü deneyimini sunan sürüm.
- **Windows 95**
  - Windows'un tanındığı ilk popüler sürüm.
- **Windows 98**
- **Windows 2000 PRO**
  - Kurumsal yapılar için kullanıldı.
- **Windows ME**
- **Windows XP**
- **Windows Vista**
- **Windows 7**
- **Windows 8**
- **Windows 10**
- **Windows 11**

#### Server OS
Servisler, hizmetler, web hizmeti, dizin hizmeti ve veri tabanı hizmeti sağlamak için tasarlanmış işletim sistemleridir.

- **Windows NT**
- **Windows 2000**
  - Grafik arayüzü ve Active Directory (AD) ile gelen sürüm.
- **Windows 2003**
- **Windows 2003 R2**
- **Windows 2008**
- **Windows 2008 R2**
- **Windows 2012**
- **Windows 2012 R2**
- **Windows 2016**
- **Windows 2019**
- **Windows 2022**

### SAM (Security Account Manager)
Windows sistemlerinde bulunan kullanıcı veritabanıdır.

- **Administrator**
  - Windows sistemlerdeki en yetkili kullanıcıdır. `root` gibi.
- **Administrators Grubu**
  - Sistemdeki en yetkili kullanıcıları içeren gruptur. `sudoers` gibi.
- **Backup Operators**
  - Sistemde yedek alabilecek kullanıcılar bu grupta bulunur.
- **Users**
  - Tüm kullanıcılar `Users` grubuna dahildir.
- **Local Security Policy**
  - Sistemin yerel güvenlik yapılandırmaları burada yapılır. Standalone çalışan bir sunucuda (SAM veritabanı ile çalışan) grupların yetkileri Local Security Policy'den gelir.

### Active Directory (AD)
Microsoft'un geliştirdiği bir dizin hizmetidir ve bir ağdaki kullanıcıların, bilgisayarların, yazıcıların ve diğer kaynakların yönetimini sağlayan bir veritabanı ve hizmet sunucusu sistemidir. AD alanına giren cihazlar, kimliğini AD üzerinde doğrular ve hem kendi etki alanlarına hem de farklı etki alanlarına erişim sağlayabilirler. Kural oluşturma, politika oluşturma, sistem yönetimi imkanlarını sunar. Merkezi yönetim genelde Windows için kullanılırken kimlik doğrulama her sistem için kullanılmaktadır.

- **Domain**
  - Altında kullanıcı, grup, bilgisayar, OU gibi nesneleri barındıran yapıdır.
- **Child Domain**
  - Domain'in altında bulunan yapı.
- **Forest**
  - Altında bir veya birden çok domain barındıran yapıdır.
- **DC (Domain Controller)**
  - Bir domain'in tüm bilgilerini içeren kontrolcüdür. AD yapıların kalbidir. AD veritabanı Domain Controller üzerinde durur. Yani AD yapısının her şeyini Domain Controller tutar. DC yapısını oluşturduğumuzda AD yapısının oluştuğu anlamına gelir.
- **DNS**
  - Domain ile ilgili isim çözümlerini yapan sistemdir.
- **FQDN**
  - Maksimum 255 karakterden oluşan, birbirinden noktayla ayrılan bir isimlendirme standardı.
- **MMC (Microsoft Management Console)**
- **Kerberos**
  - Active Directory sistemlerindeki güvenli doğrulama sistemi.
- **NTLM**
  - Eski sistemlerde kullanılan doğrulama sistemi. Güvenlik açığı yaratabilir.
- **UNC Path (Uniform Name Convention)**
  - Ağ üzerinde bir dosyaya erişmek için belirtilen yol.

#### Active Directory DNS
AD yapısına aldığımız makineleri ve bunları alırken DC bulma işlemlerini DNS gerçekleştirir. AD'deki isimleri IP'ye, IP'leri isimlere DNS çevirir. DNS durursa AD durur, çalışmaz. AD yapısını ilk kurarken DNS'i de kurmamız gerekir.

- **Active Directory İlk DC Kurulumu**
  - İlk olarak makinemize statik bir IP tanımlamamız gerekiyor (IPv4). Statik IP tanımlarken DNS sunucu olarak kendi IP'sini tanımlıyoruz. Firewall'u kapatmamız gerekiyor. Tercihen daha rahat çalışabilmek için uzak masaüstü izinlerini açabiliriz.
  - Windows 2019 için Server Manager uygulamasına giriyoruz. "Add roles and features" diyerek servis kurulumu penceresini açıyoruz. "Active Directory Domain Services" paketini seçerek yüklüyoruz (next-install).
  - Bu adımları tamamladıktan sonra Server Manager uygulaması içinde sağ üst köşede bir sarı ünlem çıkıyor. Buraya tıklayarak sihirbazı açıyoruz. Burada domain kısmına bir isim vermemiz gerekiyor. İsim verirken FQDN ismi koymamız gerekiyor (deneme.local).
    - **Add a domain controller to an existing domain:** Var olan bir domain için seçmemiz gerekiyor.
    - **Add a new domain to an existing forest:** Var olan bir forest'a yeni bir domain ekleyeceksek seçiyoruz.
    - **Add a new forest:** Yeni bir domain oluşturmamız gerekiyor.
  - **Forest Functional Level:** Windows Server 2016
  - **Domain Functional Level:** Windows Server 2016
  - Aynı seçenek sayfasında "Domain Name System (DNS) server" seçeneğini seçiyoruz ve DNS'i kuruyoruz. Yedekten geri dönmek için bir şifre belirlememiz gerekiyor. "Next" diyoruz ve "Install" diyerek kuruyoruz. Restart ederek Active Directory ortamını ayağa kaldırmış oluyoruz.
  - **Active Directory veritabanı:** NTDS olarak geçer. AD kurulduğunda SAM veritabanı kilitlenip kaldırılır ve NTDS çalışmaya başlar.

- **İlk Kontroller ve Yönetim Araçlarının Tanıtılması**
  - **Active Directory Users and Computers:** AD ile ilgili birçok işlemi buradan yapabiliyoruz.
  - **Active Directory Sites and Services:** Siteleri buradan yöneteceğiz. AD sayfalarını yönetebiliriz.
  - **Active Directory Domain and Trusts:** AD mantıksal yapısında yeni domainler eklediğimizde, child domainler eklediğimizde buradan yönetiriz.
  - **Active Directory ADSI Edit:** İleri düzey işlemlerde buradan yönetim yapacağız.

- **Active Directory Objeleri**
  - AD ortamında objeler bizim her şeyimizdir. AD ortamında göreceğimiz kullanıcı hesapları, bilgisayar hesapları, gruplar, organizasyonel birimler (OU), konteynerlar birer objedir. Hazır olarak gelen gruplar vardır.

- **Active Directory Domain'e Alma İşlemi**
  - Statik IP veriyoruz, DNS olarak AD makinemizin IP adresini veriyoruz.
  - This PC → Properties → Advanced System Settings → Computer Name → Change → Domain seç → Kendi domain ismimizi koyacağız. → Restart

### Linux - Unix AD Kimlik Doğrulaması

- **SSSD**
  - Linux ve Unix benzeri işletim sistemlerinde kimlik doğrulama ve yetkilendirme süreçlerini yönetmek için kullanılır.
  - **Yerel Önbellekleme:** Ağ üzerinden aldığı kimlik doğrulama ve yetkilendirme bilgilerini yerel olarak önbelleğe alır. Ağ bağlantısı olmadan bile kullanıcılar giriş yapabilir.
  - **Offline Desteği:** SSSD, çevrimdışı çalışabilir.

#### Kurulum ve Kullanım
```sh
	apt install sssd-ad sssd-tools realmd adcli
	realm -v discover vigilante.local  # Domain hakkında bilgi
	realm join vigilante.local  # Domain'de kimlik doğrulaması
	pam-auth-update --enable mkhomedir  # Home dizinini aktif etme
```
### Group Policy Nedir?

Group Policy, Active Directory (AD) ortamındaki tüm domainlerdeki cihazlara kısıtlama yapmamızı, yetkilendirme işlemlerini ve mevcut programları gözlemlememizi sağlayan temel bir konfigürasyon aracıdır. AD yapısının temel bileşenlerinden biridir ve çoğu işlem Group Policy Management aracı ile gerçekleştirilir. Varsayılan olarak, oluşturmadığımız bazı Group Policy'ler mevcuttur.

#### Kullanıcı Hesapları
- **Kullanıcı hesapları:** Ali, Veli gibi kullanıcıların AD ortamına giriş yapmalarını ve yetki tanımlamalarını sağlayan objelerdir. Her kullanıcı bir objedir.

#### Bilgisayar Hesapları
- **Bilgisayar hesapları:** CEM PC, Satış PC gibi bilgisayarlara kısıtlamalar uygulanabilir. AD yapısındaki her cihaz bir objedir.

#### Gruplar
- **Gruplar:** Oluşturabileceğimiz veya mevcut olan gruplar vardır. Belirli kullanıcıları üye yapabileceğimiz ve ortak yetki verebileceğimiz gruplardır, bu da yönetimi kolaylaştırır.

#### Organizational Units (OU)
- **OU:** Üzerinde group policy uygulanabilen nesnelerdir. Kullanıcıları bu nesnelere dahil ederek yetki işlemleri yapılabilir.

#### Konteyner
- **Konteyner:** Group policy’ler tanımlanamaz, genellikle basit işlemler için kullanılır ve sınıflandırma amacı taşır.

#### Yönetici Grupları
- **Enterprise Admin Group:** Forest çapında yetkilidir ve anlamlı olabilmesi için birden fazla domain olması gerekir. Tek domain'de Domain Admin Group gibidir.
- **Domain Admin Group:** AD domain çapında yetkilidir. Kullanıcı ekleme, çıkarma ve yetki verme işlemlerini yapabilirler. Neredeyse sınırsız yetkileri vardır.
- **Administrators:** Domain Controller (DC) üzerinde tam yetkiye sahiptirler. AD veri tabanında yetkilidirler.

#### Güvenlik Politikaları
- **Domain Security Policy:** AD kurulumu yapıldığında oluşur ve güvenlik ayarları yapılandırılmıştır. Örneğin, güçlü şifre politikası.
- **Domain Controller Security Policy:** DC'leri etkiler ve basit kullanıcıların giriş yapmasını sağlar.
- **Local Security Policy:** AD kurulmadan önce vardır ve AD domain'ine dahil olmayan makineleri etkiler. Dahil olduktan sonra Domain Security Policy’den etkilenirler.

### Group Policy Yönetim Aracı

Administrative Tools → Group Policy Management üzerinden bulunabilir. Burada Default Domain Policy gibi poliçeler görülebilir ve yönetilebilir. Poliçeler bulunduğu dizini ve dizinin içindeki tüm alt dizinleri etkiler.

Default Domain Policy'ye sağ tıklayarak ve "Edit" seçeneğini seçerek yönetim paneline erişim sağlayabilirsiniz.

- **Security Settings:** Administrative Tools → Group Policy Management → Default Domain Policy → Edit → Computer Configuration → Policies → Windows Settings → Security Settings → Account Policy.
- **Computer Configuration ve User Configuration arasındaki fark:** Yapılan değişikliklerin uygulanma süresi farklıdır (60 dakikayı bulabilir). Anında uygulamak için CMD konsolunda `gpupdate /force` komutu kullanılabilir.

#### Politikalar
- **Password Policy:** Kullanıcıların şifre politikalarını düzenler. Örneğin, minimum şifre uzunluğu ve şifrenin geçerlilik süresi.
- **Audit Policy:** Örneğin, bir kullanıcı 3 kez yanlış şifre girdiğinde hesabın kilitlenmesini sağlar.

>  Computer Configuration'da yapılan değişiklikler bilgisayar objelerini, User Configuration'da yapılan değişiklikler kullanıcı objelerini etkiler.
>  Computer Configuration'da yapılan ayarlar bilgisayar çalıştırıldığında aktif olurken, User Configuration'da yapılan değişiklikler kullanıcı giriş yaptıktan sonra geçerli olur.

#### Kapsam ve Yetkilendirme
- **Scope:** GPO'nun uygulanacağı kapsam.
- **Delegation:** GPO'yu değiştirme yetkisine sahip olan kişiler.

### IPsec

- **IPsec:** Uygulanan kurallara göre TCP/IP paketlerinin şifrelenmesini sağlar.

#### IPsec Protokolleri
- **Client:** IPsec normal çalışır. Karşı taraf kriptolu iletişim isterse iletişim kriptolu olur. Varsayılan olarak kriptosuzdur.
- **Secure Server:** İletişim sadece kriptolu olarak kurulmak istenir. Kriptosuz iletişim sağlanmaz.
- **Server:** IPsec kriptolu iletişim ister. Karşı taraf da kriptolu iletişim isterse iletişim kriptolu olur. Karşı taraf kriptosuz iletişim isterse iletişim kriptosuz olur. Varsayılan olarak kriptolu, gerekirse kriptosuz çalışır.


# DNS

Domain Name System (DNS) FQDN adlarını ip adreslerine çevirir.


##### Çalışma Mimarisi

>Bilgisayarınızın WEB browser Kısmına "www.google.com" yazdığınızda arka planda gerçekleşen işlemler nelerdir?

- Bilgisayar öncelikli olarak bu ismi ip adresine çevirmek ister. Bunun için de ilk olarak kendi üzerinde bulunan host dosyasına(Windows/System32/drivers/etc) bakar.

- Host dosyası boşsa kendi üzerinde tanımlı DNS sunucuya başvurarak FQDN adını ip adresine çevirmesini ister.

- Başvurulan DNS server kendisine yapılan sorgulamanın cevabını biliyorsa direkt cevabı verir ve işlem tamamlanır. Cevabını bilmiyorsa default olarak üzerinde zaten tanımlı olan ROOT DNS sunucularına başvurarak cevabı arar.

- ROOT DNS sunucular kendilerine yapılan sorgulamanın cevabını biliyorlarsa cevabı verirler ve işlem biter. Cevabı bilmiyorlarsa bilene yönlendirme yaparlar. Bu yönlendirme FQDN'in uzantısına göre yapılır.

- Sorgulamayı ilk yapan DNS sunucu yönlendirildiği yere giderek cevabı arar ve istemcisine verir.


==NOT:== Sisteme DNS kurulmasıyla birlikte 13 tane default DNS sunucu gelir. Bu sunucuların 12 tanesi Amerikada 1 tanesi ise Japonyadadır.  DNS üretici bağımsız bir sistemdir ve "**bind**" olarak ifade edilir.


---
##### Forward Lookup Zone

* İsimleri ip'ye çevirir.

* Bu şekilde bir zone oluşturup içine kayıt girmezsek, bu DNS sunucuyu gören hiçbir client bu    zone da tanımlı domaine erişemez.
     - *örn: google.com zone u oluşturup kayıt girmezsek, kimse google'a erişemez, hata gelir.
     - zone un kendi üzerinde tanımlı olduğunu düşündüğü için root DNS lere gidip sormaz direk hata döndürür.
 
-   Bir zone altında belli bir bilgisayarı işaret eden kayıtlara da host kaydı denir.



**Dynamic DNS Kaydı

>DDNS, bir dinamik IP adresine sahip cihazlara erişmek için IP adresi değişikliklerini yönetmek için kullanılır. Bir DDNS hizmeti kullanarak, bir kullanıcı belirli bir alan adını(örneğin,"kullanıcı.ddns.net") ve bu alan adının değişen IP adresini ilişkilendirir.

>Böylece, her IP adresi değiştiğinde, kullanıcı sadece DDNS sağlayıcısına yeni IP adresini bildirir ve bu yeni IP adresi otomatik olarak belirtilen alan adı ile ilişkilendirilir.

>Bu, özellikle uzaktan erişim, web sunucuları veya IP kameralar gibi durumlarda kullanışlıdır. Kullanıcılar, değişen IP adresleri nedeniyle erişim sorunları yaşamadan bu cihazlara sabit bir alan adı üzerinden erişebilirler.


**CName Nedir ?**

>CName kaydı var olan bir host kaydına diğer kayıtları yönlendirmenizi sağlar. Bu şekilde de tek bir host kaydını değiştirerek ona yönlendirilmiş tüm host kayıtlarını değiştirebileceğimiz için sonrasında yaşanabilecek ip değişiklikleri için önden yapacağınız bu işlem işleri büyük ölçüde kolaylaştırır.


**MX Kaydı**

>Mail sunucuyu işaret eden kayıttır.

--- 



##### Reverse Lookup Zone

* Ipleri isime çeviren zonedur.

* Mail sunucularda spamı anlamak için kullanılan en klasik yöntemdir.

* Reverse kaydını ISP'ler oluşturur.
    - *Reverse Lookup Zone kaydının altında PTR (pointer) kayıtları oluşturulur.
    - *Bu kayıt ip adresleriyle oluşturulur.



--- 


##### Forwarder

 - Bir DNS e bilmediği isimleri sorgulaması için başka DNS i göstermeye Forwarder denir. 
 
 - Forwarder girdiğimizde DNS servisi root DNS lere gitmez, Forwarder ın yönlendirdiği yere gider.
 
 - Kurumsal mimarilerde (kamu kurumları vs.) DNS leri root a değil forwarder ile Türk telekom DNS leri gibi DNS lere yönlendirip oradan cevap alırız.



**Conditional Forwarder**

- Domain bazlı olarak bilmediklerini başkasına sor.  

- Örneğin google.com ile ilgili bir sorgulama gelirse git şu DNS e sor gibi.  

- Şartlı yönlendiricidir.  

- Belirli DNS sorgularının belirli bir alan adı için başka bir sunucuya gönderilmesini sağlayan bir yapılandırmadır.


---



##### Primary Zone

>Zone veri tabanının hem okunabilir hem yazılabilir kopyasını tutar. Hem kayıt oluşturabiliriz, hem de DNS in sorgulamalarına cevap verebileceği zone tipidir.

##### Secondary Zone 

>Sadece okunabilir kayıt tutulur, içine kayıt giremeyiz. İlk kayıt için uygun değildir. Master(primary) a ihtiyacı vardır.



Primary                                  Secondary
|-DNS1-|         ---------->       |-DNS2-|


- *DNS 2 cevapları DNS 1'den alır ve o şekilde döndürür.
- *DNS 1'de değişiklik olursa DNS 2'de de uygulanır.*
- *Değişiklikler DNS 2'ye **serial numbera** göre gider.


**Serial Number** 

>Secondary zone a veri transferi yaparken değişiklik olup olmadığını gösteren parametredir. Serial number büyüdüğünde secondary zone değişiklik olduğunu anlar ve değişikliği kendine çeker.




**SOA (Start Of Authority)**

>Secondary zone ile ilgili ayarların yapıldığı,  primary den secondary e veri transferi yapılırken değişiklik olup olmadığını gösteren,  ne kadar zamanda bir kayıt yapılacağını gösteren, expires(süresi dolma) ve TTL ömrünü tutan kayıt tipleridir.
>
  ==NOT:== Time To Live (TTL) = Cache'de kalma ömrü.



 >**Disable Recursion :** DNS sadece kendi üzerinde bulunan zone lar için cevap vercektir ve forwarding yapmayacaktır.
 >
   ==NOT:== Linuxa bir DNS(bind) kurarsak default olarak recursion kapalı olarak gelir.


>**Round Rubin :** Enable durumda ise ve aynı fqdn farklı ip leri gösteriyorsa aralarında döndürerek yanıt verir.


> DNS cache'i temizlemek için `ipconfig /flushdns` komutu kullanılır.


---


##### Active Directory Integrated Zone

- DNS kayıtlarının active directory veri tabanında tutulmasıdır. 

- DNS ve Active Directory yönetiminin tek bir platformda merkezi olarak yapılabilmesidir. Bu, yönetim süreçlerini basitleştirir ve tutarlılığı artırır. Ancak, bu avantajları elde etmek için DNS sunucularının Active Directory domain controller'ı olması gerekir. 

- Bu şekilde secondary zone a ihtiyaç duyulmaz. DC ler arasında bu kayıtlar replike edilir.



**Secure - None Secure Dynamic Updateler**

-  **Secure Only :** Domaine dahil olan makineler kendi kayıtlarını (updateleri) otomatik olarak zone  altına düşebilirler. 
    - *Bir makinenin kaydını otomatik olarak düşmesini istiyorsak : `ipconfig /registerdns`

-  **None Secure And Secure :** AD ye dahil olsun ya da olmasın her makine DNS kaydını zone altına düşebilir.

-  **None :** Hiç kimse kaydını düşemez.



==NOT:== Active Directory ismi için oluşturulmuş zone lar (academy.local gibi) secure dynamic update lere açık olmak zorundadır. Yoksa AD düzgün çalışmaz çünkü istemciler kayıtlarını düşemezler.



**AD Zone'u SRV Kayıtları** 

- Zone altında bulunan kayıtlardır. 
- AD kurulduğu andan itibaren DC tarafından otomatik olarak oluşturulan kayıtlardır. 
- AD nin sağlıklı olması için srv kayıtlarının sağlıklı olması gerekir.


**NSLOOKUP**

- DNS sunucuyu direk olarak sorgulamamızı sağlayan araç. cmd'de `nslookup` komutu yazdığımızda sorgularız. 
- Server 8.8.8.8 yazdığımızda google ın DNS ini sorgularız. 
- Help yazdığımızda komutların açıklamalarını görürüz. 
- Gerçek hayatta DNS te sorun olup olmadığını anlamak için de kullanırız.


**Cache**

- DNS üzerinde olmayan kayıtları forwardera ya da root DNS lere sorar. 
- Bu işlemi yaptıktan sonra da bunu isim cachesine yazar. 
- Bir daha sorgulama geldiğinde cachesinden cevap verir. 
- Clear cache dediğimizde önbelleği temizler.

==NOT:== AD zone u ya da server location kayıtlarını silersek, zone u yeniden oluşturmamız gerekir.


**Netlogon**

>Netlogon servisi, etki alanı denetleyicileri arasında oturum açma bilgilerini senkronize etmek, etki alanı politikalarını uygulamak ve güvenlik duvarı ayarlarını iletmek gibi önemli görevleri de yerine getirir.


