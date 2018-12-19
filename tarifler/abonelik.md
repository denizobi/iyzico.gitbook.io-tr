# Abonelik \(subscription\)

iyzico alt yapısında kart saklama özelliği bulunmaktadır. iyzico panelinize giriş yaptıktan sonra sol menüdeki "**Eklentiler**" bölümünden "**Kart Saklama**" uygulamasını satın alarak kart saklama özelliğinden faydalanabilirsiniz . 

Bir ödeme sırasında \(veya ödemeden bağımsız\) müşterinizin kartını iyzico alt yapısında saklayabilirsiniz.

Kartı sakladıktan sonra bu kartı temsilen iyzico tarafından size “**cardToken**” ve “**cardUserKey**” bilgisi dönmektedir.

cardToken ve cardUserKey bilgileri ile dilediğiniz zaman ve tutarda tekrar ödeme isteği gönderebilirsiniz, bu şekilde abonelik ödemelerinizi alabilirsiniz.

Ödeme sırasında kart saklama yapmak isterseniz "**registercard"** parametresini "**1**" olarak göndermeniz gerekmektedir .

[https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_payment.php\#L23](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_payment.php#L23)

Ödeme öncesinde kart saklama requesti

[https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_card.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_card.php)

Saklı kart ile ödeme yapma requesti

[https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_payment\_with\_registered\_card.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_payment_with_registered_card.php)

Kart saklama abone özelliğini hazır alt yapılarda \(woocommerce , prestashop , opencart , magento\)  kullanabilmek için kendi tarafınızda bir geliştirme yapmanız gerekmektedir . Müşterileriniz kartımı sakla butonuna bastığında dönen carduserkey ve cardtoken parametreleri ile kendi tasarladığınız ödeme formu üzerinden ödeme alabilirsiniz . Saklı kart ile ödeme örneğimize linkten ulaşabilirsiniz. 

[https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_payment\_with\_registered\_card.php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_payment_with_registered_card.php)

