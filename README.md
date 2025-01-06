# Şirket Sipariş Yönetim Sistemi

## Proje Açıklaması

Şirket Sipariş Yönetim Sistemi, şirket siparişlerinin yönetimini sağlayan güçlü bir backend API olarak tasarlanmıştır. Bu API, ileride Blazor tabanlı bir yönetim paneli gibi genişlemelere olanak sağlayacak şekilde uygulamanın çekirdeğini oluşturmaktadır. Proje, ölçeklenebilirlik ve genişletilebilirlik göz önünde bulundurularak Faz 1 olarak geliştirilmiştir.

### Temel Özellikler:

- **API Odaklı**: Frontend, backend ile API üzerinden iletişim kurar.
- **Soğan Mimarisi**: Sürdürülebilir ve ölçeklenebilir kod tabanı sağlar.
- **Repository Pattern & CQRS**: Verimli ve temiz veri yönetimi.
- **Servis Katmanı**: İş mantığını kapsüller.
- **SOLID Prensipleri**: Yüksek kaliteli ve sürdürülebilir kod sağlar.
- **Dependency Injection**: Bağımlılıkların yönetimi için.
- **CodeFirst ve EntityFramework**: MSSQL veritabanı CodeFirst yaklaşımı ile.
- **UnitOfWork Pattern**: Veri işlemlerini yönetir.
- **Standart DTOlar & ApiResponse**: Tutarlı veri transferi ve yanıtlar için.
- **Birim Testleri**: %70 kapsama oranı ile kod kalitesini sağlar.
- **Hata Yönetimi**: Hataları yönetmek için sağlam sistem.
- **Önbellekleme**: Şirket ve Ürün Kategorileri için dahili önbellekleme.
- **Başlangıç Verisi**: İlk veri kurulumu.

## Veritabanı Varlıkları

### Şirket : TemelVarlık
- Id
- Ad
- Açıklama
- Kullanıcı
- Ürünler
- Siparişler
- OluşturulmaTarihi
- SonGüncellemeTarihi

### Ürün : TemelVarlık
- Id
- Ad
- Açıklama
- StokSayısı
- Fiyat
- Şirket
- ÜrünKategorisi
- OluşturulmaTarihi
- SonGüncellemeTarihi

### ÜrünKategorisi : TemelVarlık
- Id
- Ad
- Açıklama
- Ürünler
- OluşturulmaTarihi
- SonGüncellemeTarihi

### Sipariş : TemelVarlık
- Id
- Ad
- SiparişSayısı
- BirimFiyat
- ToplamFiyat
- SiparişDurumu (Beklemede, Başarılı, Başarısız)
- Şirket
- Ürün
- Kullanıcı
- OluşturulmaTarihi
- SonGüncellemeTarihi

### Kullanıcı : TemelVarlık
- Id
- Ad
- Açıklama
- Siparişler
- OluşturulmaTarihi
- SonGüncellemeTarihi

Bu varlıklarla ilgili standart işlemler uygulanacaktır (örn. ürün oluşturma, sipariş verme, kullanıcı kaydı). Gerektiğinde ek alanlar eklenebilir.

## Başlangıç

Projeyi başlatmak için aşağıdaki adımları izleyin:

1. **Depoyu Klonlayın**:
   ```sh
   git clone https://github.com/ahmedokumus/OrderManagement.git
   cd OrderManagement
   ```

2. **Bağımlılıkları Yükleyin**:
   ```sh
   dotnet restore
   ```

3. **Veritabanını Oluşturun**:
   ```sh
   dotnet ef database update
   ```

4. **Uygulamayı Çalıştırın**:
   ```sh
   dotnet run
   ```

5. **Testleri Çalıştırın**:
   ```sh
   dotnet test
   ```
