# Veri Girişi

BASH scriptini çalıştırdıktan sonra klavyeden bir girişe ihtiyacımız olabilir. Örneğin klavyeden bir sayı girilmesi istenebilir. Bu gibi durumlarda kullanacağımız girdi komutu **read** komutudur.

**read** komutu ile klavyeden bir giriş alınır ve bu giriş bir değişkende tutulur. Kullanımına örnek bir kodu aşağıda görebilirsiniz.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

echo "Klavyeden bir sayı girin:"
read sayi
echo "$sayi"
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
Klavyeden bir sayı girin:
5
5
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Elbette yalnızca sayı değil karakter de girilebilir. Örneğin isim yazılması istenebilir.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

echo "Kendini Tanımla:"
read name

echo "Hoşgeldin" $name
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
Kendini Tanımla:
Volkan
Hoşgeldin Volkan
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Sayı istediğimizi kabul edelim. Bu sayı ile işlem yapabiliriz değil mi? Örneğin girilen sayının karesini ekrana bastırabilir miyiz? Evet, bastırabiliriz. Ancak ilk denemede büyük olasılıkla hata alacağız.

Eğer girilen sayının karesini hesaplamak istiyorsak sayıyı kendisi ile çarpmalı ve bunu **echo** komutu ile ekranda göstermeliyiz.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

echo "Sayı gir:"
read sayi

sayi=$sayi*$sayi
echo "Karesi:" $sayi
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
Sayı gir:
3
Karesi: 3*3
```
{% endcode-tabs-item %}
{% endcode-tabs %}



Görüldüğü gibi çarpma işlemi gerçekleşmiyor. BASH ile aritmetik işlemler yapmanın yolu bu değil. Eğer sayısal işlem yapacaksak **let** komutundan faydalanmalıyız. Sonraki bölümde de bunu göreceğiz. Ancak sonraki bölüme geçmeden önce **read** komutu ile ilgili daha fazla örnek ve ihtiyacımız olan parametreleri görelim.





