# Network & Security (IPv4-IPv6-ACL)
![image](https://user-images.githubusercontent.com/56456793/202238101-b8c2980a-4c0c-421a-8e83-8e7c0c0f8d6d.png)


![image](https://user-images.githubusercontent.com/56456793/202238785-fd2c10d4-242f-44c1-a670-c5e444ca907c.png)
*NOT:* Projenin görüntülenmesi için öncelikle «Cisco Packet Tracer» programını cihazınıza kurmanız gerekir. 


**SENARYO**<br>
-Omurga IPv4 ve IPv6 dual stack çalışacak<br>
-Dynamic Routing OSPF ile gerçeklenecek<br>
-Hem IPv4 hem de IPv6 omurga ACL ile sadece servis portlarından hizmet verecek<br>
-Diğer tüm portlar kapalı olacak<br>

**Projede Kullanılan Cihazlar**
<br>- 2811 Router (3 adet)
<br>- 2960-24TT Switch (2 adet)
<br>- 3550-24PS Multilayer Switch (1 adet)
<br>- Server-PT(WEB(tcp80)) (1 adet)
<br>- Server-PT(DNS(udp 53)) (1 adet)
<br>- PC-PT (1 adet)
<br>- Laptop-PT (1 adet)
<br>

*NOT:* Proje yapım aşamasında testler her aşamada her cihaz için yapılmıştır. Bu sunumda örnek olması açısından sadece Router1 için ekran görüntüleri yer almaktadır
<br>

--------------------------------------------------------------------------------------------------------------------------------------------------------------

**IPv4 Kısmı**
--------------

**Cihazlara ip adreslerinin verilmesi**<br>
Desktop->IP Configuration içerisinde ipv4 ve ipv6 ip adresleri ile Default Gatewayler verildi.
![image](https://user-images.githubusercontent.com/56456793/202242102-43a5aefd-5b60-4541-8f19-3d85e4b6d814.png)
<br>

**İNTERFACE CONFİGURATİON**

**IPv4 İnterface configuration (Router 0)**

![image](https://user-images.githubusercontent.com/56456793/202244284-13e545ed-c76d-4e7f-a65c-5109b201cbab.png)

**IPv4 İnterface configuration (Router 1)**

![image](https://user-images.githubusercontent.com/56456793/202244959-7503575e-4aaf-442d-a0de-83fe1b841154.png)
<br>
![image](https://user-images.githubusercontent.com/56456793/202245616-957a3ba5-8b75-4a0c-8f2a-38edf4021f65.png)
<br>
<br>
192.168.2.2 ip ye sahip cihaza ping testi yapıldı ve bağlantının sağlandığı görüldü
<br>
![image](https://user-images.githubusercontent.com/56456793/202245688-6e47c557-1f88-41d8-84ba-bdb73510d4f3.png)
<br>
<br>

**IPv4 İnterface configuration (Router 2)**




![image](https://user-images.githubusercontent.com/56456793/202246352-e6194b90-c3af-4f89-9e68-385715ba48c5.png)

<br>

<br>

**OSPF**
<br>
Router0, Router1 ve Router2 arasında bağlantı oluşturulması için OSPF protokolü seçildi
<br>

**OSPF IPv4 (Router0)**

![image](https://user-images.githubusercontent.com/56456793/202251920-2a54e762-5b9e-4be9-9667-ab610c6652ec.png)

<br>

**OSPF IPv4 (Router1)**
<br>
![image](https://user-images.githubusercontent.com/56456793/202253605-17b32f0c-9d94-4170-8b6e-41546c131414.png)
<br>
do show ip rote komutu ile OSPF bağlantısı kontrol edildi ve bağlantının sağlandığı görüldü
<br>
![image](https://user-images.githubusercontent.com/56456793/202253887-67a42842-bb8d-458e-8e9e-3dd07bf63c02.png)
<br>
Ping testi yapıldı
<br>
![image](https://user-images.githubusercontent.com/56456793/202254099-b0434c20-d13a-4fcc-a759-020ce8a594b4.png)
<br>
**OSPF IPv4 (Router 2)**
<br>
![image](https://user-images.githubusercontent.com/56456793/202254392-d5a92752-6556-404c-90eb-f3a36c5d2306.png)
<br>

**DNS AYARLANMASI**
<br>
DNS(udp 53) Server’ının IPv4 adresi farklı networklerde bulunan Laptop0 ve PC0 ın DNS Serverine verildi. Daha sonra DNS>Services>DNS kısmına WEB serverinin IP’si aşağıdaki gibi verildi
<br>
![image](https://user-images.githubusercontent.com/56456793/202255340-3c26622c-7dc8-450f-b3d5-7e8617e46b85.png)
<br>
**Access-List ve Portların kapatılması**
<br>
Router 0
![image](https://user-images.githubusercontent.com/56456793/202255720-84bb4f03-6228-4977-bf34-63c706bad300.png)
<br>
İşlemler tamamlandıktan sonra www.cisco.com adresine erişimin sağlandığı görülüyor.
<br>
![image](https://user-images.githubusercontent.com/56456793/202256011-934e8f8f-2f5e-48e6-a2b5-58dd771c727f.png)


<br>

**IPv6 Kısmı**
--------------
<br>

**IPv6 Interface Configuration (Router 0)**
<br>
![image](https://user-images.githubusercontent.com/56456793/202258828-ea9ae416-ae2a-4440-bd83-dc2328b8733f.png)


<br>
**IPv6 Interface Configuration (Router 1)**
<br>

![image](https://user-images.githubusercontent.com/56456793/202257790-427bcf2b-f8b7-4724-8ff6-394545b0552b.png)
<br>
Ping Testi
<br>
![image](https://user-images.githubusercontent.com/56456793/202257902-32422427-0183-4316-a4c3-320a3c312f3c.png)
<br>
**IPv6 Interface Configuration (Router 2)**
<br>

![image](https://user-images.githubusercontent.com/56456793/202258196-d8f06afd-3515-4712-8544-a515eb7592df.png)

**OSPF**
<br>
**OSPF IPv6 (Router 0)**
<br>
![image](https://user-images.githubusercontent.com/56456793/202259289-98f57dad-15c7-48c1-a0f8-03cc23685fbb.png)

<br>

**OSPF IPv6 (Router 1)**
<br>

![image](https://user-images.githubusercontent.com/56456793/202259585-69805558-d4cf-47d7-acf3-1bd1b316b451.png)

<br>
OSPF kontrolu
![image](https://user-images.githubusercontent.com/56456793/202260216-1ae49618-5c7e-42b8-a271-51110c57cfee.png)

Ping kontrolü
![image](https://user-images.githubusercontent.com/56456793/202259836-81745bf0-5eca-49c5-a8e1-3fae95d7fd6f.png)



**OSPF IPv6 (Router 2)**

![image](https://user-images.githubusercontent.com/56456793/202260454-32d2b07d-27ed-4981-8237-70b950c9e262.png)

**DNS AYARLANMASI**

<br>
DNS(udp 53) Server’ının IPv6 adresi farklı networklerde bulunan Laptop0 ve PC0 ın DNS Serverine verildi. Daha sonra DNS>Services>DNS kısmına WEB serverinin IP’si aşağıdaki gibi verildi 


![image](https://user-images.githubusercontent.com/56456793/202260735-f9db8425-18fb-44d1-bc26-8afd8be45aab.png)


**Access-List ve Portların kapatılması**

![image](https://user-images.githubusercontent.com/56456793/202261077-686e4995-eb47-4b46-9172-96318a2423dd.png)


![image](https://user-images.githubusercontent.com/56456793/202260905-c6c5c8a0-678d-41a9-9289-fc5f042077d3.png)

