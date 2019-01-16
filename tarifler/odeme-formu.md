---
description: iyzico'nun ödeme formu teknolojisi ile hemen tanışın !
---

# ödeme formu \(checkout\)

  
Öncelikle ödeme formu çözümü için hazırladığımız postman kütüphanesi indirebilirsiniz. Postman hakkında daha fazla bilgi için [https://www.getpostman.com/](https://www.getpostman.com/) adresini ziyaret edebilirsiniz.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/8198585a01d98a150081)

Collection ekranında aşağıdaki görüntüye sahip oldu iseniz artık entegrasyonu test etmeye başlayabilirsiniz.

![iyzico-checkout postman collection g&#xF6;r&#xFC;n&#xFC;m&#xFC;](../.gitbook/assets/image%20%282%29.png)

Başlat sorgusunu ile ödeme formunu tetikleyebilirsiniz. Hemen "Send" butonuna tıklayarak iyzico test ortamından form oluşturma için "success" yanıtını alabilirsiniz.

![iyzico-checkout postman ba&#x15F;lat g&#xF6;r&#xFC;n&#xFC;m&#xFC;](../.gitbook/assets/image%20%283%29.png)

Bu yanıt 4 farklı şekilde kullanılabilir.

{% code-tabs %}
{% code-tabs-item title="Responsive" %}
```markup
<!--checkoutFromContent ile birlikte-->
<div id="iyzipay-checkout-form" class="responsive"></div>

```
{% endcode-tabs-item %}

{% code-tabs-item title="Pop up" %}
```markup
<!--checkoutFromContent ile birlikte-->
<div id="iyzipay-checkout-form" class="popup"></div>

```
{% endcode-tabs-item %}

{% code-tabs-item title="iframe" %}
```yaml
#paymentPageUrl ile birlikte
https://...iyzipay.com/?token=...-baf8-
2a3430b66de9&lang=tr&iframe=true

```
{% endcode-tabs-item %}

{% code-tabs-item title="Ortak Ödeme Sayfası" %}
```yaml
#paymentPageUrl ile birlikte
https://...iyzipay.com/?token=...-baf8-
2a3430b66de9&lang=tr
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Yukarıdaki kullanımlardan dilediğinizi seçebilirsiniz. Test ortamında test kartlarını kullanarak bir ödeme denemesi hemen yapabilirsiniz.

`5526080000000006  
10 / 2023  
123`

Ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen `callbackUrl` adresine işlemin sonucunu içerisinde taşıyan **token** değeri **POST** edilir. Bu token değerini kullanarak Öğren sorgusu yapılır.

![](../.gitbook/assets/image%20%284%29.png)

Eğer **`status`** ve **`paymentStatus`** parametreleri aynı aynda **success/SUCCESS** değerini taşıyor ise ve **`price`**, **`paidPrice`**, **`basketId`**, **`itemId`** gibi değerleri başlatma esnasındaki değerler ile uyumlu ise ödemeniz başarılı bir şekilde tamamlanmıştır.

## 4- Entegrasyon Testleri

* Canlı ortamda iyzico API'ına gönderilen parametrelere müşteriden alınan bilgiler set edilmelidir. Müşteriniden alınmayan "dummy" değerler sorgu parametrelerine set edilmemelidir.
* Geliştirmeler tamamlandıktan sonra ödeme adımlarınızı, test kartlarınız ile tüm durumlar için test edin.
* iyzico servislerinden dönen ve olabilecek tüm hataları karşılayacak şekilde kodunuzu düzenleyin.
* Sonuç sayfanızın iyzico'dan gelen yanıtı yorumlayabiliyor olmasına dikkat edin.
* Entegrasyonunuzun son kullanıcılar için [Kişisel Verilerin Koruması Kanunu](https://dev.iyzipay.com/tr/sss) ile uyumlu olmasına dikkat edin.
* iyzico logolarını sitenize eklemeyi unutmayın. [iyzico logo paketi](https://dev.iyzipay.com/tr/iyzico-logo-pack.zip).
* iyzico entegrasyon ekibinin onayı için [**entegrasyon@iyzico.com**](mailto:entegrasyon@iyzico.com) mail adresi ile iletişime geçin.

## Tebrikler !

Topluluklardan destek alın:

Videolardan destek alın:

### 

