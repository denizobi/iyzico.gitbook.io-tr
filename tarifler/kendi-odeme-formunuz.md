---
description: >-
  Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde
  konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir.
---

# Kendi ödeme formunuz \(API\)

Öncelikle iyzico'nun POSTMAN kütüphanesini import edebilirsiniz. Bu kütüphane ile programlama dili bağımsız olarak sorgularınızı test edip yanıtlarını görebilirsiniz.

{% hint style="warning" %}
[https://www.getpostman.com/collections/e883cd2eb09bf55cb1ff](https://www.getpostman.com/collections/e883cd2eb09bf55cb1ff)
{% endhint %}

![POSTMAN g&#xF6;r&#xFC;n&#xFC;m](../.gitbook/assets/image%20%2811%29.png)

### **Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit \(iş modeliniz uygun ise\) oranlarını yanıt olarak alabilirsiniz.

### **Ödeme**

Bu servisi kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) bir karttan para çekimi sağlayabilirsiniz. 

### **3D  Ödeme Başlat**

Bu servisleri kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) 3D ile ödeme başlatabilirsiniz. 

### **3D  Ödeme Bitir**

Bu servisi kullanarak başlatılan bir 3D ödemesinin, dönüş adresinize POST edilen sonucuna göre 3D Ödemeyi bitirebilirsiniz.

### İşlem Sorgula

İşlem sorgulama servisi ile herhangi bir ödeme işlemini, ilgili ödeme / 3D ödeme başlat üzerindeki conversationId değeri ile sorgulayabilirsiniz.

### İptal

Tahsil edilen bir ödeme, banka kuralları gereği aynı gün içinde \(gün sonu yapılmadan\) iptal edilebilir.

### İade

Tahsil edilen bir ödeme, 365 gün 7/24 iade edilebilir.

### Günlük İşlemler

Gün içerisinde yapılan işlemlerin raporunu alabilirsiniz.

