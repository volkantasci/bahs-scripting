# Sistem Değişkenleri ve Kullanıcı Değişkenleri

Hatırlarsanız bir önceki bölümde bazı değişkenler oluşturup bunlara değer atamıştık. Bu değişken isimlerinin nasıl olabileceği anlatılırken tüm değişkenler küçük harfle yazılmıştı. Elbette bu bir şart değil ancak bu bir kültürdür. 

Kullanıcı değişkenleri küçük harfle başlar ve genellikle de o şekilde devam eder. Eğer değişken ismi iki ya da daha fazla kelimeden meydana geliyorsa bunları bağlamak için birkaç farklı yöntem kullanılır. Örnek olarak aşağıdaki kodlara bakabiliriz.

```bash
#!/bin/bash

degisken_adi=""
degiskenAdi=""
```

Tabi eğer istersek şu şekilde de bir değişken adı yazabiliriz, hiçbir sakıncası yok.

```bash
DEGISKEN=""
```

Ama dediğimiz gibi değişken isimlerinde belli bir kültür vardır. Bu kültürü devam ettirmek akıllıca olacaktır çünkü herhangi birisi sizin kodlarınızı incelediğinde daha kolay anlayabilir ve siz de bir başkasının kodlarını incelediğinizde daha kolay anlayabilirsiniz.

**BASH** dilinde tamamı büyük harflerle yazılmış değişkenler sistem değişkenidir ve **BASH** dosyasında direkt isimleriyle çağırabiliriz. Öncesinde bir tanımlama yapmayız. Çağırabileceğimiz bazı sistem değişkenlerine örnek verelim.

{% code-tabs %}
{% code-tabs-item title="Program" %}
```bash
#!/bin/bash

echo $BASH
echo $HOME
echo $BASH_VERSION
echo $PWD
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
/usr/bin/bash
/home/ryuk
5.0.0(1)-release
/home/ryuk
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Bu dosyayı çalıştırdığımız zaman bazı çıktılar alacağız ve çıktılar sizin bilgisayarınızda benimkinden farklı olabilir. Çünkü bu değişkenler sistem tarafından oluşturulurlar. Örneğin ilk kullandığımız **$BASH** değişkeni bu dosya çalışırken hangi uygulamanın kullanıldığını gösterir. **$HOME** değişkeni ise ev dizininiz neredeyse o yolu gösterir. Üçüncü değişkenin ne olduğunu söylememe gerek yok sanırım. Son değişken ise bu uygulamayı çalıştırırken Terminal uygulamanızda hangi dizinde olduğunuzu gösterir. Bu, genelde dosyanın bulunduğu dizin gibi algılansa da farklı bir manaya gelmektedir. Bir başka örnekle açıklayalım.

**$PWD** değişkeni bize hangi dizinde olduğumuzu verir. Ancak dosyanın hangi dizinde olduğunu değil. Örnek olarak ben kabuk dosyamı, kabuk dosyamın olduğu dizinde çalıştırırsam şu çıktıyı alırım:

```text
/home/ryuk/Masaüstü/bash-scripting
```

Ancak ben bir üst dizine gidip şu şekilde de kabuk dosyamı çalıştırabilirim:

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
./bash-scripting/program.sh
```
{% endcode-tabs-item %}

{% code-tabs-item title="Çıktı" %}
```
/home/ryuk/Masaüstü
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Bu durumda ise yukarıdaki _Çıktı_ sekmesinde görülen sonucu alırım. Yani terminal ekranımız o an neredeyse o çıktıyı alırız.

Yeri geldikçe bu değişkenlerin anlamlarına yeniden değineceğiz ancak bu bölümün konusu olan sistem ve kullanıcı değişkenlerinin ne olduğuna dair bilgileri gerekli düzeyde aldığımıza inanıyorum.

