# Temel Ağ Notları

### Security Devices

1. **Firewall**
- Bir güvenlik duvarı
- Birden fazla OSI katmanında olabilir (özellikle 2,3,4,7)
- Ağa giren her paket incelenir, paket bir kural ile eşleştiğinde kural belirtilen şekilde uygulanır.
- Harici bağlantıların dahili bağlantılar ile karışmasına izin vermez.

2. **Saldırı Tespit Sistemi (IDS)**
- Ağa yönelik saldırıları ve ağ ihlallerini tespit eder.
- Amaç; ağ yönetiicisini bilgilendirmek. (günlük dosyalar, kısa mesajlar, e-posta bildirimleri)
- Saldırı önlenemez. IDS bir kopya alır, ağdaki trafiğin bir dizi standarda göre değerlendirilebilmesini sağlar.
- Ana bilgisayar tabanlı saldırı.

3. **Saldırı Önleme Sistemi (IPS)**
- ihlal ve saldırıyı durdurmak için tasarlanan aktif bir sistem.
- Amaç; ağın zarar görmesini engellemek.
- IPS'nin çalışması için ağ segmentindeki tüm trafiğin IPS'ye girerken IPS'den geçmesi gerekir.
- Güvenlik duvarı olan bir yönlendirici ile hedef arasındaki bağlantı -> tüm trafik IPS üzerinden akar.
- IP adresleri engellenebilir, savunmasız arayüzler kapatılabilir, ağ oturumları sonlandırılabilir.

**Virtual Private Network (VPN)**
- İzin verilen VPN bağlantısının türüne uygun olarak uygun tünelleme ve şifreleme
- Birden fazla OSI katmanı (özellikle 2,3,7)
- Katman 7 --> Proxy tabanlı VPN'ler ve SD-WAN çözümleri.
- Katman 3 --> Güvenli tünel üzerinden IPsec şifrelemesi sağlar.

#### Optimizasyon ve Performans Cihazları

1. ***Load Blancer***
- içerik anahtarı, içerik filtreleyici
- Birden fazla ana bilgisayar arasındaki yükü dengelemek için kullanılan bir ağ aygıtıdır.

2. ***Proxy Server***
- Bir istemci makinesi adına kaynaklar talep eden cihaz.
- İstemci (kullanıcı) ile internet arasında aracılık yapan bir sunucudur.
- Gerçek IP adresini gizler, kötü amaçlı içerikleri filtreler.
- Hız ve bant genişliği tasarrufu

### Network Services and Applications I.

1. ***Basic Network***
2. ***Ağ protokolleri***

Özel ağ veya VPN, uzak ana bilgisayarlar tarafından şifreli bir bağlantı yoluyla özel bir ağa erişmek için kullanılır.
VPN bağlantısı sağlandıktan sonra uzak bilgisayarlar yerel bir ana bilgisayar olarak görülür.

#### VPN Types
1. The site-to-site VPN
2. Remote access VPN (host-to-site VPN)
3. Host-to-host VPN(SSL VPN)

***VPN ve Tünelleme teknolojileri ile ilişkili protokeller***

##### Internet Protocol Security (IPSsec)

- OSI modelinin 3. katmanında ve daha üst katmanlarda çalışır.
- VPN bağlantısını güvence altına almak için IPsec, kimlik doğrulama başlık protokolüyle birlikte çalışabilir.

##### Authentication Header (AH)

- IPsec protokolünün bir parçasıdır. Kimlik doğrulama hizmeti sunar, şifreleme sunmaz.

##### Encapsulating Security Payload (ESP)

- Kimlik doğrulaması yapar ve paketleri şifreler. VPN bağlantılarında sıkça kullanılır, IPsec protokolünün parçasıdır.

##### Generic Routing Encapsulation (GRE)

- Bir ağ üzerinden farklı protokolleri taşıyabilmeyi sağlayan bir tünelleme protokolü.
- Şifreleme sıkıştırma gibi özellikleri yok, site-to-site VPN tünelleri.
- *Kapsülleme*: GRE bir protokolün (ex: MPLS) başka bir protokol üzerinden taşınmasını sağlar. Örneğin IPv6 trafiği IPv4 üzerinden gönderilir.
- *Tünelleme*: GRE iki ağ cihazı arasında sanal bir tünel oluşturur. Bu tünel taşıdığı trafiği kapsülleyerek gönnderir.

##### Point-to-point tunelling protokol (PPTP) (eski bir VPN protokolü)

- PPTP, PPP (point-to-point protokol) üzerinden veri kapsülleyerek güvenli bir bağlantı oluşturur. MPPE şifreleme kullanır.
- Güvenlik açıkları, zayıf şifreleme !

**SSL (Secure Sockets Layer) ve TLS (Transport Layer Security)**
- İnternet üzerinden güvenli veri iletimi sağlayan şifreleme protokolleridir.
- TLS, SSL'nin daha güvenli devamı şeklinde geliştirildi.
- TLS, OSI modelinin 5. katmanında ve üstünde çalışır.
- SSL artık kullanılmıyor, HTTPS ve VPN bağlantıları TLS ile korunuyor.

