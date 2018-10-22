---
description: Dünyanın en çok kullanılan eticaret platformu - shopify.com
---

# Shopify

iyzico entegrasyon sürecini sizler için daha anlaşılabilir ve kolay kılmak için bir entegrasyon rehberi hazırladık.

Rehberde yanıt bulamadığınız ve de anlaşılır gelmeyen konularla ilgili bize  entegrasyon@iyzico.com adresi üzerinden ulaşabilirsiniz, sizlere yardımcı olmaktan mutluluk duyarız.

1. **Api anahtaraları :** Siteniz üzerinde iyzico ile bağlantı kurmanız için gerekli olan anahtarlardır.
2. **Sitenizin altyapısı :** Sitenizin altyapısına uygun modülümüzü indirerek entegrasyonu gerçekleştirmelisiniz.
3. **Entegrasyon testleri :** Ödeme sisteminin sitenizde sağlıklı şekilde çalıştığından emin olmak için gerekli olan en temel testlerdir.

### **Api Anahtarı ve Güvenlik Anahtarı**  <a id="api-anahtari-ve-guevenlik-anahtari"></a>

"API Anahtarı" ve "Güvenlik Anahtarı" bilgilerine iyzico panelinize [https://merchant.iyzipay.com/login](https://merchant.iyzipay.com/login) adresinden girerek,  Ayarlar menüsünden ulaşabilirsiniz.

Api anahtarlarınız iyzico ile bağlantı kurmanızı sağlayan temel değerlerdir.

![](../.gitbook/assets/screen_shot_2018-07-11_at_10_13_26%20%282%29.png)

### **Shopify Kurulumu**

{% embed url="https://www.shopify.com/login?redirect=%2Fadmin%2Fauthorize\_gateway%2F1030202" caption="Shopify-iyzico kurulum linki" %}

Yukarıdaki linke tıklayarak, shopify siteniz için iyzico ödeme sistemini aktif edin.

**Adım 1.**

Linke tıklayıp, shopify panelinize girdiğinizde, “install payment provider” butonuna tıklayarak iyzico ödeme sistemine onay vermelisiniz.

![](../.gitbook/assets/picture1%20%2810%29.png)

**Adım 2.**

“Accept credit cards” bölümünden iyzico’yu seçin.

![](../.gitbook/assets/picture1%20%285%29.png)

**Adım 3.**

Iyzico api anahtarlarını girin.

![](../.gitbook/assets/picture1%20%288%29.png)

{% hint style="success" %}
Artık siteniz ödeme almak için hazır.
{% endhint %}

### **Entegrasyon Testleri**

-Ödeme \(başarılı ve başarısız\)

-3ds ödeme

-3ds ödemede, 3ds ekranında vazgeç butonuna basmak

-Taksitli ödeme \(sepette taksite izin olmayan bir ürün var ise taksit seçeneklerinin görüntülenmemesi\)

-Sepette birden fazla ürün ile ödeme

Yaptığınız test işlemlerini iyzico kontrol panelinizden kontrol etmeyi unutmayın.

Tüm ödeme işlemlerinizi iyzico panelinizden anında iptal edebilirsiniz.

