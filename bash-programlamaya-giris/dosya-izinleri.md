# Dosya İzinleri

Dosyaların birtakım izinleri yani sınırları vardır. Kimi dosyalar hem okunabilir hem yazılabilirken kimi dosyalar yalnızca okunabilir biçimdedir. Onları değiştiremezsiniz, içlerine yeni bir satır ekleyemez ya da var olanları silemezsiniz. Buna benzer olarak her dosya çalıştırılabilir değildir. Kimi dosyaları doğrudan çalıştırabilirken kimi dosyaları çalıştıramayız. Çalıştırmak istediğimiz dosyanın çalıştırılabilir iznine sahip olması gerekmektedir.

Dosyaların izinlerini değiştirmek için GNU/Linux'ta kullanabileceğimiz birkaç farklı metot var. Ancak biz bunların en sade olanını göreceğiz.

Herhangi bir dizinde bulunan dosyaları ve izinlerini listelemek için aşağıdaki komutu kullanıyoruz.

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
ls -l
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Bu komutu kullandığınızda içinde bulunduğunuz dizindeki tüm dosya ve dizinler listelenir. Eğer bu listede gizli dosya ve dizinlerin de olmasını istiyorsanız -l parametresinin yanına -a parametresini de eklemelisiniz. Yani şu şekilde olmalı:

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
ls -la
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Görüntülenen bu listede dosyaların izinleri de görünür. Örnek çıktı aşağıdaki gibidir.

{% code-tabs %}
{% code-tabs-item title="Çıktı" %}
```text
drwxr-xr-x 2 ryuk ryuk 4096 Eki 26 23:07 ben_bir_dizinim
-rw-r--r-- 1 ryuk ryuk   11 Eki 26 20:06 hello.sh
```
{% endcode-tabs-item %}
{% endcode-tabs %}

İlk satırda bir dizin bulunuyor. Genelde komut satırı uygulamalarının renklendirme desteği vardır ve dizinlerle dosyaları farklı renklerde gösterir. Bu sayede inceleme yapmaya gerek kalmadan ayırt edebiliriz. Ancak renklere gerek duymadan ayırt edebilmemiz için yukarıdaki örnek çıktıya bakacağız.

Listede en solda bulunan kısım izinleri belirtiyor. Dizinin bulunduğu satırda en soldaki ifade 'd' ile başlıyor. 'd' ile başlayan öğeler birer dizindir. Herhangi bir öğe ile başlamıyorsa bunun bir dosya olduğunu anlayacağız.

Her satırda izinlerin üç parçadan oluştuğunu görüyoruz. İlk kısım bizim sahip olduğumuz izinleri temsil ediyor. İkinci kısım ise grup kullanıcılarının iznini gösteriyor. Son kısım ise tüm kullanıcıları belirtiyor. Biz bu izinleri değiştirebiliriz elbette.

Yukarıdaki çıktıda görüntülenen **hello.sh** dosyasına odaklanalım. Bu dosyada bize ait izinler bölümünde '**rw**' yazıyor. Bunun ne anlama geldiğini anlamak için aşağıdaki tabloya bakalım.

| HARF | YETKİ |
| :--- | :--- |
| **-r** | **Read \(Okuma\)** |
| **-w** | **Write \(Yazma\)** |
| **-x** | **Execute \(Çalıştırma\)** |

Tablodan anladığımız üzere **hello.sh** dosyası üzerinde bizim okuma ve yazma iznimiz var. Bu dosyaya bir de çalıştırma izni vermeliyiz. Bunu yapmak için şöyle bir komut yazıyoruz:

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
chmod +x hello.sh
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Yukarıda yazmış olduğumuz '+x' ifadesi ile var olan izinlere 'x' iznini ekliyoruz. Eğer ki bu izni kaldırmak istersek şu şekilde bir komut yazacağız:

{% code-tabs %}
{% code-tabs-item title="Komut" %}
```bash
chmod -x hello.sh
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Mantığı anladığınızı düşünüyorum. Herhangi bir izni eklemek için +, çıkarmak için ise - ifadesini kullanıyoruz.

Artık **hello.sh** dosyamız çalıştırılabilir bir dosya haline geldi. Bundan sonra içine kodlarımızı yazıp kolaylıkla çalıştırabiliriz.

