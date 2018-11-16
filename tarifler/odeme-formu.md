---
description: >-
  iyzico'nun ödeme formu teknolojisini 4 basit adımı takip ederek entegre
  edebilirsiniz.
---

# iyzico ödeme formu

## Başlangıç

Hazırladığımız bu rehber ile birlikte iyzico ödeme formunu hızlı bir şekilde entegre edebilirsiniz. API ve Güvenlik anahtarınızı canlı \(gerçek\) veya sandbox \(test\) ortamınız için iyzico panelinize giriş yaptıktan sonra  "**Ayarlar -&gt; Firma Ayarları**" menüsünden alabilirsiniz. 

* [x] API ve Güvenlik anahtarınızı doğru `baseUrl` değeri ile kullanın.
* [x] Ödeme formunu başlatmak için ilgili kütüphanedeki `CreateCheckoutFormInitializeRequest` sorgusunu çalıştırın ve `checkoutFormContent` alanında dönen scripti ödeme formunun gösterilmesini istediğiniz sayfada kullanın.
* [x] Ödeme formunu kullanmak istediğiniz sayfanın ilgili bölümde aşağıdaki divi kullanın. `<div id="iyzipay-checkout-form" class="responsive"></div>`
* [x] Formu oluştururken kullandığınız `callbackUrl` adresine sonuç sayfanıza **POST** edilen _token_ değeri ile `RetrieveCheckoutFormRequest` sorgusunu çalıştırıp sonucu öğrenin.

## 1- Ödeme formunu başlatmak

iyzico kütüphanelerinin içerisinde bulunan sample klasöründen **initialize\_checkout\_form** sayfasını çalıştırabilirsiniz. 

