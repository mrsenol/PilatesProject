# Reformer Pilates Scheduling Benchmark — Dataset v1

Bu set, Reformer Pilates stüdyosu için **talep kabulü, grup eşleştirme ve eğitmen/makine kapasite planlaması** çalışmasındaki sentetik benchmark örneklerinin kanonik CSV sürümüdür. Bireysel müşteri talepleri, grup müşterileri, aday ikililer, eğitmen yetkinlikleri ve haftalık gün desenlerini içerir.

## Kapsam

- 3 kaynak çalışma kitabı: genişletilmiş, ekstra büyük ve faktör-ayrıştırılmış benchmark aileleri
- Birim gözlem: `instance_id` ile tanımlanan, deterministik tohumlu sentetik stüdyo senaryosu
- Ham girişler: çalışma sayfası biçimindeki Excel dosyaları; kaynak konumu üretim betiğinde tanımlıdır
- Kanonik çıktı: `canonical/` altındaki UTF-8 CSV dosyaları

## Yeniden üretim

```bash
python3 data/reformer_pilates_dataset_v1/build_dataset.py
```

Varsayılan kaynak dizini yerel araştırma projesidir. Farklı konum için:

```bash
python3 data/reformer_pilates_dataset_v1/build_dataset.py --source-dir /mutlak/kaynak/dizini
```

`sources.csv`, her girdi dosyasının SHA-256 özetini içerir. Böylece veri sürümü ile deney kaynağı ayrıştırılabilir.

## Kullanım ve sınırlar

Bu veri **gerçek üye kaydı değildir**; sentetik benchmark verisidir. Müşteri tanımlayıcıları (`C*`, `G*`) örnek-içi teknik kimliklerdir. Sonuç dosyaları veya çözücü koşuları bu veri setine dahil edilmemiştir; böylece giriş verisi ile yöntem performansı birbirine karışmaz.

Alan tanımları için [DATA_DICTIONARY.md](DATA_DICTIONARY.md) dosyasına bakın.
