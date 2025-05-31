# Diyabet Hastalığı Tahmini - Apache Spark Projesi

## Proje Hakkında

Bu projede sağlık verileri kullanılarak bireylerin diyabet hastası olup olmadığı tahmin edilmiştir. Modelleme sürecinde Apache Spark tercih edilmiştir.

## Kullanılan Teknolojiler

- Apache Spark (PySpark)
- Google Colab
- Pandas, Seaborn, Matplotlib
- scikit-learn

## Veri Seti

- Dosya: diabetes.csv  
- Gözlem sayısı: 768  
- Hedef değişken: Outcome (0: Hasta değil, 1: Hasta)

## Değişkenler

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
| Outcome | Diyabet durumu |

## Veri Ön İşleme

Tıbben geçersiz olan sıfır değerler eksik veri kabul edilmiştir. İlgili sütunların ortalama değerleriyle doldurma işlemi yapılmıştır.

## Veri Analizi

Veri dağılımı, korelasyon matrisi ve boxplot grafiklerle analiz edilmiştir. Değişkenlerin hedefle ilişkisi incelenmiştir.

## Modelleme

- Logistic Regression modeli kullanılmıştır.
- Veri %80 eğitim, %20 test olarak ayrılmıştır.
- Özellikler `VectorAssembler` ile birleştirilmiştir.

## Değerlendirme

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

Apache Spark ile verimli ve ölçeklenebilir bir modelleme süreci uygulanmıştır. Logistic Regression modeli ile tatmin edici sonuçlar elde edilmiştir.

