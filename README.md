#  Yapay Sinir Ağları ile Banknote Sahteciliği Tespiti  

## 1. Giriş  
Bu proje, banknotların sahte olup olmadığını belirlemek için farklı Çok Katmanlı Algılayıcı (MLP) modellerinin karşılaştırmasını içermektedir.

## 2. Yöntem  
Çalışmada **BankNote Authentication** veri seti kullanılmıştır. Veriler eğitim ve test kümelerine ayrılmış ve özellikler standartlaştırılmıştır.  

**Modeller:**  
- **1 Gizli Katmanlı :** Tanh ve ReLU aktivasyon fonksiyonları ile
- **2 Gizli Katmanlı:** Tanh ve ReLU aktivasyon fonksiyonları ile 
 

**Hiperparametreler:**  
- Öğrenme oranı: `0.1`  
- Aktivasyon fonksiyonları: `Tanh`, `ReLU`  
- Katman sayısı: `2 ve 3`  
- Eğitim süresi: `400 epoch`  

**Değerlendirme Metrikleri:**  
- Doğruluk (Accuracy)  
- Sınıflandırma Raporu (Precision, Recall, F1-score)  

## 3. Sonuçlar  
Aşağıda farklı modellerin doğruluk (accuracy) değerleri verilmiştir:  

| Model | 1 Katman (Tanh) | 2 Katman (Tanh) | 1 Katman (ReLU) | 2 Katman (ReLU) |  
|--------|---------------|---------------|---------------|---------------|  
|  MLP | **%0.9891** | **%0.9927** | **%0.9891** | **%0.9927** |  
 

## 4. Tartışma  
Sonuçlara göre:  
- **Tanh aktivasyonu**, küçük veri setlerinde daha istikrarlı sonuçlar vermiştir.  
- **ReLU aktivasyonu**, derin ağlarda daha iyi performans göstermiştir.  
- **İki katmanlı modeller**, tek katmanlı modellere kıyasla genellikle daha iyi performans göstermiştir.  


## 5. Referanslar  
- [Banknote Authentication Dataset](https://archive.ics.uci.edu/ml/datasets/banknote+authentication)  
- Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning.  
- Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning.  
