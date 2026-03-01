# 📊 Zaman Serisi Analizi ve Tahminleme Projesi

Bu repo, finansal, çevresel ve operasyonel veriler üzerinde ekonometrik zaman serisi analizleri ve tahminleme yöntemlerini kapsamlı bir şekilde incelemektedir. Çalışmada **Google Hisse Fiyatları**, **Avrupa Borsa Endeksleri (EuStockMarkets)**, **Hava Yolu Yolcu Sayısı (AirPassengers)** ve **Sıcaklık Verileri (Nottem)** analiz edilmiştir.

## 📈 Proje Kapsamı ve Veri Setleri

Projede kullanılan veri setleri ve uygulanan teknikler şunlardır:

### 1. Finansal Veri Analizi (Google Hisse Senedi Fiyatları)
- **Amaç:** Google'ın (GOOGL) günlük kapanış fiyatlarına dayalı olarak piyasa hareketlerinin indekslenmesi ve görselleştirilmesi.
- **Kullanılan Yöntemler:** Sabit Esaslı Endeks, Zincirleme (Bileşik) Esaslı Endeks hesaplamaları.
- **Veri Kaynağı:** `quantmod` paketi aracılığıyla Yahoo Finance.

### 2. Avrupa Borsaları Analizi (EuStockMarkets)
- **Amaç:** Farklı Avrupa borsa endekslerinin (DAX, SMI, CAC, FTSE) aynı baz seviyesine çekilerek karşılaştırmalı analizi.
- **Kullanılan Yöntemler:** Normalizasyon, Karşılaştırmalı Zaman Serisi Grafikleri.
- **Veri Kaynağı:** R `datasets` paketi.

### 3. Operasyonel Veri Analizi (AirPassengers)
- **Amaç:** Uluslararası havayolu yolcu sayılarındaki trend ve mevsimsel etkilerin analizi ve ARIMA/ARMA modelleri ile tahminleme.
- **Kullanılan Yöntemler:** Çarpımsal Ayrıştırma (Multiplicative Decomposition), Durağanlaştırma (Fark alma, Log dönüşümü), ARIMA/ARMA Modellemesi.
- **Veri Kaynağı:** R `datasets` paketi.

### 4. Çevresel Veri Analizi (Nottem)
- **Amaç:** Nottingham Kalesi'ndeki ortalama aylık sıcaklıkların uzun vadeli analizi.
- **Kullanılan Yöntemler:** Toplamsal Ayrıştırma (Additive Decomposition), STL Ayrıştırma.
- **Veri Kaynağı:** R `datasets` paketi.

---

## 🚀 Öne Çıkan Bulgular (Key Outputs)

* **Google:** Hisse senedinin baz tarihine göre %100'ün üzerinde değer kazandığı, ancak zincirleme endeks ile günlük volatilite düzeyinin yüksek olduğu tespit edilmiştir.
* **EuStockMarkets:** Endekslerin birbirleriyle yüksek korelasyon içinde hareket ettiği, ancak düşüş ve yükseliş zamanlarında farklılaşabildikleri gözlemlenmiştir.
* **AirPassengers:** ARIMA(2,1,1)(0,1,0)[12] modeli ile yapılan tahminlerde, yolcu sayısının artmaya devam edeceği ancak belirsizlik aralığının (confidence interval) uzun vadede genişlediği gözlemlenmiştir.
* **Nottem:** Sıcaklık verisinde belirgin bir yıllık mevsimsellik (sezonsallık) gözlemlenmiş olup, uzun vadeli bir trend belirlenememiştir.
  

## 🖼️ Analiz Görselleri ve Yorumları

Proje kapsamında gerçekleştirilen analizlerin detayları aşağıda sunulmuştur. Bu görseller, verilerin teknik özelliklerini ve modellerin performansını yansıtmaktadır.

### 1. Google Hisse Senedi Endeks Karşılaştırması
`outputs/google_index_analysis.png`
* **Açıklama:** Google kapanış fiyatlarının Sabit Esaslı ve Zincirleme (Bileşik) Esaslı Endeks yöntemleriyle karşılaştırılması.
* **Yorum:** Hisse senedinin baz tarihine göre %100'ün üzerinde değer kazandığı, ancak zincirleme endeks ile günlük volatilite düzeyinin yüksek olduğu gözlemlenmiştir.

### 2. Avrupa Borsa Endeksleri Normalizasyon Analizi
`outputs/eustock_comparative.png`
* **Açıklama:** DAX, SMI, CAC ve FTSE endekslerinin 100 baz seviyesine çekilerek (normalizasyon) karşılaştırılması.
* **Yorum:** Endekslerin birbirleriyle yüksek korelasyon içinde hareket ettiği, ancak düşüş ve yükseliş zamanlarında farklılaşabildikleri tespit edilmiştir.

### 3. AirPassengers Çarpımsal Ayrıştırma (Decomposition)
`outputs/airpassengers_decomposition.png`
* **Açıklama:** Hava yolu yolcu sayısı verisinin Trend, Mevsimsellik ve Hata bileşenlerine ayrıştırılması.
* **Yorum:** Veride belirgin bir yukarı yönlü trend ve her yıl tekrarlanan çarpımsal mevsimsel döngüler (yaz aylarında artış) net bir şekilde görülmektedir.

### 4. Nottem Verisi STL Ayrıştırma Grafiği
`outputs/nottem_stl_analysis.png`
* **Açıklama:** Sıcaklık verilerinin LOESS (STL) yöntemi ile bileşenlerine ayrılması.
* **Yorum:** Sıcaklık verisinde belirgin bir yıllık mevsimsellik gözlemlenmiş olup, uzun vadeli belirgin bir trend belirlenememiştir.

### 5. AirPassengers ARIMA Tahmin Modeli
`outputs/airpassengers_forecast.png`
* **Açıklama:** ARIMA(2,1,1)(0,1,0)[12] modeli ile gelecek 24 ay için yapılan tahminler ve %95 güven aralığı.
* **Yorum:** Yolcu sayısının artmaya devam edeceği öngörülmekle birlikte, belirsizlik aralığının (mavi gölge) uzun vadede genişlediği gözlemlenmiştir.


---

## 🛠 Teknik Altyapı
- **Dil:** R
- **Temel Kütüphaneler:** `quantmod`, `forecast`, `tseries`, `ggplot2`, `fpp2`, `TTR`

## 📂 Proje Yapısı
- `/data`: Kullanılan veri setleri (CSV formatında).
- `/notebooks`: R analiz kodları.
- `/outputs`: Analizler sonucu üretilen grafikler (PNG).
- `/report`: Projenin detaylı PDF raporu.
- `README.md`: Proje dokümantasyonu.
