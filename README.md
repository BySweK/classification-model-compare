# 🩸 Diabetes Prediction & Classification Model Comparison

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange.svg)](https://scikit-learn.org/)
[![Licence](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Bu proje, Kaggle üzerinde bulunan **Pima Indians Diabetes** veri setini kullanarak bir bireyin klinik ölçümlerine göre diyabet hastası olup olmadığını tahmin etmeyi amaçlar. Proje kapsamında kapsamlı bir **Keşifsel Veri Analizi (EDA)** yapılmış, veri ön işleme adımları uygulanmış ve 6 farklı makine öğrenmesi modeli `GridSearchCV` ile optimize edilerek karşılaştırılmıştır.

---

## 📊 Veri Seti Hakkında (Pima Indians Diabetes)

| Sütun Adı | Açıklama |
| :--- | :--- |
| **Pregnancies** | Hamile kalma sayısı |
| **Glucose** | 2 saatlik oral glukoz tolerans testindeki plazma glukoz konsantrasyonu |
| **BloodPressure** | Diyastolik kan basıncı (mm Hg) |
| **SkinThickness** | Triceps cilt kıvrım kalınlığı (mm) |
| **Insulin** | 2 saatlik serum insülini (mu U/ml) |
| **BMI** | Vücut kitle indeksi (kilo / boy^2) |
| **DiabetesPedigree** | Diyabet soy ağacı işlevi (aile geçmişine göre risk puanı) |
| **Age** | Yaş |
| **Outcome** | Sınıf değişkeni (0: Sağlıklı, 1: Diyabet Hastası) |

---

## ⚙️ Uygulanan Metodoloji & İş Akışı

### 1. Keşifsel Veri Analizi (EDA) & Veri Temizleme
* Veri setinde `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin` ve `BMI` değerlerinde sıfır (0) olan mantıksız kayıtlar tespit edilmiştir. Örneğin bir insanın insülin veya BMI değeri 0 olamaz.
* Bu "gizli eksik veriler" (`NaN`), veri sızıntısını (data leakage) önlemek amacıyla eğitim seti medyan değerleri kullanılarak doldurulmuştur.

### 2. Özellik Ölçeklendirme (Feature Scaling)
* Sınıflandırma modellerinin (özellikle KNN ve SVC gibi uzaklık tabanlı algoritmaların) daha stabil çalışması için bağımsız değişkenler `StandardScaler` kullanılarak standartlaştırılmıştır.

### 3. Model Eğitimi & Hiperparametre Optimizasyonu
Aşağıdaki 6 algoritma üzerinde, en iyi parametreleri bulmak adına `GridSearchCV` ve 5-Katlı Çapraz Doğrulama (5-Fold Cross-Validation) uygulanmıştır:
* Logistic Regression
* Support Vector Classifier (SVC)
* K-Nearest Neighbors (KNN)
* Decision Tree
* Random Forest
* AdaBoost

---

## 🛠️ Teknolojiler ve Kütüphaneler
Bu projede Python 3 ve aşağıdaki veri bilimi kütüphaneleri kullanılmıştır:
* **Veri Analizi:** `pandas`, `numpy`
* **Görselleştirme:** `matplotlib`, `seaborn`
* **Makine Öğrenmesi:** `scikit-learn`

---
