---
description: >-
  Yazılım geliştirme ekibiniz entegrasyon için gerekli yönlendirmelere buradan
  ulaşabilir.
---

# Yazılım ekibi gerekli

## Genel Bilgi

iyzico'yu sitenize entegre etmenin en hızlı yolu [iyzico ödeme formunu ](../tarifler/odeme-formu.md)kullanmaktır. 

## Nasıl Çalışır ?

iyzico sürekli gelişmekte olan kapsamlı bir Sandbox \(Test\) ortamı sunar. Sandbox ortamında hesap oluşturmak için[ bu bağlantıyı](https://sandbox-merchant.iyzipay.com/auth/register) kullanabilirsiniz. 

iyzico'nun 2 ortamı bulunmaktadır ve birbirinden bağımsızdır. Özetlemek gerekir ise **test** ortamında **test** kartları ile işlem yapılabilirken **gerçek** ortamda **gerçek** kartlar ile işlem yapılabilmektedir.

|  **** | Sandbox \(Test\) | Canlı \(Gerçek\) |
| :--- | :--- | :--- |
| Hesap Oluştur | ​[https://sandbox-merchant.iyzipay.com/auth](https://sandbox-merchant.iyzipay.com/auth)​ | ​[https://www.iyzico.com/hesap-olustur](https://www.iyzico.com/hesap-olustur)​ |
| Panel | ​[https://sandbox-merchant.iyzipay.com/dashboard](https://sandbox-merchant.iyzipay.com/dashboard)​ | ​[https://merchant.iyzipay.com/dashboard](https://merchant.iyzipay.com/dashboard)​ |
| baseUrl | ​[https://sandbox-api.iyzipay.com/](https://sandbox-api.iyzipay.com/)​ | ​[https://api.iyzipay.com/](https://api.iyzipay.com/)​ |
| apiKey | Firma ayarları menüsünde görüntüleyebilirsiniz. "**sandbox-..."** ile başlar | Firma ayarları menüsünde görüntüleyebilirsiniz. |
| secretKey | Firma ayarları menüsünde görüntüleyebilirsiniz. "**sandbox-..."** ile başlar | Firma ayarları menüsünde görüntüleyebilirsiniz. |
| Login Sms Kodu | 123456 | Cep telefonunuza iletilir. |
| 3D Şifre | 283126 | İşlem yapılan kart üzerindeki kayıtlı telefona gider. |
| Test | Test etmek için test kartlarını kullanabilirsiniz. | 1 TRY'lik temsili ürün oluşturup kişisel kartınız ile test edebilirsiniz. |

## Hadi Başlayalım

Yazılım geliştirmede kullandığınız programlama diline uygun kütüphaneyi [github hesabımızdan](https://github.com/iyzico) indirebilir veya kullandığınız dilin paket yöneticisi ile projenize ekleyebilirsiniz.

| Programlama Dili | Paket Yöneticisi | Github Sayfası |
| :--- | :--- | :--- |
| PHP | composer -&gt; iyzipay | [https://github.com/iyzico/iyzipay-php](https://github.com/iyzico/iyzipay-php) |
| C\# | nuget -&gt; iyzipay | [https://github.com/iyzico/iyzipay-dotnet](https://github.com/iyzico/iyzipay-dotnet) |
| Java | maven -&gt; iyzipay | [https://github.com/iyzico/iyzipay-java](https://github.com/iyzico/iyzipay-java) |
| Node | npm -&gt; iyzipay | [https://github.com/iyzico/iyzipay-node](https://github.com/iyzico/iyzipay-node) |
| Ruby | gem -&gt; iyzipay | [https://github.com/iyzico/iyzipay-ruby](https://github.com/iyzico/iyzipay-ruby) |
| Python | pip -&gt; iyzipay | [https://github.com/iyzico/iyzipay-python](https://github.com/iyzico/iyzipay-python) |

## Entegrasyon Methodları

iyzico'yu iki şekilde entegre edebilirsiniz.

Hızlı ve kolay bir şekilde ödeme almaya başlamak ise  ödeme formunu tercih edilebilirsiniz. Ön yüz kontrolleri \(validasyon\), BIN numarası sorgulama, Taksit yönetimi, 3D Secure ile ödeme, BKM Express, Fraud ve işlem limitleri için ek sorgu yapmaya gerek kalmadan tek bir entegrasyon ile işlemler tamamlanır.  Rehbere ulaşmak için [**tıklayınız**](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/odeme-formu).



Eğer PCI SAQ-D formunu dolduruyor iseniz kendi tasarımınız olan ödeme formunuzu API aracılığı ile entegre edebilirsiniz.

{% hint style="info" %}
Bu sayfa ile ilgili sorunuz var ise `destek@iyzico.com` adresinden bizim ile iletişime geçebilirsiniz.
{% endhint %}



