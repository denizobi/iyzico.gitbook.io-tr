---
description: iyzico entegrasyonu ile ilgili en sık sorulan soruları bulabilirsiniz.
---

# Sık Sorulan Sorular

## Ödeme Formu neden oluşmuyor?

iyzico'nun ödeme formunun görüntülenebilmesi için en önemli kriterlerden birincisi TLS versiyonunuzdur. PCI-DSS gerekliliklerinden dolayı TLS 1.2 versiyonu ile sisteminizin iyzico'ya sorgu yapabildiğinden emin olun. Sunucunuzun TLS 1.2 desteklemesi yeterli olmamak ile birlikte bu versiyonun kodunuz sorgu yapar iken kullanıldığından emin olunuz. PHP dilinde örnek TLS kontrol kodu aşağıdaki gibidir. Bu kodu test.php gibi bir sayfaya ekleyerek bu sayfayı tarayıcıdan çağırdığınızda aktif TLS versiyonu ekrana yazdırılacaktır. 

```php
<?php
$ch = curl_init("https://www.howsmyssl.com/a/check");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$data = curl_exec($ch);
curl_close($ch);

$json = json_decode($data);
echo $json->tls_version;
exit;
```

Eğer bu adrese sorgu yapamıyor iseniz yani ekranda null veya boş görüyorsanız sunucunuz internete bağlanamıyor olabilir. Hosting firmanızdan cURL kütüphanesinin aktif ve çalışabilir olduğunu teyit etmeyi unutmayınız.

## **Entegrasyonu tamamlama maili aldım ne yapmalıyım?**

Canlı ortamda oluşturduğunuz 1 TL - 5 TL arasındaki bir test ürününü gerçek bir kart ile başarılı bir ödeme yapıp  entegrasyon@iyzico.com adresine sisteme kayıt olduğunuz mail adresinen üye iş yeri numaranızı içeren bir email göndererek **canlı** statüsüne geçiş sürecinizi tamamlayabilirsiniz. Ödeme işleminizi ve gönderilen parametreleri kontrol ederek hesabınızın canlıya geçiş sürecini tamamlamaktan memnuniyet duyarız.

iyzico panelinizde "Ayarlar-&gt;Firma Ayarları" menüsünde API ve Güvenlik anahtarını görebiliyor olmanız gereklidir. Gerçek bir kart ile başarılı işlem için API ve Güvenlik anahtarlarının kullanılması gerekmektedir. Göremediğiniz durumlarda başvurunuz ile alakalı destek@iyzico.com adresine ulaşabilirsiniz. Panele giriş için aşağıdaki linki kullanabilirsiniz.

