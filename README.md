#  Yapay Sinir Ağları ile Banknote Sahteciliği Tespiti  

## Giriş
Bu çalışma, Kaggle'dan alınan "BankNote_Authentication" veri seti kullanılarak sahte banknotları tespit etmek amacıyla geliştirilmiş çok katmanlı algılayıcı (MLP) modellerini içermektedir. Model, hem özel olarak implemente edilmiş bir MLP modeli hem de Scikit-learn ve PyTorch kütüphaneleri kullanılarak eğitilmiş farklı MLP yapıları ile karşılaştırılmıştır. Çalışmanın amacı, farklı aktivasyon fonksiyonları ve model yapılarını kullanarak en iyi doğruluk oranını elde etmektir.

## Metod
### Veri Seti ve Ön İşleme
- Veri seti, dört özellik ve bir sınıf etiketinden oluşmaktadır.
- Veriler normalizasyon için **StandardScaler** ile ölçeklendirilmiştir.
- Eğitim ve test verileri **train_test_split** ile %80 eğitim, %20 test olarak ayrılmıştır.

### Model Yapıları
#### 1. Özel MLP Implementasyonu
- Model, bir ve iki gizli katmanlı (5-5 nöron) yapılarla eğitildi.
- Aktivasyon fonksiyonları olarak **Tanh** ve **ReLU** kullanıldı.
- Optimizasyon algoritması olarak **SGD (Stochastic Gradient Descent)** tercih edildi.
- Kayıp fonksiyonu olarak **Binary Cross Entropy** kullanıldı.

#### 2. Scikit-learn MLP Modeli
- **MLPClassifier** kullanılarak gizli katman sayısı ve aktivasyon fonksiyonları aynı olacak şekilde model eğitildi.

#### 3. PyTorch MLP Modeli
- **PyTorch** kullanılarak MLP modeli oluşturuldu.
- Aynı gizli katman ve aktivasyon fonksiyonları ile eğitildi.
- **SGD** optimizasyon algoritması ve **Binary Cross Entropy Loss** fonksiyonu kullanıldı.

### Değerlendirme Kriterleri
- **Accuracy (Doğruluk)**
- **Confusion Matrix (Karmaşıklık Matrisi)**
- **Precision, Recall ve F1-score** değerleri hesaplandı.

## Sonuçlar
### Özel MLP Modeli Karşılaştırması
| Model | Aktivasyon | Accuracy |
|--------|-------------|-----------|
| 1 Hidden Layer | Tanh | **0.9891** |
| 1 Hidden Layer | ReLU | **0.9891** |
| 2 Hidden Layers | Tanh | **0.9927** |
| 2 Hidden Layers | ReLU | **0.9927** |


### Scikit-learn ve PyTorch Modelleri
**Scikit-learn MLP Modeli:**
- Accuracy: **0.9927**
- Confusion Matrix:
  ```
  [[151   2]
   [  0 122]]
  ```
- F1-score: **0.99**

**PyTorch MLP Modeli:**
- Accuracy: **0.9927**
- Confusion Matrix:
  ```
  [[151   2]
   [  0 122]]
  ```
- F1-score: **0.99**

Her iki model de oldukça yüksek doğruluk oranına ulaşmış ve birbirine yakın sonuçlar vermiştir.

## Tartışma
Sonuçlara göre: 
- **İki farklı framework (Scikit-learn ve PyTorch) ile aynı model yapısının benzer sonuçlar vermesi**, modelin tutarlılığını gösterir. 
- **Tanh aktivasyonu**, küçük veri setlerinde daha istikrarlı sonuçlar vermiştir.  
- **ReLU aktivasyonu**, derin ağlarda daha iyi performans göstermiştir.  
- **İki katmanlı modeller**, tek katmanlı modellere kıyasla genellikle daha iyi performans göstermiştir. 
## Referanslar
1. Banknote Authentication Data Set - Kaggle: https://www.kaggle.com/datasets/ritesaluja/bank-note-authentication-uci-data
2. Scikit-learn MLPClassifier: https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPClassifier.html
3. PyTorch Documentation: https://pytorch.org/docs/stable/index.html

