# Kendi ödeme formunuz

API entegrasyonunda üye işyeri kendi ödeme formunu kullanır. Bu form üzerindeki kontrolleri ve kuralları uygulaması gerekir.

* Kart numarası\(PAN\) luhn algoritmasına tabi tutulmalıdır.
* Kartın hamilinin adı ve soyadı alınmalıdır.
* Son kullanma tarihi geçmiş kartlar ile API'ye sorgu yapılmamalıdır.
* AMEX kartları ile işlem alabilir şekilde tasarlanmalıdır.

iyzico arka planda çalıştığından üye işyerinin ihtiyaçlarına göre istenilen servisler entegre edilebilir.

**Taksit ve Bin Sorgulama**

Bu servisi kullanarak işleme gönderilecek kartın ilk 6 hanesinden, işlem yapılmak istenen kart ile ilgili bilgi edinebilir ve ek olarak taksit oranlarını yanıt olarak alabilirsiniz. Bu servis ile ilgili detaylı bilgiyi [Taksit ve Bin Sorgulama](https://dev.iyzipay.com/tr/api/taksit-sorgulama) sayfamızdan edinebilirsiniz.

**Ödeme**

Tek çekim, taksitli, tek tıkla ödeme ve abonelik işlemleri için kullanılabilir. İşleme gönderilen kartın bakiyesinden ilgili miktarı çekme işlemi yapılır. Bu servis ile ilgili detaylı bilgiyi [Ödeme](https://dev.iyzipay.com/tr/api/odeme) sayfamızdan edinebilirsiniz.

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

