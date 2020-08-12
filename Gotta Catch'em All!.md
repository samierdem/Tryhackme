# Gotta Catch'em All! by Tryhackme
<a href="https://tryhackme.com/room/pokemon" rel="nofollow">Odaya Buradan Ulaşabilirsiniz.</a> 

İlk olarak VPN açıp makinayı çalıştırıyourm.

Bana verdiği IP adresi şu şekilde = 10.10.55.124 (sizde bu farklı olacaktır.)

Şimdi NMAP taraması yapıyorum

namp -sV -sC -Pn  10.10.55.124

tarama sonucu şu şekilde;

![Screenshot_2](https://user-images.githubusercontent.com/34964480/90057828-9d228f80-dce9-11ea-80d4-f2b083923684.png)


Burada görüyorum ki 22 ve 80 portları açık. 

10.10.55.124 adresine gidip sayfa kaynağını incelerken ssh kullanıcısı ve şifresinin yer aldığını düşündüğüm bir bölüm görüyorum ve bunu deneyeceğiz.

![Screenshot_5](https://user-images.githubusercontent.com/34964480/90057418-0b1a8700-dce9-11ea-9ab0-79b04bb60e47.png)


Ek olarak konsola gidince bir kullanıcı listesine ulaşıyorum.(Biliyorsunuz ki konsola F12 ile ulaşabilirim)

![Screenshot_1](https://user-images.githubusercontent.com/34964480/90057604-4cab3200-dce9-11ea-9741-5cc72b3523f3.png)

SSH için bulduğum kullanıcı adı ve şifremi deniyorum başarılı oldum.

![Screenshot_3](https://user-images.githubusercontent.com/34964480/90058126-fee2f980-dce9-11ea-8bac-a0a461f8de04.png)

Burada sırasyla ```ls``` ```cd Desktop``` ```ls``` komutlarını girdiğimde PokEmOn.zip görüyorum.

Şimdi bunu zipten çıkarmak için ```unzip PokEmOn.zip ``` komutunu giriyorum ardından ```ls``` komutunu girince P0kEmOn klasörünü zipten çıkmış halde görüyorum.

Şimdi bu klasöre girelim ```cd P0kEmOn ``` ardından ```ls``` burada görüyorum ki ```grass-type.txt``` var.

Bunu ```cat grass-type.txt``` komutu ile açalım.Burada şifreli bir bayrak var.

https://dencode.com/ adresine giderek bu şifreli bayrağı yağıştırıyorum ve ilk sorumun cevabını elde ediyorrum.

İkinci soruda ise benden ```Water-Type Pokemon``` isteniyor.

```locate``` komutu ile ```water``` araması yapıyorum karşıma çıkanlar arasında ```water-type.txt``` görüyorum ve  ```cat /var/www/html/water-type.txt``` komutu ile açıyorum burada ikinci sorumun cevabını buluyorum.

![Screenshot_4](https://user-images.githubusercontent.com/34964480/90061649-183a7480-dcef-11ea-939e-2fdd7c1d5bce.png)

![Screenshot_6](https://user-images.githubusercontent.com/34964480/90061774-4b7d0380-dcef-11ea-82eb-9a92b5c59961.png)

Ama cevabı decode etmem gerekli.Bunun için https://cryptii.com/ adresine gidiyorum.

![Screenshot_7](https://user-images.githubusercontent.com/34964480/90063055-70727600-dcf1-11ea-93b7-274cbc9f6b22.png)

Böylece ikinci soruyuda geride bıraktık şimdi üçüncü soru için ```locate fire-type ``` araması yapıyorum ```/etc/why_am_i_here?/fire-type.txt``` yolunu görüyorum 
```cat /etc/why_am_i_here?/fire-type.txt ``` komutu ile şifreli bayrağı buluyorum.
Yeniden https://dencode.com/ adresine giderek bayrağı yapıştırıyorum aşağıda ```Base64``` olarak çevrilmiş hali gözüküyor.Böylece üçüncü soruyuda geride bıraktık.



