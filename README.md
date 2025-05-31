# Diyabet Hastalığı Tahmini - Apache Spark Projesi

## Proje Hakkında

Bu projede, bir bireyin diyabet hastası olup olmadığını sağlık verilerine bakarak tahmin etmeyi amaçladım. Büyük veri teknolojisi olan Apache Spark'ı kullanarak modelleme yaptım. Veri seti görece küçük olsa da Spark’ın paralel işlem avantajlarından faydalanarak işlemleri daha hızlı ve modüler hale getirdim. Proje sürecinde veriyi temizledim, analiz ettim ve basit bir makine öğrenmesi modeli kurarak sonuçları değerlendirdim.

## Kullanılan Teknolojiler

- **Apache Spark (PySpark)**: Veri işleme ve modelleme
- **Google Colab**: Spark kurulumu ve çalışma ortamı
- **Pandas, Seaborn, Matplotlib**: Görselleştirme ve analiz
- **scikit-learn**: Model değerlendirme metrikleri

## Veri Seti

- **Kaynak**: diabetes.csv
- **Gözlem Sayısı**: 768
- **Hedef Değişken**: `Outcome` (0 = Diyabet yok, 1 = Diyabet var)

### Değişkenler:

| Sütun | Açıklama |
|-------|----------|
| Pregnancies | Gebelik sayısı |
| Glucose | Kan şekeri |
| BloodPressure | Kan basıncı |
| SkinThickness | Deri kalınlığı |
| Insulin | İnsülin seviyesi |
| BMI | Vücut kitle indeksi |
| DiabetesPedigreeFunction | Genetik risk skoru |
| Age | Yaş |
| Outcome | Hedef değişken |

## Veri Ön İşleme

Veri setinde bazı tıbben geçersiz 0 değerleri vardı (örneğin Glucose, BMI gibi). Bu değerleri eksik veri olarak kabul edip, ilgili sütunun ortalama değeriyle doldurdum. Bu sayede modelin öğrenmesini olumsuz etkileyebilecek eksiklikleri giderdim.

## Keşifsel Veri Analizi (EDA)

Veriyi tanımak için bazı temel grafikler kullandım:

- **Sınıf Dağılımı**: Diyabet olan ve olmayan bireylerin sayısı.
- **Korelasyon Matrisi**: Hangi değişkenlerin hedef değişkenle daha çok ilişkili olduğunu görmek için.
- **Boxplot**: Özelliklerin Outcome=0 ve Outcome=1 için dağılımını inceledim.

Bu adımlar modelleme öncesi veri hakkında fikir sahibi olmamı sağladı.

## Özellik Vektörü Oluşturma

Spark’ta makine öğrenmesi için tüm değişkenleri tek bir `features` vektörüne dönüştürmek gerekiyor. Bu işlem için `VectorAssembler` kullandım.

## Modelleme

- **Model**: Logistic Regression
- **Veri Bölme**: Veriyi %80 eğitim, %20 test olarak ayırdım.
- Modeli eğittikten sonra test verisi üzerinde tahmin yaptım ve başarıyı ölçtüm.

## Değerlendirme Metrikleri

Modelin performansını şu metriklerle değerlendirdim:

| Metrik | Değer |
|--------|-------|
| ROC-AUC | 0.8341 |
| Accuracy | 0.7922 |
| Precision | 0.7308 |
| Recall | 0.6735 |
| F1 Score | 0.7010 |

**Confusion Matrix:**
[[87 13]
[15 31]]

## Neden Spark?

- Gerçek zamanlı ve paralel işlem avantajı
- Kodun daha modüler ve genişletilebilir olması
- Büyük veriyle çalışmaya uygun yapı

## Sonuç

Veri temizleme, analiz ve modelleme sürecini Apache Spark ile yürüttüm. Logistic Regression ile sonuçlar elde ettim (ROC AUC ≈ 0.83). 

