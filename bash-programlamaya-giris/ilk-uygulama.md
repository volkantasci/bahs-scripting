# İlk Uygulama

Bu bölümde ilk uygulamamızı yazacağız. Adettendir, herhangi bir programlama dili öğrenilirken ilk olarak ekrana 'Merhaba Dünya' yazılır. Biz de bu geleneği bozmadan ekrana 'Merhaba Dünya' yazan bir uygulama yapacağız.

BASH dilinde ekrana bir şey bastırmak için kullanılan komut echo komutudur. Elbette daha derin inceleyeceğiz ancak şimdilik üstünkörü bir şekilde ekrana bir çıktı bastırmak için yazıp geçelim.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

echo "Merhaba Dünya"
```
{% endcode-tabs-item %}
{% endcode-tabs %}

hello.sh dosyasını yukarıdaki biçimde doldurdum ve kaydettim. Dosyamıza bir önceki bölümde çalıştırma izni vermiştik. Şimdi de nasıl çalıştırıldığını görelim.

Komut satırında şu ifadeyi yazarak hello.sh dosyasını içinde belirtilen dille çalıştırıyoruz:

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
./hello.sh
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Burada yazmış olduğumuz nokta \(.\) 'içinde bulunduğumuz dizini' temsil etmektedir. Eğik çizgi ise 'yazılan dizinin altında' anlamını taşımaktadır. Yani toplamında 'içinde bulunduğumuz dizin altında' anlamına gelmektir. İçinde bulunduğumuz dizin altındaki hello.sh dosyasını yazmış olduk. Enter yaptığımız durumda bu dosya çalışacaktır.

Dosya çalıştıktan sonra komut satırında şöyle bir cümle görünüyor:

{% code-tabs %}
{% code-tabs-item title="Çıktı" %}
```text
Merhaba Dünya
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Tebrikler! İlk uygulamanızı yazdınız. Buradan sonra değişken kavramıyla devam edeceğiz.

