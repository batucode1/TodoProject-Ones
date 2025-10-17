

# Notely: iOS Not Uygulaması

<img width="1619" height="1730" alt="todo mockup" src="https://github.com/user-attachments/assets/73278c2b-037d-49bf-a7c6-55353c0224de" />

## Temel Özellikler
-   **Firebase ile Güvenli Kimlik Doğrulama:** E-posta ve şifre ile kullanıcı kaydı ve girişi.
-   **Çevrimdışı Öncelikli Çalışma:** SwiftData sayesinde internet bağlantısı olmadan tüm not işlemlerini (oluşturma, düzenleme, silme) sorunsuzca gerçekleştirebilme.
-   **Anlık Bulut Senkronizasyonu:** Firestore veritabanı ile tüm verilerin, bağlantı kurulduğu an bulutla otomatik olarak senkronize edilmesi.

   ## Teknolojiler ve Mimari

Proje, modern iOS geliştirme pratikleri göz önünde bulundurularak **Özellik Odaklı Mimari (Feature-Driven Architecture)** prensibiyle tasarlanmıştır. Bu yaklaşım ile kodun modüler, anlaşılır ve bakımının kolay olması hedeflenmiştir.

-   **UI:** SwiftUI
-   **Yerel Veritabanı (Çevrimdışı Depolama):** SwiftData
-   **Backend & Senkronizasyon:** Google Firebase
    -   **Authentication:** Kullanıcı yönetimi
    -   **Firestore:** Gerçek zamanlı NoSQL veritabanı
## Mimari Yapının Açıklaması


Proje, sorumlulukların net bir şekilde ayrıldığı katmanlı bir yapıya sahiptir:

-   **`Application` Katmanı:** Uygulamanın yaşam döngüsünü (`App`, `AppDelegate`), genel oturum durumunu (`Session`) ve ilk yönlendirme mantığını (`RootView`) içerir. Projenin başlangıç ve ana yapılandırma merkezidir.

-   **`Features` Katmanı:** Uygulamanın ana işlevsel modüllerini barındırır. Her özellik (örneğin `Onboarding`, `Authentication`, `Notes`) kendi klasörü içinde, kendine ait View'ları ve mantığıyla birlikte bulunur. Bu, projenin ölçeklenmesini kolaylaştırır.

-   **`Core` Katmanı:** Uygulamanın merkezi iş mantığını ve altyapısını içerir.
    -   **`Data`:** SwiftData ile tanımlanmış veri modellerini (`AppUser`, `Note`) barındırır.
    -   **`Services`:** `AuthService` ve `FirebaseSyncManager` gibi Firebase ile iletişimi yöneten ve arka plan işlemlerini yürüten servisleri içerir.

-   **`Shared` Katmanı:** Birden fazla özellikte kullanılan, yeniden kullanılabilir bileşenleri ve yardımcı kodları barındırır.
    -   **`UI`:** `CustomTextField` gibi genel UI bileşenleri burada toplanmıştır.
    -   **`Extensions`:** `String` gibi mevcut türlere eklenen yardımcı fonksiyonlar burada yer alır.
 

   ## Geliştirici

  **Batuhan Koç**

Bu proje, **OnesTechnology**'deki staj programım süresince geliştirilmiştir.    
