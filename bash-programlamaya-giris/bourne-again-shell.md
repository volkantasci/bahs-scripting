# Bourne Again Shell

BASH, GNU/Linux sistemler için bir komut yorumlayıcısı, yani bir kabuktur. BASH kabuğu Unix sistemlerdeki sh’ nin hemen hemen tüm özelliklerine de sahiptir. BASH, GNU/Linux sistemlerde öntanımlı komut yorumlayıcısı \(kabuk\) olarak gelmektedir.

BASH, hem bir kabuk hem de bir programlama dilidir. Kabuk olarak işletim sistemini yönetmek için kullandığımız komutları yerine getirir. Bir programlama dili olarak ise programlama dillerinin sahip olduğu yapılara sahiptir ve bunları bir dosyaya yazıp çalıştırabilmemize imkan sağlar. Bu sayede tüm bu kabuk komutlarını bir arada kullanabilmemize olanak verir. **Komutlar içeren bu dosyaların kendileri de birer komut haline gelebilirler.**

İşletim sistemimizde bulunan kabuk uygulamalarını görüntülemek için şu komutu çalıştırabiliriz:

```text
cat /etc/shells
```

Bu komutun çıktısında işletim sistemimizde yüklü olan kabuk uygulamaları olacaktır. Örneğin benim kullandığım GNU/Linux sisteminde yüklü olan kabuk uygulamaları şunlar:

* /bin/sh
* /bin/bash
* /bin/zsh
* /usr/bin/zsh
* /usr/bin/git-shell

Biz bu kitapta yukarıda listelenen kabuk dillerinden ikincisi olan BASH dilini öğreneceğiz.

