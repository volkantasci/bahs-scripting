# Değişkenler

Eğer halihazırda bir programlama dili biliyorsanız değişken kavramına zaten aşinasınızdır. Ancak değişken tanımlama ve kullanma biçimleri her dilde farklılık gösterebileceğinden bu bölümü atlamadan okumanızı öneriyorum.

Değişkenler isimlerinden de anlaşılacağı üzere kod içerisinde her an farklı değerler tutabilen, içlerinde veri sakladığımız 'şeyler' dir. Şimdilik şeyler diyerek fazla yormadan anlatıma devam edelim.

Değişkenlere istediğimiz değerleri atayabilir ve bu değişkenleri istediğimiz şekillerde kullanabiliriz. Örneğin kendi ad ve soyad bilgilerimizi birer değişkene aktaralım ve bu değişkenleri sırayla ekrana bastıralım. Ekrana yazı yazmak için önceki bölümde echo komutunu kullanmıştık, yine aynı komutu kullanacağız.

Kodlarımızı yazdıktan sonra dosyamızı çalıştırılabilir hale getirip terminalden çalıştırıyoruz. Bu işlemi önceki bölümlerde detaylıca incelediğimizden dolayı yeniden aynı şeyleri tekrar etmiyorum. Bundan sonra kod ve çıktı gördüğünüz zaman ne yapacağınızı biliyorsunuz.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/usr/bin/bash

ad="Volkan"
soyad="Taşcı"

echo $ad
echo $soyad
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
Volkan
Taşcı
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Yukarıdaki alanda 'Program' ve 'Çıktı' sekmelerini kullanarak kodlara ve çıktılara erişebilirsiniz.
{% endhint %}

Değişkenleri tanımlarken dikkat etmeniz gereken çok önemli bir nokta var. Değişken isimleri ve değerleri arasında eşittir operatörünü kullanıyoruz ancak bu operatör ve solundaki, sağındaki bilgiler arasında boşluk olmamalıdır. Eğer aşağıdaki gibi yazım söz konusu olursa hata alırız.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

ad = "Volkan"     #Hatalı Yazım
soyad = "Taşcı"   #Hatalı Yazım

echo $ad
echo $soyad
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
deneme.sh: satır 3: ad: komut yok
deneme.sh: satır 4: soyad: komut yok
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Değişken tanımlama işlemini hallettik diye düşünüyorum. Bu konuda söylenebilecek son bir şey var, değişken isimlerinin kuralları. Değişken isimleri BASH dilinde bir anahtar kelimeye denk gelse dahi sorun yaşamayız. Oysa pek çok programlama dili için bu durum olmamalıdır. Ancak BASH dilinde istersek '**echo**' isminde değişken oluşturabiliriz.

Bir kural olarak değişken isimleri sayı ile başlayamaz. Ancak bir değişken ismi sayı ile sonlanabilir. Ya da bir değişken isminde sayı yer alabilir. Örnek olarak aşağıdaki kod bloğuna bakalım.

```bash
degisken=""        # Doğru Yazım
degisken1=""       # Doğru Yazım
ben1degiskenim=""  # Doğru Yazım
echo=""            # Doğru Yazım
if=""              # Doğru Yazım
1degisken=""       # Hatalı Yazım
ben.degiskenim=""  # Hatalı Yazım
```

Yukarıda birkaç örnek ile değişken ismi kurallarını anlatmaya çalıştım. Umarım anlaşılmıştır.

Değişkenlerin bir de çağrılması var tabi. Kabuk dosyamıza tekrar bakalım, $ işaretini değişkenleri çağırırken kullandığımızı görüyoruz. BASH dilinde anahtar kelimeleri de değişken olarak kullanabilmemizin sebeplerinden birisi bu. Çünkü anahtar kelimeler ile değişkenler birbirine karışmıyor. Değişkenleri çağırıyorsak eğer başında dolar \($\) işareti kullanıyoruz ve BASH bizim bir değişkenden bahsettiğimizi anlıyor.

Değişkenlerimizi yukarıda kullandığımız gibi şu şekilde de kullanabiliriz:

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/usr/bin/bash

yazi1="Merhaba"
yazi2="Dünya"

echo "$yazi1 $yazi2"
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
Merhaba Dünya
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Yeri geldikçe değişkenleri bol bol kullanacağımızdan dolayı başlangıcı üzerinde çok durmuyorum. Sonraki bölümde sistem değişkenleri ve kullanıcı değişkenleri şeklinde iki sınıfta inceleme yapacağız.

