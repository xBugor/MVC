#### MVC NEDİR ? (Model-View-Controller)
 Yazılım geliştirmede kullanılan(özellikle webte) geliştirme patternidir.(Yazılım mimari deseni).



 
![xBugor ][resim]

[resim]: ./assets/mvc.jpg "Bugrahan"


Modüler bir yaklaşım kullanarak yazlımı parçalara ayırıyoruz.Bu da bir bileşende yapılan değişiklikleri bağımsızlaştırır. Bu parçalar:

* Model
* View
* Controller
* User 

### Model 

1. Verinin yönetilmesi ve iş mantığının çalışmasını yönetir.
2. Veritabanı ile iletişim kurar.
3. Controllere veri sağlar.
4. Validation işlemini gerçekleştirir.
Örnek (Django Model - Python)

### View
 Projelerimizde arayüzlerin oluştuğu bölüme view denir. Kullanıcının iletişim kuracağı ekrana view diyoruz.


 1. Kullanıcıya verileri görüntüler
 2. HTML ,CSS ,JavaScript  kullanarak görsel bir arayüz sunar.


### Controller

 1. Kullanıcıdan gelen istekler burda değerlendirilir. İsteğin detaylarına göre hangi işlemin yapılacağını seçer.(veri güncelleme gibi )

2. Gerekli verileri Model’den alır, üzerinde işlem yapar ve View’e (görünüme) yönlendirir.
 View’e işlenmiş verileri iletir ve istemciye HTML, JSON veya başka bir formatta yanıt döndürülmesini sağlar.


| Framework       | Programlama Dili | Kullanım Alanı          |
|---------------|----------------|----------------------|
| **Django**     | Python         | Web uygulamaları     |
| **Laravel**    | PHP            | Web geliştirme      |
| **Ruby on Rails** | Ruby        | Web & API geliştirme |
| **Spring MVC** | Java           | Kurumsal uygulamalar |
| **ASP.NET MVC** | C#            | Microsoft tabanlı web uygulamaları |





| Avantajlar                                 | Dezavantajlar                                |
|--------------------------------------------|----------------------------------------------|
| **Modülerlik**: Her bileşenin ayrı olması, geliştirme sürecini daha düzenli hale getirir. | **Başlangıç Karmaşıklığı**: Yeni başlayanlar için tasarım deseninin anlaşılması zor olabilir. |
| **Test Edilebilirlik**: Model, View ve Controller arasındaki ayrım, her bileşenin bağımsız test edilmesini kolaylaştırır. | **Performans Sorunları**: MVC'nin eklediği soyutlama, performans kaybına yol açabilir. |
| **Bakım Kolaylığı**: Değişiklikler yalnızca ilgili bileşende yapılabilir, bu da bakım sürecini basitleştirir. | **Zaman Alıcı Başlangıç**: İlk kurulum ve yapılandırma süreci daha uzun olabilir. |
| **Yeniden Kullanılabilirlik**: Her bileşen bağımsız olarak kullanılabilir ve yeniden kullanılabilir. | **Karmaşık Yapılar**: Büyük projelerde MVC yapısı, fazladan dosya ve kod yönetimi gerektirebilir. |

Senaryo 
Kullanıcı bir istek oluşturuyor (Request)
Kullanıcı bir girdi oluşturduğu zaman bu girdiler Controllera geliyor.
Bu veriler üzerinde ne yapılacağına lojik denir.
Controller üzerinde Model(veritabanına) yapılacak bir işlem varsa yapar. Örneğin veri getirme veya kaydetme gibi
Sonra bu veriler view ile kullanıcıya sunulur. Aşağıdaki diagramda bu senaryo anlatıldı.

```mermaid
sequenceDiagram
    participant Kullanıcı
    participant Controller
    participant Model
    participant View
    Kullanıcı->>Controller: REQUEST 
    Controller->>Model: Veriyi  getir
    Model-->>Controller:  Veriyi döndür
    Controller->>View: Ürünü HTML içinde göster
    View-->>Kullanıcı: Sayfayı döndür