# Kendi ödeme formunuz \(API\)

## Başlarken

Kendi formunu kullanan üye işyeri form üzerindeki kontrolleri ve kuralları uygulaması gerekir. 

* Kart numarası\(PAN\) [luhn](https://www.google.com.tr/search?ei=VmAKXPvIHIeMmgXJv6yoDQ&q=luhn+algorithm&oq=luhn+algorithm&gs_l=psy-ab.3..0j0i67j0l2j0i22i30l6.1196.2533..2822...0.0..0.133.1042.0j9......0....1..gws-wiz.......0i71.R2J5qTjekMY) algoritmasına tabi tutulmalıdır.
* Kartın hamilinin adı ve soyadı alınmalıdır. \(şüpheli aktiviteleri takip etmek için\)
* Son kullanma tarihi geçmiş kartlar ile sorgu yapma engellenmelidir.
* AMEX kartları ile işlem alabilir şekilde tasarlanmalıdır. \([güvenlik kodu](https://www.google.com.tr/search?ei=GmEKXOP6McqQmgWU1KS4Aw&q=cvv+cvc+cid&oq=cvv+cvc+cid&gs_l=psy-ab.3..0i19j0i22i30i19l9.7428.9172..9304...1.0..0.258.740.0j4j1......0....1..gws-wiz.......0j0i22i30j0i22i10i30j0i22i10i30i19j33i160.t2LBYfTt3rU)\)

Bu entegrasyon rehberinde sisteminiz iyzico ile server-to-server şeklinde konuşur. Yapılan tüm isteklere iyzico anlık olarak yanıt verir. **6** ana servisten oluşur. Bu adımları takip ederek entegrasyonunuzu tamamlayabilirsiniz

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

