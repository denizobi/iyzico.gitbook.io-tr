---
description: >-
  Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde
  konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir.
---

# Kendi ödeme formunuz \(API\)

### **Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit \(iş modeliniz uygun ise\) oranlarını yanıt olarak alabilirsiniz.![Run in Postman](https://run.pstmn.io/button.svg)

### **Ödeme**

Bu servisi kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) bir karttan para çekimi sağlayabilirsiniz. ![Run in Postman](https://run.pstmn.io/button.svg)

### **3D  Ödeme Başlat**

Bu servisleri kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) 3D ile ödeme başlatabilirsiniz. ![Run in Postman](https://run.pstmn.io/button.svg)

### **3D  Ödeme Bitir**

Bu servisi kullanarak başlatılan bir 3D ödemesinin, dönüş adresinize POST edilen sonucuna göre 3D Ödemeyi bitirebilirsiniz.![Run in Postman](https://run.pstmn.io/button.svg)

### İşlem Sorgula

İşlem sorgulama servisi ile herhangi bir ödeme işlemini, ilgili ödeme / 3D ödeme başlat üzerindeki conversationId değeri ile sorgulayabilirsiniz.[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/cb37c0f635cf450839c6)

### İptal

Tahsil edilen bir ödeme, banka kuralları gereği aynı gün içinde \(gün sonu yapılmadan\) iptal edilebilir.[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/942c169c1b93b2e83f86)

### İade

Tahsil edilen bir ödeme, 365 gün 7/24 iade edilebilir.[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/adba0e9bd8f42f995ab1)

### Günlük İşlemler

Gün içerisinde yapılan işlemlerin raporunu alabilirsiniz.[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/b0a9efe82d406cb46d3f)

