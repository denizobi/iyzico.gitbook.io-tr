---
description: iyzilink
---

# iyzilink API

5 servisten oluşan iyzilink ürünümüzü PHP kütüphanemiz ile kullanabilirsiniz. 

## Ürün ekle

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
  "status": "success",
  "locale": "tr",
  "systemTime": 1545225967963,
  "conversationId": "123456789",
  "data": {
    "token": "BLA",
    "url": "https://sandbox.iyzi.link/BLA",
    "imageUrl": "https://sandbox-img.iyzi.link/BL/A.jpg"
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün Sil

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr",
  "conversationId": "123456789",
  "token": "BLA"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1545226229597,
  "conversationId": "123456789"
}

```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün Getir

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr",
  "conversationId": "123456789",
  "token": "BLA"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1545226460890,
  "conversationId": "123456789",
  "data": {
    "name": "Sample Integration",
    "conversationId": "123456789",
    "description": "Sample Integration",
    "price": 1,
    "currencyId": 1,
    "currencyCode": "TRY",
    "token": "BLE",
    "productType": "IYZILINK",
    "productStatus": "ACTIVE",
    "merchantId": 50343,
    "url": "https://sandbox.iyzi.link/BLE",
    "imageUrl": "https://sandbox-img.iyzi.link/BL/E.jpg",
    "addressIgnorable": false,
    "soldCount": 0,
    "soldLimit": 1,
    "remainingSoldLimit": 1,
    "installmentRequested": false
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürünleri Getir

{% code-tabs %}
{% code-tabs-item title="İstek" %}
```javascript
{
  "locale": "tr",
  "conversationId": "123456789",
  "page": 1,
  "count": 2
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yanıt" %}
```javascript
{
  "status": "success",
  "locale": "tr",
  "systemTime": 1545226669152,
  "conversationId": "123456789",
  "data": {
    "listingReviewed": true,
    "totalCount": 20,
    "currentPage": 1,
    "pageCount": 10,
    "items": [
      {
        "name": "Sample Integration",
        "conversationId": "123456789",
        "description": "Sample Integration",
        "price": 1,
        "currencyId": 1,
        "currencyCode": "TRY",
        "token": "BLE",
        "productType": "IYZILINK",
        "productStatus": "ACTIVE",
        "merchantId": 50343,
        "url": "https://sandbox.iyzi.link/BLE",
        "imageUrl": "https://sandbox-img.iyzi.link/BL/E.jpg",
        "addressIgnorable": false,
        "soldCount": 0,
        "soldLimit": 1,
        "remainingSoldLimit": 1,
        "installmentRequested": false
      },
      {
        "name": "product-name",
        "description": "product-description",
        "price": 5,
        "currencyId": 1,
        "currencyCode": "TRY",
        "token": "BK4",
        "productType": "IYZILINK",
        "productStatus": "ACTIVE",
        "merchantId": 50343,
        "url": "https://sandbox.iyzi.link/BK4",
        "imageUrl": "https://sandbox-img.iyzi.link/BK/4.jpg",
        "addressIgnorable": true,
        "soldCount": 1,
        "soldLimit": 0,
        "remainingSoldLimit": -1,
        "installmentRequested": false
      }
    ]
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Ürün güncelle

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

