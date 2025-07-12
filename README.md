# 💬 Makine Öğrenmesi Yöntemleri ile Siber Zorbalık Tespiti

## 📌 Tanıtım

Bu proje, Türkçe sosyal medya içeriklerinde yer alan siber zorbalık ifadelerini otomatik olarak tespit etmeyi amaçlamaktadır.  
Sosyal medya platformlarında kullanıcılar arası olumsuz etkileşimler, özellikle genç bireylerde psikolojik sorunlara yol açabildiğinden
siber zorbalığın tespiti ve önlenmesi büyük önem taşımaktadır. Bu nedenle doğal dil işleme ve makine öğrenmesi teknikleri kullanılarak siber 
zorbalık içeren içeriklerin doğrulukla sınıflandırılması hedeflenmiştir.

---

## 🧰 Kullanılan Teknolojiler

- Python  
- Scikit-learn  
- Pandas, NumPy  
- NLTK  
- Matplotlib, Seaborn  

---

## 📂 Veri Seti

- **Kaynak:** [Türkçe Sosyal Medya Paylaşımı Veri Seti – Kaggle](https://www.kaggle.com/datasets/mrtbeyz/trke-sosyal-medya-paylam-veri-seti)  
- **Sınıflar:** Pozitif (%55), Negatif (%45)

---

## 🧪 Veri Ön İşleme

Veri kalitesini artırmak için şu işlemler uygulanmıştır:

- Küçük harfe dönüştürme  
- Noktalama, URL ve kullanıcı adı temizliği  
- Türkçe stop-word temizliği  
- Lemmatizasyon 
- TF-IDF vektörleştirme 
- Tematik manuel etiketleme (negatif içerikler için)

Ek olarak, metinlere ilişkin yapısal özellikler çıkarılmıştır:

- Cümle uzunluğu  
- Kelime çeşitliliği (TTR)  
- Büyük harf oranı  
- Negatif kelime sıklığı  

---

## 🧠 Modelleme Süreci

Aşağıdaki algoritmalar eğitilmiş ve karşılaştırılmıştır:

| Model                  | F1 Skoru     |
|------------------------|--------------|
| Logistic Regression    | **0.8724 ✅** |
| Support Vector Machine | 0.8697       |
| Random Forest          | 0.8442       |

> ✔️ Logistic Regression, en yüksek başarıyı göstermiştir.

---

## 📈 Performans Değerlendirmesi

**Test Seti Başarı Özeti:**

| Metrik               | Değer |
|----------------------|--------|
| Doğruluk (Accuracy)  | 0.84   |
| Macro Avg F1         | 0.84   |
| Weighted Avg F1      | 0.84   |
| Pozitif F1 Skoru     | 0.87   |
| Negatif F1 Skoru     | 0.81   |

- **Friedman testi sonucu:** `p = 0.0150`  
  → Modeller arasında istatistiksel olarak anlamlı fark vardır.

---

## 🧠 Tematik Analiz (LDA)

Negatif içerikler, **Latent Dirichlet Allocation (LDA)** ile temalara ayrılmıştır.  
En sık görülen temalar:

- Bireysel Hakaret ve Zorbalık  
- Kadına Şiddet ve Cinsiyetçilik  
- Dini ve Milli Değerlere Saldırı  

> Bu sonuç zorbalığın tematik olarak da tahmin edilebilir olduğunu göstermektedir.

---

## 🔬 Ek Bulgular

| Özellik                  | Bulgular                                                   |
|--------------------------|-------------------------------------------------------------|
| Cümle Uzunluğu           | Negatif içerikler daha kısa (∅ ≈ 9.5 kelime)                |
| TTR (Kelime çeşitliliği) | Negatifler daha yüksek TTR değeri göstermektedir            |
| Dilsel Kalıplaşma        | Negatif içerikler daha tekrarlı ve saldırgan bir yapıdadır |

---

## 🖼️ Görsel Sonuçlar

<details>
<summary>📊 Boxplot: Cümle Uzunluğu (Pozitif vs Negatif)</summary>

Negatif içeriklerin daha kısa ve direkt olduğu gözlemlenmiştir.

</details>

<details>
<summary>📊 Tematik Dağılım: Zorbalık Türleri</summary>

Bireysel hakaret ve toplumsal değerlere saldırı en yaygın kategorilerdir.

</details>

---

## ✅ Sonuç

Bu proje, sosyal medya platformlarındaki Türkçe içerikler üzerinde  
**siber zorbalık davranışlarını başarılı şekilde sınıflandırabilen** bir makine öğrenmesi modeli geliştirmiştir.  
**Logistic Regression**, hem eğitim hem test verisinde yüksek performans sergilemiş; içeriklerin tematik ve dilsel özellikleri analiz edilerek modele katkı sağlanmıştır.