{% tabs %}
{% tab title="Request" %}
Samples klasöründeki örneği aşağıdaki parametreleri kullanarak düzenleyin.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parametre İsmi</th>
      <th style="text-align:left">Açıklama</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">locale</td>
      <td style="text-align:left">Ödeme formu dilini belirler. Şu anda sadece İngilizce ve Türkçe dili ile
        kullanılmaktadır. İngilizce için <code>en </code>Türkçe için <code>tr </code>olarak
        set edebilirsiniz.</td>
    </tr>
    <tr>
      <td style="text-align:left">conversationId</td>
      <td style="text-align:left">Request ve response değerlerini karşılaştırmak için kullanılır. <b>Sipariş numaranızı</b> set
        edebilirsiniz.</td>
    </tr>
    <tr>
      <td style="text-align:left">price</td>
      <td style="text-align:left">Sepetteki ürünlerin (basketItemPrice) toplam tutarıdır. Sepetteki ürünlerin
        toplamı muhakkak bu parametreye eşit olmalıdır.</td>
    </tr>
    <tr>
      <td style="text-align:left">paidPrice</td>
      <td style="text-align:left"><b>Karttan çekilecek tutardır</b>. Price parametresinden <b>düşük</b> veya <b>yüksek</b> veya <b>eşit</b> olabilir.
        Örneğin bir indirim var ise, price parametresinden yani sepetteki ürünlerin
        toplam tutarından düşük olabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">
        <p>Ödeme formunun para birimi için kullanılır.</p>
        <p>TRY dışında kullanmak için, hesabınızda multicurrency özelliğinin aktif
          olması gerekmektedir.</p>
        <p>TRY, EUR, USD, GBP, RUB, CHF, NOK kullanılabilir.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">basketId</td>
      <td style="text-align:left">Ödeme sonucunu öğrenirken dönen değerdir. <b>Sipariş numarası</b> veya <b>arkaplanda doğrulama için kullanılacak bir değer </b>set
        edilebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">paymentGroup</td>
      <td style="text-align:left">PRODUCT olarak set edilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">callbackUrl</td>
      <td style="text-align:left">iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan
        sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir
        ve bu adrese bir token değeri post edilir. Sipariş sonucu sorgulama ve
        gösterme sayfanızın adresidir. <b>HTTPS</b> ile başlamalı ve <b>dışarıdan erişime uygun</b> olmalı.</td>
    </tr>
    <tr>
      <td style="text-align:left">enabledInstallments</td>
      <td style="text-align:left">Kategori/ürün/ödeme bazlı taksit kısıtlama için kullanılır. Sadece set
        edilen taksit seçenekleri ödeme formunda uygun kartlara gösterilir. iyzico
        default olarak 2, 3, 6, 9, 12 değerlerini destekler.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerId</td>
      <td style="text-align:left">Alıcınızı temsil eden id bilgisidir. Satın alan kullanıcıyı temsil eden
        eşsiz bir değer olabilir. Örn: sitenizdeki üyelik numarası olabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerName</td>
      <td style="text-align:left">Alıcınızın adı. Alıcınızın üye olurken veya sipariş verirken ad alanına
        girdiği değerdir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerSurname</td>
      <td style="text-align:left">Alıcınızın soyadı. Alıcınızın üye olurken veya sipariş verirken soyadı
        alanına girdiği değerdir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerGsmNumber</td>
      <td style="text-align:left">Alıcınızın telefon numarası. Alıcınızın üye olurken veya sipariş verirken
        telefon numarası alanına girdiği değerdir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerEmail</td>
      <td style="text-align:left">Alıcınızın email adresi. Alıcınızın üye olurken veya sipariş verirken
        email alanına girdiği değerdir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerIdentity</td>
      <td style="text-align:left">Alıcınızın kimlik numarası. Bu parametre hakkında <a href="https://iyzico.gitbook.io/tr/sss/teknik-sorular/hata-kodlari/validasyon-hatalari#8-identitynumber-goenderilmesi-zorunludur">buradan</a> ayrıntılı
        bilgi alabilirsiniz.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerRegistrationAddress</td>
      <td style="text-align:left">Alıcınızın kullandığı adres. Ülke ve İl/Şehir bilgisi bulunmayan mahalle,
        sokak, cadde, kapı no, ilçe, semt..vb bilgileri yazılabilir. Bu alan kargo
        veya fatura adresi ile aynı olabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerIp</td>
      <td style="text-align:left">Alıcınızın IP bilgisi. PHP için kullanım örneği <b>$_SERVER[‘REMOTE_ADDR’];</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">buyerCity</td>
      <td style="text-align:left">Alıcınızın kullandığı adresin <b>il/şehir </b>bilgisi.</td>
    </tr>
    <tr>
      <td style="text-align:left">buyerCountry</td>
      <td style="text-align:left">Alıcınızın kullandığı adresin <b>ülke</b> bilgisi. <b>TR, TUR, Türkiye, Turkey </b>olarak
        kullanabilirsiniz.</td>
    </tr>
    <tr>
      <td style="text-align:left">shippingContactName</td>
      <td style="text-align:left">Kargoyu teslim alacak isim ve soyisim değeri. Bu kişi buyer ile aynı kişi
        ise buyerName ve buyerSurname bu kısma eklenebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">shippingAddress</td>
      <td style="text-align:left">Kargonun teslim edileceği adres. Bu adres buyerRegistrationAddress veya
        billingAddress ile aynı olabilir. Ülke ve İl/Şehir bilgisi bulunmayan mahalle,
        sokak, cadde, kapı no, ilçe, semt..vb bilgileri yazılabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">shippingCity</td>
      <td style="text-align:left">Kargonun teslim edileceği il/şehir bilgisi. Bu alan buyerCity ile aynı
        bilgileri taşıyabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">shippingCountry</td>
      <td style="text-align:left">Kargonun teslim edileceği ülke bilgisi. TR, TUR, Türkiye, Turkey olarak
        kullanabilirsiniz. Bu alan buyerCountry ile aynı bilgileri taşıyabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">billingContactName</td>
      <td style="text-align:left">Fatura üzerinde yer alacak isim ve soyisim değeri. Bu kişi buyer ile aynı
        kişi ise buyerName ve buyerSurname bu kısma eklenebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">billingAddress</td>
      <td style="text-align:left">Fatura üzerinde yer alacak adres. Bu adres buyerRegistrationAddress veya
        shippingAddress ile aynı olabilir. Ülke ve İl/Şehir bilgisi bulunmayan
        mahalle, sokak, cadde, kapı no, ilçe, semt..vb bilgileri yazılabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">billingCity</td>
      <td style="text-align:left">Fatura üzerinde yer alacak il/şehir bilgisi. Bu alan buyerCity ile aynı
        bilgileri taşıyabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">billingCountry</td>
      <td style="text-align:left">Fatura üzerinde yer alacak ülke bilgisi. TR, TUR, Türkiye, Turkey olarak
        kullanabilirsiniz. Bu alan buyerCountry ile aynı bilgileri taşıyabilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">basketItemId</td>
      <td style="text-align:left">Ürün veya ürünlerin sisteminizdeki temsili numarası. Sepete denk gelen
        ürün kodlarını içerebilir. "Genel Ürün ID" olarak set edilebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">basketItemName</td>
      <td style="text-align:left">Ürün veya ürünlerin ismi. "Genel Ürün" olarak set edilebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">basketItemCategory1</td>
      <td style="text-align:left">Ürün veya ürünlerin kategorisi. "Genel Kategori" olarak set edilebilir.</td>
    </tr>
    <tr>
      <td style="text-align:left">basketItemType</td>
      <td style="text-align:left">PHYSICAL olarak set edilir. Sanal bir ürün söz konusu ise VIRTUAL olarak
        set edilir. VIRTUAL set edildiği durumda shipping parametreleri zorunlu
        olmaktan çıkar.</td>
    </tr>
    <tr>
      <td style="text-align:left">basketItemPrice</td>
      <td style="text-align:left">Ürün veya ürünlerin fiyatı. Tek üründe toplam fiyat yazılabilir.</td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="Response" %}
