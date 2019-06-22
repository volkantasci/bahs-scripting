# Dosya-Dizin Bilgileri ve Güvenlik-İzin Ayarları

**ls** komutu **-l** seçeneği ile çalıştırıldığında dosya ve dizinler hakkında ayrıntılı bilgi verir. Örnek olarak ev dizininde çalıştırıp çıktıya bir göz atalım.

```text
-rw-r--r--  1 ryuk ryuk   53 Şub  6 14:56 belge
drwxr-xr-x  2 ryuk ryuk 4096 Şub  6 02:05 Belgeler
```

Çıktıda yedi sütun görüyoruz. Daha net görebilmek için tablo halinde gösterelim:

| Sütun İçeriği | Sütun Anlamı |
| :--- | :--- |
| `-rw-r--r--` | Dosya ya da dizin üzerindeki yetkileri gösterir. |
| `1` | Dosya ya da dizine bağlantı sayısını gösterir. |
| `ryuk` | Dosyanın sahibini gösterir. |
| `ryuk` | Sahibinin grup adını gösterir. |
| `53` | Dosyanın boyutu \(byte cinsinden\) |
| `Şub  6   14:56` | Dosyanın düzenlenme tarihi. |
| `belge` | Dosyanın adını gösterir. |

Birinci sütunda dosyanın/dizinin izinleri bulunuyor. Bu izinleri dört gruba ayırarak incelemek mümkün. Çıktıdaki ikinci satır üzerinden ilerleyelim.

İkinci satırda görüntülenen dizin bilgileri şu şekilde:

```text
drwxr-xr-x  2 ryuk ryuk 4096 Şub  6 02:05 Belgeler
```

Her bir grubu küme parantezleri ile gösterelim:

```text
{d} {rwx} {r-x} {r-x}
```

En baştaki grup tek elemanlıdır ve \(d\) harfi dizini temsil eder. Dosyalarda \(d\) yerine \(-\) yer almaktadır. Sonraki gruplar üç elemanlıdır ve Read \(r\) , Write \(w\), Execute \(x\)  yani Okuma, Yazma, Çalıştırma izinlerini taşır. Eğer bir izin yoksa o sırada \(-\) yer alır. Örneğin ikinci grupta \(w\) yerine \(-\) işareti var. Peki bu üç grup kimleri temsil ediyor?

Birinci üçlü: Dosyanın sahibi, ikinci üçlü: Grup ve üçüncü üçlü: Diğerleri demektir.

## İzin Ayarlarını Değiştirme

Bir dizin ya da dosyanın izin ayarları nasıl değiştirilir? sorusuna cevap verelim.

Öncelikle, bir dosyada izin ayarı değişikliğine neden ihtiyaç duyulur? sorusuna cevap vermemiz gerekiyor. Bazı dosyalar üzerinde değişiklik yapmak istediğimizde engellerle karşılaşabiliriz. Bunun birincil sebebi o dosyanın sahibi olmayışımız olabilir. Örneğin _root_ kullanıcısına ait bir dosyada değişiklik yapmak için ya _sudo_ yetkisini almak ya da _root_ olmak gerekir. Ancak _root'_ a ait bir dosyaya _root_ olmadan ulaşmak istersek _root_ olduktan sonra bu dosyada izinleri değiştirebiliriz.

{% hint style="info" %}
Yukarıda yazılanlar yalnızca bir örnektir. Eğer ne yaptığını çok iyi bilen biri değilseniz **root** kullanıcısına ait dosyalara erişim yetkisini bir başka kullanıcıya vermek pek akıllıca olmayacaktır. 
{% endhint %}

Dosyada izin değişikliğine gitmemizdeki bir diğer amaç bu dosyayı çalıştırılabilir hale getirmek olabilir. Örneğin Linux komutlarını kullanabilmemizin sebebi bu komut dosyalarının birer çalıştırılabilir dosya olmasındandır.

Yazdığımız bir uygulamayı komut satırından çağırırken bu dosyanın çalıştırılabilir halde olması gerekiyor ve biz de bu sebeple dosyalarda izin değişikliği yapacağız.

Örnek olarak bir BASH dosyasına çalıştırma yetkisi verelim. Bunun için izleyebileceğimiz birden çok yol var.

Bunlardan birincisi \(bu eğitimde sıklıkla kullanacağımız\) `+x` ifadesidir. Bu ifade sayesinde dosyalara çalıştırma \(Executable\) yetkisi verilir. Nasıl kullanıldığına bakalım.

```bash
chmod +x dosya_adı.sh
```

Yukarıdaki komut yardımıyla tüm kullanıcılara \(sahip, grup ve diğerleri\) bu dosya üzerinde çalıştırma yetkisi verilmiştir. Benzer metotla herhangi bir yetki bu kullanıcılardan geri alınabilir.

```bash
chmod -x dosya_adı.sh
```

{% hint style="info" %}
Bu yöntemler `w` ve `r` yetkilerinde de kullanılabilmektedir.
{% endhint %}

Her bir kullanıcı için \(sahip, grup ve diğerleri\) farklı izin yetkileri ayarlamak istersek bunu nasıl yapabiliriz? İşte burada ikinci metodumuz devreye giriyor: dosyalara sayı kullanarak izin yetkisi vermek. Nasıl mı?

Sayılar, her yetki için farklı değerdedir ve birden fazla yetki verebilmek için bu sayılar toplanır. Öncelikle bu sayıları görelim.

| Kip | Değer |
| :--- | :--- |
| r | 4 |
| w | 2 |
| x | 1 |

Örneğin; bir dosyanın sahibi ve diğer tüm kullanıcılara dosya üzerinde sadece okuma yetkisi vermek istersek aşağıdaki biçimde komut kullanırız.

```bash
chmod 444 dosya.sh
```

Komut içinde kullandığımız `444` sayısı aslında 3 parçaya ayrılmış şekilde inceleniyor. `{4}{4}{4}` Birinci sütun dosyanın sahibinin izinlerini, ikinci sütun grup kullanıcılarının izinlerini, üçüncü sütun ise diğer kullanıcıların izinlerini temsil ediyor. Yani `444` sayısı ile tüm kullanıcılara yalnızca okuma yetkisi vermiş oluyoruz.

Eğer dosya sahibine tüm izinleri, diğer kullanıcılara ise sadece okuma iznini vermek istersek aşağıdaki gibi komut kullanırız.

```bash
chmod 744 dosya.sh
```

`chmod` kullanımı hakkında eğitim boyunca bu bilgiler işimizi görecektir. Ancak `chmod` komutunun parametreleri için İnternet üzerinde detaylı arama yapabilir ya da yardım alma sayfalarına bakabilirsiniz.

