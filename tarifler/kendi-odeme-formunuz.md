# Kendi ödeme formunuz \(API\)

## Başlarken

Kendi formunu kullanan üye işyeri form üzerindeki kontrolleri ve kuralları uygulaması gerekir. 

* Kart numarası\(PAN\) [luhn](https://www.google.com.tr/search?ei=VmAKXPvIHIeMmgXJv6yoDQ&q=luhn+algorithm&oq=luhn+algorithm&gs_l=psy-ab.3..0j0i67j0l2j0i22i30l6.1196.2533..2822...0.0..0.133.1042.0j9......0....1..gws-wiz.......0i71.R2J5qTjekMY) algoritmasına tabi tutulmalıdır.
* Kartın hamilinin adı ve soyadı alınmalıdır. \(şüpheli aktiviteleri takip etmek için\)
* Son kullanma tarihi geçmiş kartlar ile sorgu yapma engellenmelidir.
* AMEX kartları ile işlem alabilir şekilde tasarlanmalıdır. \([güvenlik kodu](https://www.google.com.tr/search?ei=GmEKXOP6McqQmgWU1KS4Aw&q=cvv+cvc+cid&oq=cvv+cvc+cid&gs_l=psy-ab.3..0i19j0i22i30i19l9.7428.9172..9304...1.0..0.258.740.0j4j1......0....1..gws-wiz.......0j0i22i30j0i22i10i30j0i22i10i30i19j33i160.t2LBYfTt3rU)\)

Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir. **6** ana servisten oluşur. Bu adımları takip ederek entegrasyonunuzu tamamlayabilirsiniz

**Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit \(iş modeliniz uygun ise\) oranlarını yanıt olarak alabilirsiniz. Bu serviste dönen oranlar iyzico üye iş yeri panelindeki oranlardır.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/07e3a5ce053078777766)

**Ödeme**

Bu servisi kullanarak bir karttan para çekimi sağlayabilirsiniz. 

{% code-tabs %}
{% code-tabs-item title="PHP" %}
```php
<?php
require_once('config.php');
# create request class
$request = new \Iyzipay\Request\CreatePaymentRequest();
$request->setLocale(\Iyzipay\Model\Locale::TR);
$request->setConversationId("123456789");
$request->setPrice("1.3");
$request->setPaidPrice("1.2");
$request->setCurrency(\Iyzipay\Model\Currency::TL);
$request->setInstallment(1);
$request->setBasketId("B67832");
$request->setPaymentChannel(\Iyzipay\Model\PaymentChannel::WEB);
$request->setPaymentGroup(\Iyzipay\Model\PaymentGroup::PRODUCT);
$paymentCard = new \Iyzipay\Model\PaymentCard();
$paymentCard->setCardHolderName("John Doe");
$paymentCard->setCardNumber("5528790000000008");
$paymentCard->setExpireMonth("12");
$paymentCard->setExpireYear("2030");
$paymentCard->setCvc("123");
$paymentCard->setRegisterCard(0);
$request->setPaymentCard($paymentCard);
$buyer = new \Iyzipay\Model\Buyer();
$buyer->setId("BY789");
$buyer->setName("John");
$buyer->setSurname("Doe");
$buyer->setGsmNumber("+905350000000");
$buyer->setEmail("email@email.com");
$buyer->setIdentityNumber("74300864791");
$buyer->setRegistrationAddress("Nidakule Göztepe, Merdivenköy Mah. Bora Sok. No:1");
$buyer->setIp("85.34.78.112");
$buyer->setCity("Istanbul");
$buyer->setCountry("Turkey");
$request->setBuyer($buyer);
$shippingAddress = new \Iyzipay\Model\Address();
$shippingAddress->setContactName("Jane Doe");
$shippingAddress->setCity("Istanbul");
$shippingAddress->setCountry("Turkey");
$shippingAddress->setAddress("Nidakule Göztepe, Merdivenköy Mah. Bora Sok. No:1");
$request->setShippingAddress($shippingAddress);
$billingAddress = new \Iyzipay\Model\Address();
$billingAddress->setContactName("Jane Doe");
$billingAddress->setCity("Istanbul");
$billingAddress->setCountry("Turkey");
$billingAddress->setAddress("Nidakule Göztepe, Merdivenköy Mah. Bora Sok. No:1");
$request->setBillingAddress($billingAddress);
$basketItems = array();
$firstBasketItem = new \Iyzipay\Model\BasketItem();
$firstBasketItem->setId("BI101");
$firstBasketItem->setName("Binocular");
$firstBasketItem->setCategory1("Collectibles");
$firstBasketItem->setCategory2("Accessories");
$firstBasketItem->setItemType(\Iyzipay\Model\BasketItemType::PHYSICAL);
$firstBasketItem->setPrice("1.3");
$basketItems[0] = $firstBasketItem;
$request->setBasketItems($basketItems);
# make request
$payment = \Iyzipay\Model\Payment::create($request, Config::options());
# print response
print_r($payment);
```
{% endcode-tabs-item %}
{% endcode-tabs %}

**3D ile Ödeme**

Tek çekim, taksitli ve tek tıkla ödeme işlemleri için uygundur. İşleme gönderilen kartın bakiyesinden ilgili miktarı çekme işlemi yapar. Bu servis ile ilgili detaylı bilgiyi [3D ile Ödeme](https://dev.iyzipay.com/tr/api/3d-ile-odeme) sayfamızdan edinebilirsiniz.

**BKM Express ile Ödeme**

BKM Express dijital cüzdanı içerisinden seçilen kartın bakiyesinden, ilgili miktarı çekme işlemini yapar.Bu servis ile ilgili detaylı bilgiyi [BKM Express ile Ödeme](https://dev.iyzipay.com/tr/api/bkm-express-ile-odeme) sayfamızdan edinebilirsiniz.

**Ödeme Sorgulama**

iyzico'da kaydı oluşturulan bir işlemin detayları sorgulanabilir. Bu servis ile ilgili detaylı bilgiyi [Ödeme Sorgulama](https://dev.iyzipay.com/tr/api/odeme-sorgulama) sayfamızdan edinebilirsiniz.

**İptal**

Bankalar gün sonu almadan önce işlemin iptal edilmesidir. Bu servis ile ilgili detaylı bilgiyi [İptal](https://dev.iyzipay.com/tr/api/iptal) sayfamızdan edinebilirsiniz.

**İade**

Bankalar gün sonu aldıktan sonra işlemin kısmi veya tam olarak iade edilmesidir. Bu servis ile ilgili detaylı bilgiyi [İade](https://dev.iyzipay.com/tr/api/iade) sayfamızdan edinebilirsiniz.

**Kart Saklama**

Üye işyerinden işleme gönderilen kartların iyzico'nun sunucularında saklanmasını sağlar. Bu servis ile ilgili detaylı bilgiyi [Kart Saklama](https://dev.iyzipay.com/tr/api/kart-saklama) sayfamızdan edinebilirsiniz.

