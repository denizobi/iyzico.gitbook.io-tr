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

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## **3D entegrasyonunda dikkat edilmesi gereken noktalar?**

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

## **istek yanıtı Null olarak dönüyor ve TLS 1.2 konusunda ne yapabilirim?**

Yes, after a few months we finally found the answer. Sadly, Mike is on vacations right now so I'm afraid we are not able to provide the answer at this point.

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

