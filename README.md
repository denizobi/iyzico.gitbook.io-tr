---
description: 'iyzico''nun API''sini, dokümanlarını ve ödeme çözümlerini keşfedin.'
---

# Entegrasyon

{% hint style="danger" %}
Bu portalda anlatılan tüm ürünler "Ayarlar-Firma Ayarları" menüsünde API ve Güvenlik Anahtarını görebilen kurumsal hesap sahiplerine hitap etmektedir.
{% endhint %}

iyzico'nun 2 farklı ortamı bulunmaktadır ve birbirinden bağımsızdır. Özetlemek gerekir ise **test** ortamında **test** kartları ile işlem yapılabilirken **gerçek** ortamda **gerçek** kartlar ile işlem yapılabilmektedir.

|   | **Sandbox \(Test\)** | **Canlı \(Gerçek\)** |
| :--- | :--- | :--- |
| hesapOluştur | [https://sandbox-merchant.iyzipay.com/auth](https://sandbox-merchant.iyzipay.com/auth) | [https://www.iyzico.com/hesap-olustur](https://www.iyzico.com/hesap-olustur) |
| panel | [https://sandbox-merchant.iyzipay.com/dashboard](https://sandbox-merchant.iyzipay.com/dashboard) | [https://merchant.iyzipay.com/dashboard](https://merchant.iyzipay.com/dashboard) |
| baseUrl | [https://sandbox-api.iyzipay.com/](https://sandbox-api.iyzipay.com/) | [https://api.iyzipay.com/](https://api.iyzipay.com/) |
| apiKey | Firma ayarları menüsünde görüntüleyebilirsiniz. "**sandbox-..."** ile ****başlar | Firma ayarları menüsünde görüntüleyebilirsiniz. |
| secretKey | Firma ayarları menüsünde görüntüleyebilirsiniz. "**sandbox-..."** ile başlar | Firma ayarları menüsünde görüntüleyebilirsiniz. |
| loginSmsKodu | 123456 | Cep telefonunuza iletilir. |
| 3dSifre | 283126 | İşlem yapılan kart üzerindeki kayıtlı telefona gider. |
| Test | Test etmek için test kartlarını kullanabilirsiniz. | 1 TRY'lik temsili ürün oluşturup kişisel kartınız ile test edebilirsiniz. |



