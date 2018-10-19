---
description: Gelişmiş fonksiyonları ve topluluğu bulunan açık kaynaklı eticaret platformu
---

# Prestashop

{% hint style="info" %}
iyzico prestashop modülü, yalın prestashop \(eklentisiz\) kurulumu üzerinde geliştirilip test edilmiştir. Kurulum yaparken mutlaka bu uyarıyı dikkate alınız.
{% endhint %}

Partnerlerimizden [Kahvedigital](http://kahvedigital.com/) tarafından geliştirilen ve [github.com/kahvedigital](https://github.com/kahvedigital) hesabında bulunan modüllerden, websitenizin altyapısına uygun olan modülü aşağıdaki linkler üzerinden indirebilirsiniz.

​[Prestashop 1.6 altyapısı için ödeme modülü](https://github.com/kahvedigital/iyzico-prestashop/archive/master.zip) [Prestashop 1.7 altyapısı için ödeme modülü](https://github.com/iyzico/iyzipay-prestashop/archive/master.zip)​

**PrestaShop modülünü nasıl entegre edeceğim? \(Prestashop 1.6\)**

Aşağıdaki entegrasyon adımlarını takip ederek veya iyzico prestashop videomuzu izleyerek prestashop entegrasyonunu gerçekleştirebilirsiniz.​

{% embed url="https://youtu.be/y7ZwYdzixFE" %}

1. İndirdiğiniz modülün içindeki dosyaları bir FTP ile PrestaShop dizinindeki "Modules" klasörünün altına yükleyin.
2. PrestaShop yönetim paneline girip, Modüller&gt; Modüller menüsüne ulaşın.
3. Modül arama alanına iyzico yazarak modülü bulun ve yükleyin.
4. Gelen uyarıda "Yükleme İşlemine Devam" butonuna tıklayarak kurulumu sürdürün.
5. iyzico Kontrol Panelinize giriş yapın. Sağ üstteki Ayarlar sekmesinden API Key ve Secret Key değerlerinizin olduğu menüye girin. Bu değerleri PrestaShop’taki yönetim sayfanızda ilgili alanlara kopyalayın.
6. Form Class ayarından ödeme sayfasının “Responsive” veya “PopUp” olarak seçimini yapın.
7. Kaydet butonuna bastıktan sonra iyzico'yu kullanmaya başlayabilirsiniz.

**PrestaShop modülünü nasıl entegre edeceğim? \(Prestashop 1.7\)**

Aşağıdaki entegrasyon adımlarını takip ederek veya iyzico prestashop videomuzu izleyerek prestashop entegrasyonunu gerçekleştirebilirsiniz.​

{% embed url="https://youtu.be/y7ZwYdzixFE" %}

1. İndirdiğiniz modülün içindeki “iyzicocheckoutform” klasörünü zip dosyası haline getiriniz
2. Prestashop panelinizin sol menüsünden moduls sekmesini açın ve sağ üst köşedeki “upload a module” seçeneğini tıklayınız.
3. “upload a module” seçeneğini tıkladıktan sonra iyzico modülünü yükleyebileceğiniz bir panel açılacaktır .Zip dosyası haline getirdiğiniz iyzico modül dosyasını bu panele sürükleyiniz .
4. iyzico eklentisini kurduktan sonra düzenle butonuna tıklayın. Bu aşamada sizden iyzico Api ve güvenlik anahtarlarınızı girmeniz istenecektir .
5. iyzico Kontrol Panelinize giriş yapın. Sağ üstteki Ayarlar sekmesinden API Key ve Secret Key değerlerinizin olduğu menüye giriş yapacaksınız. Bu değerleri Prestashop yönetim sayfanızda ilgili alanlara kopyalayın.
6. Form Class ayarından ödeme sayfasının "Responsive" veya "PopUp" olarak seçimini yapın.Responsive ve pop-up ödeme formunun sitilini belirtmektedir . Herhangi birini tercih edebilirsiniz .
7. Kaydet butonuna bastıktan sonra iyzico'yu kullanmaya başlayabilirsiniz

{% hint style="info" %}
Kurulumu bitirdikten sonra mutlaka en az 1 tane gerçek kredi kartınızla cüzi tutarlı bir ödeme yapmanızı öneririz. Bu deneme işlemini iyzico panelinizden anında iptal edebilirsiniz. Başarılı bir test işleminin ardından başvuru durumunuzu “Entegrasyon aşamasından ” “Canlı ” moda güncelliyor olacağız.
{% endhint %}

