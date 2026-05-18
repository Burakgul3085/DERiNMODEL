
# DAGM 2007 Model Özetleri

## Kullanılan Modeller

Bu projede DAGM 2007 veri seti üzerinde dört farklı model yaklaşımı denenmiştir:

| Model | Yöntem | Threshold | Accuracy | Kusurlu Precision | Kusurlu Recall | Kusurlu F1 |
|---|---|---:|---:|---:|---:|---:|
| Kendi CNN Model 1 | Regularized CNN | 0.50 | 0.8661 | 0.4718 | 0.1476 | 0.2248 |
| Kendi CNN Model 2 | Balanced Batch CNN | 0.50 | 0.8843 | 0.8985 | 0.1366 | 0.2371 |
| Kendi CNN Model 3 | Focal Loss CNN | 0.40 | 0.4939 | 0.1670 | 0.7137 | 0.2707 |
| EfficientNetB0 | Transfer Learning | 0.60 | 0.8986 | 0.6221 | 0.5837 | 0.6023 |

## Final Model

Final model olarak **EfficientNetB0 Transfer Learning** modeli seçilmiştir.

Bu modelin seçilme nedeni, kusurlu sınıf için precision ve recall değerlerini en dengeli şekilde sağlamasıdır.

## EfficientNetB0 Final Sonuçları

- Accuracy: 0.8986
- Kusurlu Precision: 0.6221
- Kusurlu Recall: 0.5837
- Kusurlu F1-score: 0.6023
- Threshold: 0.60

## Confusion Matrix

| Gerçek / Tahmin | Kusursuz | Kusurlu |
|---|---:|---:|
| Kusursuz | 2835 | 161 |
| Kusurlu | 189 | 265 |

## Genel Değerlendirme

Kendi CNN modelleri sınıf dengesizliği nedeniyle kusurlu sınıfı yakalamakta zorlanmıştır.
Focal Loss modeli recall değerini artırmış ancak yanlış alarm sayısını yükseltmiştir.

EfficientNetB0 modeli, ImageNet üzerinde önceden eğitilmiş özellik çıkarıcı yapısı sayesinde daha dengeli ve güçlü sonuç vermiştir.
Bu nedenle final model olarak seçilmiştir.