Yapılan sorguya yanıt olarak dönen parametrelerin açıklamalarını içermektedir. Ödeme loglarınıza eklenmesinde büyük fayda var. 

| Parametre İsmi | Açıklama |
| :--- | :--- |
| token | iyzico tarafından ödeme formunun görüntülenebilmesi için dönen eşsiz değer. üzerinde 1 adet başarılı ödeme taşır.  |
| checkoutFormContent | Sayfadaki div etiketinin aktifleşmesini sağlayan scriptin döndüğü alandır. popup ve responsive kullanımlar için geçerlidir. |
| tokenExpireTime | Tokenin geçerlilik süresidir. 30dk olarak sistemde sabittir.  |
| paymentPageUrl | Ortak ödeme sayfası ve iframe kullanımlarında bu alandaki dönen bağlantı kullanılır. |
| status | Yapılan sorgunun sistem sonucunu döner. |
| errorCode | Eğer bir hata oluşmuş ise kodunu döner. |
| errorMessage | Eğer bir hata oluşmuş ise mesajını döner. |
| errorGroup | Eğer bir hata oluşmuş ise hata grubunu döner. |
| locale | Gönderilen dil bilgisi değerini döner. |
| systemTime | Unix formatında zaman damgası değeri. |
| conversationId | Gönderilen conversationId bilgisini döner. |
{% endtab %}
{% endtabs %}

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

## 3- Ödeme sonucunu öğrenmek

iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir ve bu adrese bir **token** değeri post edilir.

Bu **token** değeri ile ikinci bir sorgu yapılması gerekmektedir. Yapılacak olan ikinci sorgu ile, işlem sonucuna dair ayrıntılar alınmaktadır.

Bu sorguda kullanacağınız **token** değerini ödeme formunu oluşturduğunuz anda ya da callbackUrl adresinize iyzico tarafından post edildiğinde alabilirsiniz.

{% tabs %}
{% tab title="Request" %}
Ödemenin sonucunu öğrenmek için `callbackUrl` adresinize **POST** edilen **token** _****_değerini ****kullanabilirsiniz.

| Parametre İsmi | Açıklama |
| :--- | :--- |
| token | callbackUrl adresinize POST edilen token değeridir. Örnek olarak **$\_POST\['token'\]** şeklinde sayfanın üst kısmında bir değişkene atayabilirsiniz. |
{% endtab %}

