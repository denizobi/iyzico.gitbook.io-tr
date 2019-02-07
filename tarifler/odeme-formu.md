---
description: iyzico'nun ödeme formu teknolojisi ile hemen tanışın !
---

# ödeme formu \(checkout\)

Öncelikle ödeme formu çözümü için hazırladığımız postman kütüphanesi indirebilirsiniz. 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/8198585a01d98a150081)

Collection ekranında aşağıdaki görüntüye sahip oldu iseniz tek satır kod yazmadan entegrasyonu test etmeye başlayabilirsiniz. 



![iyzico-checkout postman collection g&#xF6;r&#xFC;n&#xFC;m&#xFC;](../.gitbook/assets/image%20%282%29.png)

**Başlat** sorgusu ile iyzico'dan ödeme formunu başlatabilirsiniz. `paymentPageUrl` parametresindeki adresi tarayıcımıza yazarak ödeme sayfasına ulaşabiliriz. Test ortamında olduğumuzdan test kartımızı `Kart Üzerindeki İsim: test test  
Kart Numarası: 5526080000000006  
Ay: 10 Yıl: 23 cvc: 123`   
kullanarak bir ödeme denemesi yapabilirsiniz. Daha sonra bu ödemenin sonucunu Başlat sorgusundan alacağınız `token` değeri ile **Öğren** sorgusu ile öğrenebilirsiniz. 

![iyzico-checkout postman ba&#x15F;lat g&#xF6;r&#xFC;n&#xFC;m&#xFC;](../.gitbook/assets/image%20%283%29.png)

![iyzico-checkout postman &#xF6;&#x11F;ren g&#xF6;r&#xFC;n&#xFC;m&#xFC;](../.gitbook/assets/image%20%284%29.png)

Başlat sorgusunda gelen yanıt 4 farklı şekilde kullanılabilir;

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
```http
#paymentPageUrl ile birlikte
https://...iyzipay.com/?token=...-baf8-
2a3430b66de9&lang=tr&iframe=true

```
{% endcode-tabs-item %}

{% code-tabs-item title="Ortak Ödeme Sayfası" %}
```http
#paymentPageUrl ile birlikte
https://...iyzipay.com/?token=...-baf8-
2a3430b66de9&lang=tr
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen `callbackUrl` adresine işlemin sonucunu içerisinde taşıyan **token** değeri **POST** edilir. Bu token değerini kullanarak Öğren sorgusu yapılır.

Eğer **`status`** ve **`paymentStatus`** parametreleri aynı aynda **success/SUCCESS** değerini taşıyor ise ve **`price`**, **`paidPrice`**, **`basketId`**, **`itemId`** gibi değerleri başlatma esnasındaki değerler ile uyumlu ise ödemeniz başarılı bir şekilde tamamlanmıştır.

{% tabs %}
{% tab title="PHP" %}
[Başlat](https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize_checkout_form.php)

[Öğren](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_checkout_form_result.php)

[İşlem Sorgula](https://github.com/iyzico/iyzipay-php/blob/master/samples/reporting_payment_detail.php)

[İptal](https://github.com/iyzico/iyzipay-php/blob/master/samples/cancel_with_reason.php)

[İade](https://github.com/iyzico/iyzipay-php/blob/master/samples/refund_with_reason.php)

[Günlük İşlemler](https://github.com/iyzico/iyzipay-php/blob/master/samples/reporting_payment_transaction.php)

[Para Aktarım Raporu](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_payout_transactions.php)
{% endtab %}

{% tab title=".NET" %}

{% endtab %}

{% tab title="Node" %}

{% endtab %}

{% tab title="Java" %}

{% endtab %}

{% tab title="Ruby" %}

{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="" %}

{% endtab %}
{% endtabs %}



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