[https://merchant.iyzipay.com/auth/login](https://merchant.iyzipay.com/auth/login)

Eğer hesabınız entegrasyon aşamasında uzun süre kaldı ise entegrasyonu hatırlatmak için sistemimiz otomatik olarak bu maili göndermektedir. Hesabınız canlı statüsüne geçişi tamamladığınızda bu maili almayacaksınız. 

## **3D entegrasyonunda dikkat edilmesi gereken noktalar?**

3D entegrasyonu bir asenkron iletişim yapar. Kendi ödeme formunuzu kullandığınız API entegrasyonlarında 3D ile ödeme için öncelikle bir adet başlatma \(initialize\) sorgusu yapılır. Bu sorguya gelen yanıt bir HTML sayfası içerir. Yapmanız gereken bu HTML sayfasını render ederek son kullanıcıya göstermenizdir. Kullanıcı şifresini girdikten sonra başlatma sorgusunda verdiğiniz dönüş \(callbackUrl\) adresine iyzico doğrulamanın başarılı veya başarısız olduğu ile alakalı olarak sonuç iletir. \(browser redirection\) Başarılı olan durumlarda bitirme \(create\) sorgusu yapılarak işlem tamamlanır.

## **İstek yanıtı Null olarak dönüyor ve TLS 1.2 konusunda ne yapabilirim?**

iyzico'nun ödeme formunun görüntülenebilmesi için en önemli kriterlerden birincisi TLS versiyonunuzdur. PCI-DSS gerekliliklerinden dolayı TLS 1.2 versiyonu ile sisteminizin iyzico'ya sorgu yapabildiğinden emin olun. Sunucunuzun TLS 1.2 desteklemesi yeterli olmamak ile birlikte bu versiyonun kodunuz sorgu yapar iken kullanıldığından emin olunuz. PHP dilinde örnek TLS kontrol kodu aşağıdaki gibidir. Bu kodu test.php gibi bir sayfaya ekleyerek bu sayfayı tarayıcıdan çağırdığınızda aktif TLS versiyonu ekrana yazdırılacaktır. 

```php
<?php
$ch = curl_init("https://www.howsmyssl.com/a/check");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$data = curl_exec($ch);
curl_close($ch);

$json = json_decode($data);
echo $json->tls_version;
exit;
```

Eğer bu adrese sorgu yapamıyor iseniz yani ekranda null veya boş görüyorsanız sunucunuz internete bağlanamıyor olabilir. Hosting firmanızdan cURL kütüphanesinin aktif ve çalışabilir olduğunu teyit etmeyi unutmayınız.

## Kart kaynakları hataları nasıl anlayabilirim?

iyzico' sisteminde 2 tip hata vardır. İlk tip hata kodları panelinizde **işlemler-&gt;tüm işlemler** menüsünde görüntülenebilir. [https://merchant.iyzipay.com/transactions](https://merchant.iyzipay.com/transactions)

Tüm işlemler menüsündeki hatalar iyzico'nun çalıştığı bankalardan dönen hatalardır. Bu hatalar yüksek ihtimal ile kartın sahibinin bankasından kaynaklanmaktadır.

İkinci tip hatalar ise **işlemler-&gt;validasyon hataları** menüsünde görüntülenebilir. [https://merchant.iyzipay.com/validation-errors](https://merchant.iyzipay.com/validation-errors) 

Validasyon hataları ise iyzico'nun sisteminden dönen hatalardır. Bu hatalar konusunda neler yapılabileceği ile alakalı olarak entegrasyon@iyzico.com mail adresinden entegrasyon ekibi ile iletişime geçebilirsiniz.

## Zorunlu parametreler hangileridir?

Rehberler bölümündeki ürünlerin içerisindeki POSTMAN sorgularının body kısmı minimum parametrelerden oluşmaktadır. Bu sorguları baz alabilirsiniz. Tüm üye işyerleri sahtecilik koruma programı kapsamında gönderilen isteklerde doğru değerlerle doldurulan parametreleri göndermelidir. 

## İşlemler panelde neden görünmüyor?

iyzico'ya yapılan sorguların görüntülenebileceği 2 adet menü bulunmaktadır. [**işlemler-&gt;tüm işlemler**](https://merchant.iyzipay.com/transactions) ****ve ****[**işlemler-&gt;validasyon hataları**](https://merchant.iyzipay.com/validation-errors) ****menülerinde bulunabilir. Bu menüler ile ilgili detaylı bilgiyi [bağlantıdaki](https://dev-beta.iyzipay.com/tr/sik-sorulan-sorular/sik-sorulan-sorular#kart-kaynaklari-hatalari-nasil-anlayabilirim) sorumuzdan alabilirsiniz.

## **Api bilgilerim neden görünmüyor?**

Bireysel başvurularınızda \(iyzilink\) API ve Güvenlik anahtar bilgileri gizli tutulmaktadır. Eğer bir vergi numarası ile başvuru yaptı iseniz, iyzico panelinizde "Ayarlar-&gt;Firma Ayarları" menüsünde API ve Güvenlik anahtarını görebiliyor olmanız gereklidir. Göremediğiniz durumlarda başvurunuz ile alakalı destek@iyzico.com adresine ulaşabilirsiniz. 

## **Etsy entegrasyonunda beklenmedik ve genel bir hata neden oluşuyor.**

iyzico Etsy entegrasyonunda [videodaki](https://www.youtube.com/watch?v=DhLD_kOnz_o) adımları sırası ile gerçekleştirdiğinizden emin olunuz. 

## Kişisel Verilerin Korunması Kanunu ile alakalı yapmam gerekenler nedir?

Site sahibi internet sitesine üye olacak son kullanıcıların onaylayacakları Kullanıcı Sözleşmesine aşağıdaki cümleyi bir madde olarak eklemelidir.

Müşteri \(son kullanıcı\), ödeme yöntemine, üyeliğine ve siparişine ilişkin bilgilerin, ödemenin gerçekleştirilebilmesi ve ödeme usulsüzlüklerinin önlenmesi, araştırılması ve tespit edilmesini temin amacıyla iyzico Ödeme Hizmetleri A.Ş.’ye aktarılmasına ve iyzico tarafından [https://www.iyzico.com/gizlilik-politikasi/ ](https://www.iyzico.com/gizlilik-politikasi/)adresindeki Gizlilik Politikası’nın en güncel halinde açıklandığı şekilde işlenmesine ve saklanmasına rıza göstermektedir.

## SSL Güvenlik Protokolü

SSL ile internet tarayıcısına girilen bilgilerinin şifrelenerek transfer edilmesini _\(post edilmesini\)_ sağlayan güvenlik protokolüdür. Veri trafiği şifrelenir ve şifreli trafik başkaları tarafından izlenemez, kredi kartı ve diğer kişisel bilgiler trafik izlenerek okunamaz.

SSL sertifikası bulunan e-ticaret sitelerine, http:// yerine https:// kullanarak gireceği için adres çubuğunda bu ibarenin bulunduğu sitelerin güvenli olduğunu anlaşılabilir. Çünkü yetkili bir şirket tarafından onaylanan SSL sertifikası ile adres https:// olarak kullanıma açılır. Bu sertifikanın bulunduğu sitelerden yapılan alışverişlerde verilen kredi kartı bilgileri kopyalanmaya karşı şifrelenerek ödeme kuruluşuna gönderilir ve işlem gerçekleştirilir. Tahmini ve ele geçirilmesi pek mümkün olmayan bu şifre kombinasyonları sayesinde kart bilgileri ve diğer kişisel veriler üçüncü kişilerle paylaşılmaz, kopyalanarak kötü amaçlarla kullanılmasının önüne geçilir.

## SSL Kurulumu İçin Kimden Destek Alabilirim?

SSL kurulumuna dair daha önce bir tecrübeniz yok ise;  
· Hazır bir e-ticaret altyapısı kullanıyorsanız altyapı sağlayan firmanızdan destek alabilirsiniz.  
· Açık kaynaklı veya özel yazılım bir web siteniz var ise hosting _\(sunucu\)_ sağlayıcınızdan destek alabilirsiniz. Hosting hizmeti aldığınız firma, sitenize SSL kurulumu için yardımcı olacaktır.  
· SSL kurumunu sitenizde kendiniz tamamlamayı planlıyorsanız [https://movingtohttps.com](https://movingtohttps.com/) adresinden _\(İngilizce\)_ ayrıntılı bilgiye ulaşabilirsiniz.

## iyzico Çevrim Ücreti nedir?

Yabancı para birimi üzerinden gerçekleştirilecek işlemlerde, Komisyon Ücreti oranına %2 hizmet bedeli eklenecektir. Yabancı para birimi ile yapılacak satışlara uygulanacak ücret ise İşlem Ücreti’nin, işlemin yapıldığı gün Türkiye Cumhuriyet Merkez Bankası \(T.C.M.B.\) tarafından ilan edilen efektif satış kuru üzerinden hesaplanacak yabancı para birimi karşılığı + KDV olacaktır.

Döviz kurları için [http://www.tcmb.gov.tr/kurlar/today.xml](http://www.tcmb.gov.tr/kurlar/today.xml) linkindeki her gece saat 02:10’da. Forex alış, forex satış alanları dikkate alınmaktadır.

## **Geçersiz imza hatası nedir, neden alınır ve nasıl çözülür?**

iyzico'ya yapılan sorgularda datalar gönderilirken secretKey'in güvenliği için bir hash oluşturulup şifrelenip gönderilmektedir. Eğer bu hash iyzico tarafında çözülemez ise bu hata mesajı dönmektedir.

Bu hataya sebep olan durumlar: 

1. Güvenlik anahtarının \(secret key\) yanlış girilmesi
2. Karakter seti olarak UTF-8 kullanılmaması
3. Parametrelerin uygun formatta gönderilmemesi \(integer yerine string..vb\)

Bu hatayı çözebilmek ve sebebini bulabilmek için

1. Senaryo kontrolü: En basit sorgu olan taksit sorgusu ile \(retrieve installment\) bir deneme yapabilirsiniz. \(sadece kartın ilk 6 hanesi ve taksit yapılacak tutar alınmakta\) Eğer bu sorgu başarılı sonuçlanıyor ise güvenlik anahtarı doğru demektir.
2. Senaryo kontrolü: Taksit sorgusunda, conversationId parametresine türkçe karakterler ekleyerek deneyebilir misiniz? Örnek olarak; ş, ü, ğ, ç..vb gibi.
3. Senaryo kontrolü: Yaptığınız sorgunun parametrelerini github üzerindeki kütüphanemizdeki örneklerde kullanılan parametreleri birebir set ederek bir deneme yapabilirsiniz. \([https://github.com/iyzico](https://github.com/iyzico)\)

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0

## **Geçersiz istek hatası nedir, neden alınır ve nasıl çözülür?**

“Geçersiz istek" hatası, parametreler uygun formatta set edilmediği zaman dönmektedir. Set ettiğiniz parametrelerin formatını kontrol edebilirsiniz. İlk adımda tutar parametrelerinin ondalık kısmını virgülle değil nokta ile ayırdığınızı kontrol edebilirsiniz. Ör: 1,0 değil 1.0