{% tab title="Response" %}
| Parametre İsmi | Açıklama |
| :--- | :--- |
| status | Yapılan sorgunun sistem sonucunu döner. Kontrol edilmelidir. |
| locale | Ödeme formunu başlatma esnasında girilen dil değerini döner. |
| systemTime | Unix formatında zaman damgası değeridir. |
| conversationId | Sonuç öğrenme sorgusunda kullanılan conversationId değeridir. |
| price | Sepetteki ürünlerin toplam tutarıdır. |
| paidPrice | Karttan çekilen son tutar. Kontrol edilmelidir. |
| installment | Ödeme seçilen taksit değeri. Kontrol edilmelidir.  |
| paymentId | Ödemeye iyzico tarafından verilen eşsiz değer. Ödemenin iptalinde kullanılır. Saklanmalıdır. |
| fraudStatus |  Entegrasyon ekibinin yönlendirmesi ile gri alan entegrasyonlarında kullanılır. |
| merchantCommissionRate | price ve paidPrice arasında farkın orantısal değeridir.  |
| merchantCommissionRateAmount | price ve paidPrice arasında farkın tutarsal değeridir.  |
| iyziCommissionRateAmount | iyzico'nun bu ödemeden aldığı yüzdesel komisyonunun tutarını belirtir. |
| iyziCommissionFee | iyzico'nun bu ödemeden aldığı sabir tutarlı komisyonu belirtir. |
| cardType | Ödeme yapılan kartın tipini döner. Kredi kartı..vb |
| cardAssociation | Ödeme yapılan kartın şema bilgisini döner. Mastercard, Visa..vb |
| cardFamily | Ödeme yapılan kartın ailesini döner. Axess, Neo..vb |
| cardToken | Ödeme esnasında kart saklama özelliği aktif ise ve ödeme yapan son kullanıcı kartını saklar ise bu alanda saklanan kartın token değeri döner. |
| cardUserKey | Ödeme esnasında kart saklama özelliği aktif ise ve ödeme yapan son kullanıcı kartını saklar ise bu alanda saklanan kullanıcının token değeri döner. |
| binNumber | Ödeme yapılan kartın ilk 6 hanesini döner. |
| lastFourDigits | Ödeme yapılan kartın son 4 hanesini döner. |
| basketId | Ödeme formunu başlatma esnasında set edilen basketId değerini döner. Ödeme sonuç eşleştirmede kullanılabilir.  |
| currency | Ödeme yapılan para birimini döner. TRY..vb |
| authCode | Ödemenin bankadaki onay kodudur. Ödeme, İptal ve İade işlemlerinin takibinde kullanılır. |
| hostReference | Ödemenin bankadaki referans kodudur. Ödeme, İptal ve İade işlemlerinin takibinde kullanılır. |
| phase | Ödemenin fazını belirtir. Direkt karttan para çekimleri için AUTH olarak döner. |
| token | Ödeme başlatma sorgusunda dönen ve `callbackUrl`'e **POST** edilen token değeridir. |
| callbackUrl | Ödeme başlatma sorgusunda set edilen dönüş adresi değeridir. |
| paymentStatus | Yapılan ödemenin iyzico'daki sonucunu belirtir. Mutlaka kontrol edilmelidir. |
| errorCode | status değeri failure olduğunda hata mesajının kodunu döner. |
| errorMessage | status değeri failure olduğunda hata mesajının içeriğini döner. |
| errorGroup | status değeri failure oldıuğunda hata mesajının grubunu döner. |
| mdStatus | 3D olarak yapılan ödemelerde ek bilgi dönen değerdir. |
| itemId | Sepetteki ürüne verdiğiniz ID değeridir. |
| paymentTransactionId | iyzico'nun sepette gönderilen ürüne verdiği eşsiz ID değeridir. Saklanmalıdır. |
| transactionStatus | Sepetteki ürünün iyzico'daki durumunu gösterir. |
| itemPrice | Sepetteki ürünün fiyatıdır. |
| itemPaidPrice | Sepetteki ürünün paidPrice ile arasındaki fark uygulandıktan sonraki fiyatıdır. |
| itemMerchantCommissionRate | iyzico'nun komisyon oranıdır. |
| itemMerchantCommissionRateAmount | iyzico'nun komisyon tutarıdır. |
| itemIyziCommissionRateAmount | Kırılım bazında iyzico'nun komisyon tutarıdır. |
| itemIyziCommissionFee | Kırılım bazında iyzico'nun komisyon tutarıdır. |
| itemBlockageRate | Kullanılmamaktadır. |
| itemBlockageRateAmountMerchant | Kullanılmamaktadır. |
| itemBlockageRateAmountSubMerchant | Kullanılmamaktadır. |
| itemBlockageResolvedDate | Kullanılmamaktadır. |
| itemSubMerchantPrice | Sepetteki üründen alt üye işyerine gönderilecek tutar. |
| itemSubMerchantPayoutRate | Sepetteki üründen alt üye iş yerine aktarılacak tutarın orantısal değeridir. |
| itemSubMerchantPayoutAmount | Sepetteki üründen alt üye işyerine aktarılacak tutardır. |
| itemMerchantPayoutAmount | Sepetteki üründen üye işyerine aktarılacak tutardır. |
| itemConvertedPaidPrice |  |
| itemConvertedIyziCommissionRateAmount |  |
| itemConvertedIyziCommissionFee |  |
| itemConvertedBlockageRateAmountMerchant |  |
| itemConvertedBlockageRateAmountSubMerchant |  |
| itemConvertedSubMerchantPayoutAmount |  |
| itemConvertedMerchantPayoutAmount |  |
| itemConvertedIyziConversionRate |  |
| itemConvertedIyziConversionRateAmount |  |
| itemConvertedCurrency |  |
{% endtab %}
{% endtabs %}

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

### 

