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

İşlem sorgulama servisi ile iyzico'daki herhangi bir ödeme işlemini, ilgili ödeme üzerindeki conversationId değeri ile sorgulayabilirsiniz.

### İptal

### İade

### Günlük İşlemler







<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">Postman</th>
      <th style="text-align:left">PHP</th>
      <th style="text-align:left">.NET</th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Taksit ve BIN</td>
      <td style="text-align:left">
        <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" />
      </td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <img src="../.gitbook/assets/image (2).png" alt/>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD6;dem</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">3D Ba&#x15F;la</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">3D Bitir</td>
      <td style="text-align:left">
        <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" />
      </td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#x130;&#x15F;lem Sorgula</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#x130;ptal</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#x130;ade</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#x130;&#x15F;lem Raporu</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="https://github.com/iyzico/iyzipay-php/releases/latest"><img src="https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png" alt="PHP"/></a>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>
          <img src="../.gitbook/assets/image (2).png" alt/>
        </p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>![](../.gitbook/assets/image%20%287%29.png)

