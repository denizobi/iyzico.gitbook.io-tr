# Kendi ödeme formunuz \(API\)

Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir. 

### **Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit \(iş modeliniz uygun ise\) oranlarını yanıt olarak alabilirsiniz. Bu serviste dönen oranlar iyzico üye iş yeri panelindeki oranlardır.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/07e3a5ce053078777766)

### **Ödeme**

Bu servisi kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) bir karttan para çekimi sağlayabilirsiniz. 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/92c400ddb66eb28f794d)

### **3D  Ödeme Başlat**

Bu servisleri kullanarak tek çekim veya taksitli olarak \(iş modelinize uygun ise\) 3D ile ödeme başlatabilirsiniz. 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/5b1543edc8e322c94e62)

### **3D  Ödeme Bitir**

Bu servisi kullanarak başlatılan bir 3D ödemesinin, dönüş adresinize POST edilen sonucuna göre 3D Ödemeyi bitirebilirsiniz.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/56e0c3b7584295f7677a)

\*\*\*\*

**Ödeme Sorgulama**

iyzico'da kaydı oluşturulan bir işlemin detayları sorgulanabilir. Bu servis ile ilgili detaylı bilgiyi [Ödeme Sorgulama](https://dev.iyzipay.com/tr/api/odeme-sorgulama) sayfamızdan edinebilirsiniz.

**İptal**

Bankalar gün sonu almadan önce işlemin iptal edilmesidir. Bu servis ile ilgili detaylı bilgiyi [İptal](https://dev.iyzipay.com/tr/api/iptal) sayfamızdan edinebilirsiniz.

**İade**

Bankalar gün sonu aldıktan sonra işlemin kısmi veya tam olarak iade edilmesidir. Bu servis ile ilgili detaylı bilgiyi [İade](https://dev.iyzipay.com/tr/api/iade) sayfamızdan edinebilirsiniz.

