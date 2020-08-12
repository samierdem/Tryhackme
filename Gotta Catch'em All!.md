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

Şimdi bu klasöre girelim ```cd P0kEmOn ```



