---
description: >-
  iyzico'nun ödeme formu teknolojisini 4 basit adımı takip ederek entegre
  edebilirsiniz.
---

# ödeme formu \(checkout\)

## Başlangıç

Hazırladığımız bu rehber ile birlikte iyzico ödeme formunu hızlı bir şekilde entegre edebilirsiniz. API ve Güvenlik anahtarınızı canlı \(gerçek\) veya sandbox \(test\) ortamınız için iyzico panelinize giriş yaptıktan sonra  "**Ayarlar -&gt; Firma Ayarları**" menüsünden alabilirsiniz. 

* [x] API ve Güvenlik anahtarınızı doğru `baseUrl` değeri ile kullanın.
* [x] Ödeme formunu başlatmak için ilgili kütüphanedeki `CreateCheckoutFormInitializeRequest` sorgusunu çalıştırın ve `checkoutFormContent` alanında dönen scripti ödeme formunun gösterilmesini istediğiniz sayfada kullanın.
* [x] Ödeme formunu kullanmak istediğiniz sayfanın ilgili bölümde aşağıdaki divi kullanın. `<div id="iyzipay-checkout-form" class="responsive"></div>`
* [x] Formu oluştururken kullandığınız `callbackUrl` adresine sonuç sayfanıza **POST** edilen _token_ değeri ile `RetrieveCheckoutFormRequest` sorgusunu çalıştırıp sonucu öğrenin.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/8198585a01d98a150081)

## 1- Ödeme formunu başlatmak

iyzico kütüphanelerinin içerisinde bulunan sample klasöründen **initialize\_checkout\_form** sayfasını çalıştırabilirsiniz.

## 2- Ödeme formunu göstermek

Ödeme formu 4 farklı biçimde kullanılabilir. `checkoutFormContent` alanında dönen scripti kullandığınız sayfada aşağıdaki div kullanımları ile ödeme formunu gösterebilirsiniz. 

En çok tercih edilen responsive şeklinde kullanımdır. class değerini responsive olarak set edebilirsiniz.

`<div id="iyzipay-checkout-form" class="responsive"></div>`

İkinci en çok tercih edilen popup şeklinde kullanımdır. class değerini popup olarak set edebilirsiniz.

`<div id="iyzipay-checkout-form" class="popup"></div>`

iframe içerisinde göstermek için src değerinde kullanılan `paymentPageUrl` değerinin sonuna aşağıdaki kısım eklenir.

`https://...iyzipay.com/?token=...-baf8-2a3430b66de9&lang=tr`**`&iframe=true`**

Ortak ödeme sayfası şeklinde kullanmak için paymentPageUrl değerindeki adrese yönlendirme yapabilirsiniz.

`https://...iyzipay.com/?token=...-baf8-2a3430b66de9&lang=tr`

Yukarıdaki 4 farklı kullanım için ödeme formu başlatma sorgusundaki `callbackUrl` adresine işlemin sonucunu içerisinde taşıyan **token** değeri **POST** edilir.

iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir ve bu adrese bir **token** değeri post edilir.

Bu **token** değeri ile ikinci bir sorgu yapılması gerekmektedir. Yapılacak olan ikinci sorgu ile, işlem sonucuna dair ayrıntılar alınmaktadır.

Bu sorguda kullanacağınız **token** değerini ödeme formunu oluşturduğunuz anda ya da callbackUrl adresinize iyzico tarafından post edildiğinde alabilirsiniz.

## 4- Entegrasyon Testleri

* Canlı ortamda iyzico API'ına gönderilen parametrelere müşteriden alınan bilgiler set edilmelidir. Müşteriniden alınmayan "dummy" değerler sorgu parametrelerine set edilmemelidir.
* Ödeme işlemi sonucunda iyzico tarafından dönen cevaptaki değerler \(price, paidPrice, basketId, conversationId\) ile sizin sisteminize kaydettiğiniz değerleri karşılaştırarak bir farklılık var ise genel bir hata mesajı gösterebilirsiniz. Bu tür durumlarda iyzico entegrasyon ekibi ile iletişime geçmeyi unutmayınız. Müşteri tarafından ödenen tutar iyzico tarafından dönen cevaptaki paidPrice parametresindeki değere eşittir.
* Geliştirmeler tamamlandıktan sonra ödeme adımlarınızı, test kartlarınız ile tüm durumlar için test edin.
* iyzico servislerinden dönen ve olabilecek tüm hataları karşılayacak şekilde kodunuzu düzenleyin.
* Sonuç sayfanızın iyzico'dan gelen yanıtı yorumlayabiliyor olmasına dikkat edin.
* Hassas olmayan dataları ve yanıtları loglamaya dikkat edin.
* Entegrasyonunuzun son kullanıcılar için [Kişisel Verilerin Koruması Kanunu](https://dev.iyzipay.com/tr/sss) ile uyumlu olmasına dikkat edin.
* iyzico logolarını sitenize eklemeyi unutmayın. [iyzico logo paketi](https://dev.iyzipay.com/tr/iyzico-logo-pack.zip).
* iyzico entegrasyon ekibinin onayı için [**entegrasyon@iyzico.com**](mailto:entegrasyon@iyzico.com) mail adresi ile iletişime geçin.

## Tebrikler !

Topluluklardan destek alın:

Videolardan destek alın:

### 

