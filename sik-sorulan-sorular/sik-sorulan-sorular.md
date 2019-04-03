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

## **istek yanıtı Null olarak dönüyor ve TLS 1.2 konusunda ne yapabilirim?**

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

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## Zorunlu parametreler hangileridir?

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## İşlemler panelde neden görünmüyor?

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## **Api bilgilerim neden görünmüyor?**

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## **Geçersiz istek ve Geçersiz imza hataları neden alınır ve nasıl çözülür?**

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

