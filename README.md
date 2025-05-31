# Diyabet Hastalığı Tahmini - Apache Spark ile Büyük Veri Analitiği

## 📌 Proje Tanımı

Bu projede, sağlık verileri kullanılarak bireylerin diyabet hastalığına sahip olup olmadığı makine öğrenmesi ile tahmin edilmiştir. Büyük veri analizinde yaygın olarak kullanılan Apache Spark teknolojisi ile veri işleme, analiz ve modelleme süreçleri gerçekleştirilmiştir. Amaç; Spark'ın dağıtık ve hızlı işlem yeteneklerinden faydalanarak doğruluğu yüksek, tekrar edilebilir ve ölçeklenebilir bir tahmin modeli oluşturmaktır.

---

## 🛠️ Kullanılan Teknolojiler

- Apache Spark (PySpark)
- Google Colab
- Python
- Spark MLlib
- Pandas, Matplotlib, Seaborn
- scikit-learn

---

## 📁 Veri Kümesi

- **Kaynak**: Pima Indians Diabetes Dataset (Kaggle)
- **Dosya**: `diabetes.csv`
- **Gözlem Sayısı**: 768
- **Hedef Değişken**: `Outcome` (0: Diyabet yok, 1: Diyabet var)

| Özellik | Açıklama |
|---------|----------|
| Pregnancies | Gebelik sayısı |
| Glucose | Kan şekeri seviyesi |
| BloodPressure | Kan basıncı |
| SkinThickness | Deri kalınlığı |
| Insulin | İnsülin seviyesi |
| BMI | Vücut kitle indeksi |
| DiabetesPedigreeFunction | Genetik risk skoru |
| Age | Yaş |
| Outcome | Diyabet durumu |

---

## 🔍 Veri Ön İşleme

- Tıbben geçerli olmayan (0) değerler eksik veri olarak değerlendirilmiştir.
- Bu değerler, ilgili sütunların ortalamalarıyla doldurulmuştur.
- Spark DataFrame yapısı üzerinde işlem yapılmıştır.

---

## 📊 Keşifsel Veri Analizi (EDA)

- `Outcome` değişkeninin dağılımı incelenmiştir.
- Korelasyon matrisi çıkarılarak hedef değişken ile ilişkiler analiz edilmiştir.
- Histogram ve boxplot grafikleri ile değişkenlerin dağılımı görselleştirilmiştir.

---

## 🤖 Modelleme Süreci

### Özellik Dönüşümü
- `VectorAssembler` ile bağımsız değişkenler vektör haline getirildi.

### Veri Ayrımı
- Veri seti %80 eğitim, %20 test olacak şekilde bölündü.

### Kullanılan Model
- **Logistic Regression** (Spark MLlib)

---

## 📈 Performans Değerlendirmesi

| Metrik | Değer |
|--------|-------|
| ROC-AUC | 0.8341 |
| Accuracy | 0.7922 |
| Precision | 0.7308 |
| Recall | 0.6735 |
| F1 Score | 0.7010 |

**Confusion Matrix**:
[[87 13]
[15 31]]


## ⚙️ Apache Spark Tercih Sebebi

- **Paralel ve hızlı işlem yapısı** sayesinde büyük veri analizinde verimlidir.
- **MLlib kütüphanesi** ile entegre makine öğrenmesi sunar.
- **Modüler ve ölçeklenebilir yapı** ile gerçek dünyaya uygulanabilir çözümler sağlar.

---

## ✅ Sonuç

Proje kapsamında Apache Spark kullanılarak veri temizleme, analiz ve tahmin süreçleri başarıyla yürütülmüştür. Logistic Regression modeliyle %83 AUC skoru elde edilmiştir. Bu sonuçlar, Spark’ın büyük veri ortamlarında makine öğrenmesi uygulamaları için etkili ve ölçeklenebilir bir çözüm sunduğunu göstermektedir.
