---
description: iyzilink
---

# iyzilink API

5 servisten oluşan iyzilink ürünümüzü PHP kütüphanemiz ile kullanabilirsiniz. 

## Ürün ekle

Sadece PHP kütüphanemizde bulunmaktadır.

[https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink\_add\_product\_sample.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink_add_product_sample.php)

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr", // tr ve en değerleri desteklenmektedir.
  "conversationId": "123456789", // sipariş numarası gibi set edebilirsiniz.
  "price": "1.0", // ürünün fiyatı
  "name": "Sample Integration", // ürünün ismi
  "description": "Sample Integration", // ürünün tanımı
  "encodedImageFile": "/9j/4AAQSkZJRgABAQEAYABgAAD//", // ürünün fotoğrafı
  "currencyCode": "TRY", // para birimi
  "addressIgnorable": false, // satın alma esnasında adres bilgisi istensin mi ?
  "soldLimit": 1, // stok miktarı
  "installmentRequested": false // taksitli satışa uygun ürün bilgisi
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success", // sorgunun yanıtı
  "locale": "tr", // gönderilen dil parametresi
  "systemTime": 1545225967963, // unix zaman damgası
  "conversationId": "123456789", // sipariş numarası
  "data": {
    "token": "BLA", //iyzico tarafından üretilen değer
    "url": "https://sandbox.iyzi.link/BLA", // ürünün satın alma linki
    "imageUrl": "https://sandbox-img.iyzi.link/BL/A.jpg" // ürün resmi
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün Sil

Sadece PHP kütüphanemizde bulunmaktadır.

[https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink\_delete\_product\_sample.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink_delete_product_sample.php)

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr", // tr ve en değerleri desteklenmektedir.
  "conversationId": "123456789", // sipariş numarası gibi set edebilirsiniz.
  "token": "BLA" // iyzico'nun ürün için döndüğü değer
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success", // sorgunun yanıtı
  "locale": "tr", // gönderilen dil parametresi
  "systemTime": 1545226229597, // unix zaman damgası
  "conversationId": "123456789" // sipariş numarası
}

```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün Getir

Sadece PHP kütüphanemizde bulunmaktadır.

[https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink\_retrieve\_product\_sample.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink_retrieve_product_sample.php)

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr", // tr ve en değerleri desteklenmektedir.
  "conversationId": "123456789",  // sipariş numarası gibi set edebilirsiniz.
  "token": "BLA" // iyzico'nun ürün için döndüğü değer
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success", // sorgunun yanıtı
  "locale": "tr", // gönderilen dil parametresi
  "systemTime": 1545226460890, // unix zaman damgası
  "conversationId": "123456789", // sipariş numarası
  "data": {
    "name": "Sample Integration", // ürünün ismi
    "conversationId": "123456789", // sipariş numarası 
    "description": "Sample Integration", // ürünün tanımı
    "price": 1, // ürünün fiyatı
    "currencyId": 1, // ürünün para birimi idsi
    "currencyCode": "TRY", // ürünün para birimi
    "token": "BLE", //iyzico tarafından üretilen değer
    "productType": "IYZILINK", // iyzico tarafından kullanılan tip
    "productStatus": "ACTIVE", // ürünün durumu
    "merchantId": 50343, // iyzico'daki üye işyeri numarası
    "url": "https://sandbox.iyzi.link/BLE", // ürünün satın alma linki
    "imageUrl": "https://sandbox-img.iyzi.link/BL/E.jpg", // ürün resmi
    "addressIgnorable": false, // ürün adres durumu
    "soldCount": 0, // satılan ürün sayısı
    "soldLimit": 1, // toplam stok sayısı
    "remainingSoldLimit": 1, // kalan stok sayısı
    "installmentRequested": false // taksit yapılabilir durumu
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürünleri Getir

Sadece PHP kütüphanemizde bulunmaktadır.

[https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink\_retrieve\_products\_sample.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink_retrieve_products_sample.php)

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr", // tr ve en değerleri desteklenmektedir.
  "conversationId": "123456789", // sipariş numarası gibi set edebilirsiniz.
  "page": 1, // sayfa numarası
  "count": 2 // sayfada görüntülenen ürün sayısı
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success", // sorgunun yanıtı
  "locale": "tr", // gönderilen dil parametresi
  "systemTime": 1545226669152, // unix zaman damgası
  "conversationId": "123456789", // sipariş numarası
  "data": {
    "listingReviewed": true, // listeleme durumu
    "totalCount": 20, // gösterilen toplam sayfa
    "currentPage": 1, // bulunduğunuz sayfa
    "pageCount": 10, // toplam sayfa
    "items": [
      {
        "name": "Sample Integration", // ürünün ismi
        "conversationId": "123456789", // sipariş numarası 
        "description": "Sample Integration", // ürünün tanımı
        "price": 1, // ürünün fiyatı
        "currencyId": 1, // ürünün para birim idsi
        "currencyCode": "TRY", // ürünün para birimi
        "token": "BLE", //iyzico tarafından üretilen değer
        "productType": "IYZILINK", // iyzico tarafından kullanılan tip
        "productStatus": "ACTIVE", // ürünün durumu
        "merchantId": 50343, // iyzico'daki üye işyeri numarası
        "url": "https://sandbox.iyzi.link/BLE", // ürünün satın alma linki
        "imageUrl": "https://sandbox-img.iyzi.link/BL/E.jpg", // ürün resmi
        "addressIgnorable": false, // ürün adres durumu
        "soldCount": 0, // satılan ürün sayısı
        "soldLimit": 1, // toplam stok sayısı
        "remainingSoldLimit": 1, // kalan stok sayısı
        "installmentRequested": false // taksit yapılabilir durumu
      },
      {
        "name": "product-name", // ürünün ismi
        "description": "product-description", // ürünün tanımı
        "price": 5, // ürünün fiyatı
        "currencyId": 1, // ürünün para birim idsi
        "currencyCode": "TRY", // ürünün para birimi
        "token": "BK4", //iyzico tarafından üretilen değer
        "productType": "IYZILINK", // iyzico tarafından kullanılan tip
        "productStatus": "ACTIVE", // ürünün durumu
        "merchantId": 50343, // iyzico'daki üye işyeri numarası
        "url": "https://sandbox.iyzi.link/BK4", // ürünün satın alma linki
        "imageUrl": "https://sandbox-img.iyzi.link/BK/4.jpg", // ürün resmi
        "addressIgnorable": true, // ürün adres durumu
        "soldCount": 1, // satılan ürün sayısı
        "soldLimit": 0, // toplam stok sayısı
        "remainingSoldLimit": -1, // kalan stok sayısı
        "installmentRequested": false // taksit yapılabilir durumu
      }
    ]
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün güncelle

Sadece PHP kütüphanemizde bulunmaktadır.

[https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink\_update\_product\_sample.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/iyzilink_update_product_sample.php)

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr",
  "conversationId": "123456789",
  "price": "1.0",
  "name": "Sample Integration",
  "description": "Sample Integration",
  "encodedImageFile": "/9j/4AAQSkZJRgABAQEAYABgAAD//",
  "currencyCode": "TRY",
  "addressIgnorable": false,
  "soldLimit": 1,
  "installmentRequested": false,
  "token": "BKA"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1545226810662,
  "conversationId": "123456789",
  "data": {
    "token": "BK4",
    "url": "https://sandbox.iyzi.link/BK4",
    "imageUrl": "https://sandbox-img.iyzi.link/BK/4+V1.jpg"
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

