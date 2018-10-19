---
description: 'Türkiye''de en çok tercih edilen açık kaynaklı, php tabanlı eticaret platformu'
---

# Opencart

{% hint style="info" %}
iyzico Opencart modülü, yalın opencart \(eklentisiz\) kurulumu üzerinde geliştirilip test edilmiştir. Kurulum yaparken mutlaka bu uyarıyı dikkate alınız.
{% endhint %}

Partnerlerimizden [Kahvedigital](http://kahvedigital.com/) tarafından geliştirilen ve [github.com/kahvedigital](https://github.com/kahvedigital) hesabında bulunan modüllerden, websitenizin altyapısına uygun olan modülü aşağıdaki linkler üzerinden indirebilirsiniz.

* [Opencart 3.x modülü](https://github.com/iyzico/iyzipay-opencart/archive/3.x_1.1.zip)
* [Opencart 2.3 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/2.3.x.zip)
* [Opencart 2.0-2.2 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/2.2.x.zip)
* [Opencart 1.5 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/1.5.6.zip)

### **OpenCart modülünü nasıl entegre edeceğim?**

Aşağıdaki entegrasyon adımlarını takip ederek veya iyzico opencart videomuzu izleyerek opencart entegrasyonunu gerçekleştirebilirsiniz.

{% embed url="https://youtu.be/b3P\_SuLMg0c" %}

1. İndirdiğiniz modülün içindeki dosyaları Opencart'ın çalıştığı dizinine yükleyin.
2. Opencart yönetim panelinizdeki Eklentiler menüsünden ödemeleri tıklayın.
3. iyzico eklentisini listeden bulup kurduktan sonra düzenle linkine tıklayın. Bu aşamada sizden iyzico Api ve Güvenlik anahtarlarınızı girmeniz istenecektir.
4. iyzico Kontrol Panelinize giriş yapın. Sağ üstteki Ayarlar sekmesinden API ve Güvenlik anahtarınızı olduğu sayfadan değerleri alıp bu değerleri Opencart'taki yönetim sayfanızda ilgili alanlara kopyalayın. Api ve Güvenlik anahtarınızı kopyalarken baştan ve sondan boşluk kalmamasına dikkat ediniz.
5. "Satın Al" sonrası durum için hazırlanıyor seçeneğini seçin.
6. Form Class ayarından ödeme sayfasının "Responsive" veya "PopUp" olarak seçimini yapın.Responsive ve pop-up ödeme formunun sitilini belirtmektedir. Herhangi birini tercih edebilirsiniz.
7. Modül durumunu "açık" hale getirin.
8. Kaydet butonuna bastıktan sonra iyzico'yu kullanmaya başlayabilirsiniz.

{% hint style="info" %}
Kurulumu bitirdikten sonra mutlaka en az 1 tane gerçek kredi kartınızla cüzi tutarlı bir ödeme yapmanızı öneririz. Bu deneme işlemini iyzico panelinizden anında iptal edebilirsiniz. Başarılı bir test işleminin ardından başvuru durumunuzu “Entegrasyon aşamasından ” “Canlı ” moda güncelliyor olacağız.
{% endhint %}

### Demo kurulum

[Buradan](https://www.iyziodeme.com/test/opencart/3.0.2.0/upload) demo opencart kurulumumuzu inceleyebilirsiniz.

