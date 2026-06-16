# Türkiye Akaryakıt Fiyat Analizi (Power BI)

2019-2024 arası Türkiye akaryakıt satış verisini analiz ettiğim 2 sayfalık Power BI dashboard'u. İl bazında harita, yıllık fiyat trendi, ürün ve şirket dağılımı içeriyor.

## İçerik

**Sayfa 1:**
- Toplam Hasılat KPI ($2.4M)
- Şirketlere göre gelir dağılımı (pasta)
- Yıllara göre toplam ciro (sütun, 2019→2024 trendi)
- En çok ciro yapan 10 şehir (yatay bar)
- En çok ciro yapan 5 şirket (yatay bar)
- Çeyrek bazında dağılım (pasta)

**Sayfa 2:**
- 4 KPI: Ortalama Fiyat, İşlem Sayısı, Min/Max/Medyan
- Yıllık ortalama, min, max fiyat trendi (çizgi)
- Türkiye haritası — il bazında ortalama ciro
- Kategoriye göre ortalama ciro (pasta — Benzin, Dizel, LPG, Katkı)

## Veri Seti

Sentetik veri (2.500 satış kaydı, 2019-2024):
- 20 il (enlem/boylam dahil)
- 6 yakıt türü (Benzin 95/97, Motorin, LPG, Adblue)
- 10 dağıtım şirketi (Opet, Shell, BP, Total, Lukoil...)
- Gerçekçi enflasyon modeli (2019 → 2024 ~9.5x artış)

## Kullandığım Şeyler

- Power BI Desktop
- DAX (SUM, AVERAGE, CALCULATE, DISTINCTCOUNT)
- Power Query (veri tipi düzeltme, ilişkiler)
- Türkiye haritası (enlem/boylam ile)
- PowerPoint (kırmızı temalı arka plan)

## Yazdığım DAX Ölçüleri

```dax
Toplam Hasılat   = SUM(Satışlar[Tutar])
Ortalama Fiyat   = AVERAGE(Satışlar[BirimFiyat])
İşlem Sayısı     = COUNTROWS(Satışlar)
Minimum Fiyat    = MIN(Satışlar[BirimFiyat])
Maksimum Fiyat   = MAX(Satışlar[BirimFiyat])
```

## Tasarım Notları

- Kırmızı + beyaz palet (akaryakıt sektörüne uygun)
- 6 sayfa veri modeli (Satışlar + İller + Ürünler + Şirketler + Takvim)
- Tablolar arası ilişkiler kuruldu
- Harita için il enlem/boylam verisi entegre

## Dosyalar

```
├── README.md
├── Turkiye_Akaryakit_Dashboard.pbix
├── images/
│   ├── sayfa1.png
│   └── sayfa2.png
└── data/
    └── Akaryakit_Dashboard_Veri.xlsx
```

---

**Abdülrahim Etyemez**  
[LinkedIn](https://www.linkedin.com/in/abdulrahim-etyemez/)
