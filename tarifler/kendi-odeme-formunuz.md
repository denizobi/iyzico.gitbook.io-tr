# Kendi ödeme formunuz \(API\)

##  Başlarken

Kendi formunu kullanan üye işyeri form üzerindeki kontrolleri ve kuralları uygulaması gerekir. 

* Kart numarası\(PAN\) [luhn](https://www.google.com.tr/search?ei=VmAKXPvIHIeMmgXJv6yoDQ&q=luhn+algorithm&oq=luhn+algorithm&gs_l=psy-ab.3..0j0i67j0l2j0i22i30l6.1196.2533..2822...0.0..0.133.1042.0j9......0....1..gws-wiz.......0i71.R2J5qTjekMY) algoritmasına tabi tutulmalıdır.
* Kartın hamilinin adı ve soyadı alınmalıdır. \(şüpheli aktiviteleri takip etmek için\)
* Son kullanma tarihi geçmiş kartlar ile sorgu yapma engellenmelidir.
* AMEX kartları ile işlem alabilir şekilde tasarlanmalıdır. \([güvenlik kodu](https://www.google.com.tr/search?ei=GmEKXOP6McqQmgWU1KS4Aw&q=cvv+cvc+cid&oq=cvv+cvc+cid&gs_l=psy-ab.3..0i19j0i22i30i19l9.7428.9172..9304...1.0..0.258.740.0j4j1......0....1..gws-wiz.......0j0i22i30j0i22i10i30j0i22i10i30i19j33i160.t2LBYfTt3rU)\)

Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir. **6** ana servisten oluşur. Bu adımları takip ederek entegrasyonunuzu tamamlayabilirsiniz.

**Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit \(iş modeliniz uygun ise\) oranlarını yanıt olarak alabilirsiniz. Bu serviste dönen oranlar iyzico üye iş yeri panelindeki oranlardır.

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr",
  "conversationId": "123456789",
  "binNumber": "492095",
  "price": "100.0"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1544184942588,
  "conversationId": "123456789",
  "installmentDetails": [
    {
      "binNumber": "492095",
      "price": 100,
      "cardType": "CREDIT_CARD",
      "cardAssociation": "VISA",
      "cardFamilyName": "Paraf",
      "force3ds": 0,
      "bankCode": 12,
      "bankName": "Halk Bankası",
      "forceCvc": 0,
      "commercial": 0,
      "installmentPrices": [
        {
          "installmentPrice": 100,
          "totalPrice": 100,
          "installmentNumber": 1
        },
        {
          "installmentPrice": 53.03,
          "totalPrice": 106.06,
          "installmentNumber": 2
        },
        {
          "installmentPrice": 35.87,
          "totalPrice": 107.6,
          "installmentNumber": 3
        },
        {
          "installmentPrice": 18.58,
          "totalPrice": 111.46,
          "installmentNumber": 6
        },
        {
          "installmentPrice": 13,
          "totalPrice": 117.01,
          "installmentNumber": 9
        },
        {
          "installmentPrice": 10.25,
          "totalPrice": 122.99,
          "installmentNumber": 12
        }
      ]
    }
  ]
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

**Ödeme**

Bu servisi kullanarak bir karttan para çekimi sağlayabilirsiniz. 

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr", // sadece tr ve en değerini alabilmektedir
  "conversationId": "orderiddegeri1",
  "price": "100.0",
  "paidPrice": "110.5",
  "installment": 3,
  "paymentChannel": "WEB",
  "basketId": "orderiddegeri1",
  "paymentGroup": "LISTING",
  "paymentCard": {
    "cardHolderName": "Emre Faik",
    "cardNumber": "5528790000000008",
    "expireYear": "2020",
    "expireMonth": "10",
    "cvc": "123",
    "registerCard": 1
  },
  "buyer": {
    "id": "kullanıcıiddegeri",
    "name": "Emre",
    "surname": "Faik",
    "identityNumber": "74300864791",
    "email": "email@email.com",
    "gsmNumber": "+905350000000",
    "registrationAddress": "Burhaniye Mahallesi Atilla Sokak No:7 Üsküdar",
    "city": "Istanbul",
    "country": "Turkey",
    "ip": "85.34.78.112"
  },
  "shippingAddress": {
    "address": "Burhaniye Mahallesi Atilla Sokak No:7 Üsküdar",
    "contactName": "Emre Faik",
    "city": "Istanbul",
    "country": "Turkey"
  },
  "billingAddress": {
    "address": "Burhaniye Mahallesi Atilla Sokak No:7 Üsküdar",
    "contactName": "Emre Faik",
    "city": "Istanbul",
    "country": "Turkey"
  },
  "basketItems": [
    {
      "id": "orderiddegeri1",
      "price": "100.0",
      "name": "ürünismi",
      "category1": "ürünkategorisi",
      "itemType": "PHYSICAL"
    }
  ],
  "currency": "TRY"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1545220956037,
  "conversationId": "orderiddegeri1",
  "price": 100,
  "paidPrice": 110.5,
  "installment": 3,
  "paymentId": "11154295",
  "fraudStatus": 0,
  "merchantCommissionRate": 10.5,
  "merchantCommissionRateAmount": 10.5,
  "iyziCommissionRateAmount": 5.33715,
  "iyziCommissionFee": 0.25,
  "cardType": "CREDIT_CARD",
  "cardAssociation": "MASTER_CARD",
  "cardFamily": "Paraf",
  "cardToken": "so4ERPJ2ouMuPSKEFiUNqQRROnQ=",
  "cardUserKey": "hDsAoIK28+DG0TlmErBiHp1+klg=",
  "binNumber": "552879",
  "lastFourDigits": "0008",
  "basketId": "orderiddegeri1",
  "currency": "TRY",
  "itemTransactions": [
    {
      "itemId": "orderiddegeri1",
      "paymentTransactionId": "11791668",
      "transactionStatus": 2,
      "price": 100,
      "paidPrice": 110.5,
      "merchantCommissionRate": 10.5,
      "merchantCommissionRateAmount": 10.5,
      "iyziCommissionRateAmount": 5.33715,
      "iyziCommissionFee": 0.25,
      "blockageRate": 0,
      "blockageRateAmountMerchant": 0,
      "blockageRateAmountSubMerchant": 0,
      "blockageResolvedDate": "2018-12-20 00:00:00",
      "subMerchantPrice": 0,
      "subMerchantPayoutRate": 0,
      "subMerchantPayoutAmount": 0,
      "merchantPayoutAmount": 104.91285,
      "convertedPayout": {
        "paidPrice": 110.5,
        "iyziCommissionRateAmount": 5.33715,
        "iyziCommissionFee": 0.25,
        "blockageRateAmountMerchant": 0,
        "blockageRateAmountSubMerchant": 0,
        "subMerchantPayoutAmount": 0,
        "merchantPayoutAmount": 104.91285,
        "iyziConversionRate": 0,
        "iyziConversionRateAmount": 0,
        "currency": "TRY"
      }
    }
  ],
  "authCode": "914653",
  "phase": "AUTH",
  "hostReference": "mock00001iyzihostrfn"
}

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

