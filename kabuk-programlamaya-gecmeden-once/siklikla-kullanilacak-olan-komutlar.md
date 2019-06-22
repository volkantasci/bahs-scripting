---
description: >-
  Kitap boyunca sıklıkla kullanılması muhtemel Linux komutlarına ve işlevlerine
  değineceğiz.
---

# Sıklıkla Kullanılacak Olan Komutlar

{% hint style="info" %}
Komutlar küçük harfli olmalarına rağmen başlık olarak tüm harfleri büyük olarak yazılmıştır.
{% endhint %}

### CAT Komutu?

Farklı amaçlara hizmet etse de genellikle bir dosya içerisindeki metni ekrana bastırmak için kullanılır. Metin, terminal ekranından taşacak kadar büyükse eğer okunmasında zorluk çekmemek amacıyla çıktılar boru hattı \(pipe \[ \| \]\) kullanılarak **more** komutuna aktarılır. Boru hattı teriminin yabancı geldiğini biliyorum, merak etmeyin, programlamaya başladığımız vakit ne olduğunu öğrenecek ve çok seveceksiniz.

Örnek bir kullanım aşağıda görüntülenmektedir.

```bash
cat dosya.txt | more
```

### TOUCH Komutu?

Bulunulan dizinde bir ya da birden fazla dosya oluşturmak amacıyla kullanılır. Örnek:

```bash
touch dosya1.txt dosya2.py dosya3.sh
```

### CD Komutu?

Bir dizinden başka bir dizine ilerlemek için kullanılan, açılımı _Change Directory_ olan olmazsa olmaz komutlardandır. Örnek kullanım:

```bash
cd /home/ryuk
```

### PWD Komutu?

Açılımı _Print Working Directory_ olan, içinde bulunduğumuz dizin yolunu ekrana bastıran çok kullanışlı komuttur.

```bash
pwd
```

Kitap yazımı devam ettikçe bu sayfa da güncellenecektir.

