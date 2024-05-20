# NETWORK

## Network Nedir ?
> - Bir bağlam yardımıyla (kablo, wireless) cihazların birbiriyle iletişim kurmasını sağlayan ortam. Temelleri, Amerikan Savunma Bakanlığı Hava Kuvvetleri tarafından geliştirilen ARPANET ile atılmıştır.
> - Fiziksel ve yazılımsal olmak üzere 2 boyuttan oluşur. 

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
- **2. Data-Link - Veri Bağlantı** : Ağdaki cihazlar arasında doğrudan veri transferini yönetir ve hataları düzeltir.
	- Paketlere MAC adresi verilir ve kuyruk kısmına hata kontrol değeri yazılır.
- **1. Physical - Fiziksel** : Verinin fiziksel ortamda nasıl iletileceğini belirler.
	- Data bitlere dönüştürülür ve iletim sağlanır.


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
- mert: kullanıcı adı
- x: parolanın /etc/shadow a taşındığını belirtir.
- 1000: kullanıcı idsi
- 1000: kullanıcının grup idsi
- mert:/home/mert: mert kullanıcısının dizini
- /bin/bash: mert kullanıcısının bash kullanım hakkı 

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
	- ext için: `resize2fs /dev/sdx`
	- xfs için: `xfs_growfs /dev/sdx`


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

**SCP** (Secure Copy Protocol) = SSH protokolü üzerinden güvenli dosya transferi.

- scp C:\Users\Ali Asker\Desktop\ubuntu-22.04.3-live-server-amd64.iso ali@192.168.17.177/linux_path windowstaki bir dosyayı scp ile linuxa gönderir.

