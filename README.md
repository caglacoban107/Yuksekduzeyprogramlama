# Yuksekduzeyprogramlama
proje
Proje Raporu: Cleaned vs Dirty Görüntü Sınıflandırma
1. Proje Amacı
Bu proje, Kaggle'dan alınan 'Cleaned vs Dirty' veri setini kullanarak, temiz ('cleaned') ve kirli ('dirty') görüntülerin sınıflandırılmasını amaçlamaktadır. Proje kapsamında ResNet152 modeli ile transfer öğrenme uygulanmıştır.
2. Veri Seti ve Ön İşleme
**Veri Seti:**
- ZIP formatında alınan veri seti, `/kaggle/working/plates/` klasörüne çıkarılmıştır.
- Görseller, 'cleaned' ve 'dirty' olarak iki sınıfa ayrılmıştır.
- Eğitim (%80), doğrulama (%10), test (%10) oranlarında bölünmüştür.

**Ön İşleme:**
- Görseller, `rembg` kütüphanesi kullanılarak arka plan temizleme işlemine tabi tutulmuştur.
- Veri artırımı (rotation, crop, flip) gibi işlemler uygulanmıştır.
3. Model ve Eğitim Süreci
**Kullanılan Model:**
- ResNet152 modeli kullanılmış ve transfer öğrenme uygulanmıştır.
- Modelin son katmanı yeniden yapılandırılarak 'cleaned' ve 'dirty' sınıflarını sınıflandıracak şekilde düzenlenmiştir.

**Eğitim Süreci:**
- Eğitim için veri yükleyiciler tanımlanmıştır.
- Model, Binary Cross Entropy kayıp fonksiyonu ve Adam optimizer ile eğitilmiştir.
- Eğitim 200 epoch boyunca gerçekleştirilmiştir.
4. Model Değerlendirmesi
**Eğitim Sonuçları:**
- Eğitim doğruluğu: %100'e yaklaştı.
- Doğrulama doğruluğu: %87.5

**Performans Ölçütleri:**
- Kayıp ve doğruluk değerleri, epoch başına kaydedilmiştir.
- Eğitim ve doğrulama kayıpları giderek azalmış, doğruluk oranları artmıştır.
5. Sonuçlar ve Değerlendirme
**Sonuçlar:**
- Test setinde yapılan tahminler başarıyla sonuçlandırılmıştır.
- Modelin çıktıları şu şekilde kaydedilmiştir:
  - 0000 cleaned
  - 0001 dirty
  - 0002 dirty

**Değerlendirme:**
- Veri setinin sınırlı olması genelleme yeteneğini kısıtlamış olabilir.
- Eğitimde kullanılan veri artırma teknikleri modelin doğruluğunu artırmıştır.
6. Projenin Çalıştırılması
**Gereksinimler:**
- Python ve gerekli kütüphaneler (`torch`, `rembg`, `torchvision`, vb.) yüklü olmalıdır.

**Adımlar:**
1. Veri seti ZIP dosyasını `/kaggle/working/plates/` dizinine çıkarın.
2. Jupyter Notebook'u açarak veri işleme ve model eğitimi bölümlerini çalıştırın.
3. Çıktılar `submission.csv` dosyasında kaydedilecektir.

