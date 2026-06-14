# 🧠 NLP Healthcare Solutions

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-0.24%2B-orange?logo=scikit-learn)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green)
![OpenAI API](https://img.shields.io/badge/OpenAI-GPT_3.5-black?logo=openai)

Bu depo, sağlık ve klinik verileri üzerinde Doğal Dil İşleme (NLP) tekniklerini ve Büyük Dil Modellerini (LLM) harmanlayarak geliştirilmiş iki temel modülü içermektedir.

## 📁 Proje İçeriği

### 1. Klinik Metin Sınıflandırma Modeli
Tıbbi transkripsiyon raporlarını (`mtsamples.csv`) analiz ederek, hastanın durumunun hangi tıbbi uzmanlık alanına (medical specialty) girdiğini tahmin eden bir makine öğrenmesi modelidir.

* **Metin Ön İşleme (Preprocessing):** `NLTK` kütüphanesi kullanılarak metinler noktalama işaretlerinden ve rakamlardan arındırılır, tokenizasyon işlemi yapılır ve kelimeler köklerine (Lemmatization) indirgenir. Bağlamı yakalamak adına metinlerin ilk ve son cümlelerine odaklanılır.
* **Vektörizasyon:** Metin verilerinin matematiksel temsili için **TF-IDF** (Term Frequency-Inverse Document Frequency) yöntemi uygulanmıştır.
* **Görselleştirme ve Boyut İndirgeme:** Karmaşık metin verilerinin uzaydaki dağılımını gözlemleyebilmek için **t-SNE** ve **PCA** (Temel Bileşen Analizi) kullanılarak veriler 2 boyuta indirgenmiş ve `seaborn` ile görselleştirilmiştir.
* **Makine Öğrenmesi (Model):** Boyutları küçültülmüş TF-IDF vektörleri üzerinde **Lojistik Regresyon** modeli eğitilmiştir. Karmaşıklık matrisi (Confusion Matrix) ısı haritası ile çizdirilerek modelin doğruluk performansı ölçülür.
* **Kayıt:** Eğitilen nihai model, tekrar kullanım için `NLP.pkl` olarak dışa aktarılır.

### 2. Yapay Zeka Destekli Hasta Şikayet Asistanı
Hastaların şikayetlerini dinleyen, analiz eden ve onlarla akıcı bir şekilde etkileşime giren CLI (Komut Satırı) tabanlı bir sohbet asistanıdır.

* **Altyapı:** Doğal dil üretimi için güçlü **OpenAI API (`gpt-3.5-turbo`)** modeli entegre edilmiştir.
* **Bağlamsal Hafıza:** Kullanıcının (hastanın) önceki mesajlarını bir dizi geçmiş (history) listesinde tutarak diyaloğun kopmamasını ve uygulamanın mantıklı, ardışık cevaplar verebilmesini sağlar.

## 💻 Kullanılan Teknolojiler

* **Veri Bilimi & ML:** `pandas`, `numpy`, `scikit-learn`
* **Doğal Dil İşleme (NLP):** `nltk`, `re` (RegEx)
* **Veri Görselleştirme:** `matplotlib`, `seaborn`
* **Generative AI:** `openai`

## 🚀 Kurulum ve Çalıştırma

Projeyi yerel bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

**1. Gerekli Python kütüphanelerini yükleyin:**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn nltk openai