### Ağ Protokolleri 
Cihazların birbirleriyle iletişim kurmasını sağlayan standartlar bütünü.

1. *Transmission Control Protocol (TCP)*: Güvenilir, bağlantı odaklı veri iletimi sağlar.
2. *User Datagram Protocol (UDP)*: Daha hızlı ancak güvenilirliği düşük veri iletimi yapar.
3. *Internet Protocol (IP):* Cihazlara adres atayan ve veri paketlerini yönlendiren protokoldür.
4. *HyperText Transfer Protocol / Secure (HTTP/HTTPS)*: Web tarayıcılarıyla sunucular arasındaki iletişimi sağlar. HTTPS, şifreli ve güvenlidir.
5. *File Transfer Protocol (FTP)*: Dosya aktarımı için kullanılır.
6. *Domain Name System (DNS)*: Alan adlarını IP adreslerine çevirir.
7. *SMTP/IMAP/POP3*: E-posta gönderme ve alma protokolleridir.

#### Network Access Services / Other Servicez and Applications

1. **Network Interface Controller (NIC)**
- Bir bilgisayarın veya cihazın ağa bağlanmasını sağlayan donanım bileşeni.
- OSI modelinin 2. katmanı veri bağlantı katmanında çalışır.
- Hangi ağ protokollerinin kullanılacağını belirler. (ethernet haberleşmesi, point-to-point)

2. **Remote Authentication Dial-In User Service (RADIUS)**
- Kimlik doğrulaması için kullanılan uzaktan erişim hizmeti.
- AAA protokol (Authentication, Authorization, and Accounting): Kimlik doğrulama, yetkilendirme, hesap verilebilirlik.
- dezavantaj: son kullanıcının şifresi ile şifrelenir.

3. **Terminal Access Controller Access-Control System Plus (TACACS+)**
- Büyük ölçekli ağlarda kullanıcı erişimini yönetmek için kullanılır. 
- Daha güvenilir veri aktarımı (TCP üzerinden port 49)
- RADIUS'dan farklı olarak daha üst düzey güvenlik.
- Tam şifreleme desteği sunar (RADIUS gibi sadece şifreyi değil, tüm oturum verisini şifreler.)

**Remote Access Server (RAS)**
- Uzaktan erişim bağlantısı için gerekli yazılım ve donanım kombinasyonunun tamamı.
- Genellikle kurumsal ağlarda veya ISS'lerde (İnternet Servis Sağlayıcılar) kullanılır.

##### DHCP in the Network

***Dynamic Host Configuration Protocol (DHCP)***: Ağdaki cihazlara otomatik olarak IP adresi, alt ağ maskesi, varsayılan ağ geçidi ve DNS sunucusu gibi ağ yapılandırma bilgilerini atayan bir protokoldür.
- Cihazların ağ üzerinde iletişim kurmasını sağlayan iki farklı yöntem. (statik ve dinamik IP)
 
1. ***Statik IP Yapılandırması***:
- Ağ yönetici tarafından elle yapılır.
- Adres, ağ yöneticisi değiştirmediği sürece sabi kalır.
- IP yapılandırmalarının zamanla güncellenmeleri gerekir.
- DNS yapılandırması veya port yönlendirme gibi ayarlar daha basit.
dejavantaj: hataya açık.

2. ***Dinamik IP Yapılandırması***: 
- Otomatik atanır.
- İşlem DHCP sunucusu tarafından yapılır.
- Adres yönetimi kolaylaşır.
- Kullanıcı ve yönetici müdahalesi gerekmez.

##### DHCP nasıl çalışır?
1. ***DHCP Discover (keşif mesajı)***: 
- Cihaz IP adresine ihtiyaç duyar.
- Cihaz bir keşif mesajı gönderir.
- Bu mesaj cihazın IP adresi talebini içeren bir yayın (broadcast) mesajıdır.
- Bu yayın mesajı ağa bağlı tüm cihazlara iletilir.

2. ***DHCP Offer (teklif mesajı)***: 
- Ağda bulunan DHCP sunucusu keşif mesajını alır.
- Sunucu kullanılabilir bir IP adresi belirler.
- Bu adresi cihaza teklif etmek için bir teklif mesajı gönderir.
- Bu mesajda; önerilen IP adresi, alt ağ maskesi (subnet mask), varsayılan ağ geçidi (default gateway) ve DNS sunucusu bilgileri yer alır.

3. ***DHCP Request (talep mesajı)***: 
- Cihaz sunucuda geçe teklif mesajını kabul ederse DHCP, reques adında mesaj gönderir.

4. ***DHCP Acknowledgment (onay mesajı)***: 
- DHCP sunucusu gelen talebi onaylar ve cihaza onay mesajı gönderir. 
- Mesajda cihazın IP adresini kullanabileceği ve diğer yapılandırma verileri yer alır. 
- Cihaz artık ağda bu IP adresiyle iletişim kurabilir.

DHCP bileşenleri:


### DNS Service








    
