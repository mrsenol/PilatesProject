# Reformer Pilates Scheduling — Solution Archive v1

Bu klasör, dataset klasöründen ayrıdır ve **yalnızca çözücü çıktıları** içerir. Her çalışma kitabının değişmez bir kopyası `workbooks/` altında saklanır; `solution_runs_long.csv` ise karşılaştırmalı analiz için satır bazında birleştirilmiş sonuç tablosudur.

## Dahil edilen nihai deney çözümleri

1. **Genişletilmiş benchmark, 60 s:** 90 örnek için CP-Interval ve MIP ayrıntılı çözümleri.
2. **Faktör-ayrıştırılmış benchmark, 60 s:** 135 örnek için CP ve MIP sonuçları.
3. **Zaman limiti deneyi — genişletilmiş:** 90 örnek, CP ve MIP, 60/300/600 saniye.
4. **Zaman limiti deneyi — ekstra büyük:** 30 örnek, CP ve MIP, 60/300/600 saniye.
5. **Tekrarlı CP koşuları:** genişletilmiş örneklerde 300/600 s; ekstra büyük örneklerde 60/300/600 s; her kombinasyonda 5 tekrar.

Toplamda 7 çalışma kitabı ve 2.520 koşu/özet satırı vardır. Aynı senaryo farklı model, zaman limiti ya da tekrar ayarıyla birden fazla satırda görünebilir; bunlar yinelenen kayıt değil, ayrı deney koşularıdır.

## Dışarıda bırakılanlar

Smoke-test dosyaları, dar kapsamlı hata ayıklama/inspection dosyaları, eski/ara benchmark çıktıları ve yalnızca tablo/figür üretmek için oluşturulmuş türev özetler bu arşive alınmadı. Böylece analiz seti nihai deney koşularıyla sınırlı kaldı.

## Yeniden üretim

```bash
python3 data/reformer_pilates_solutions_v1/build_solution_archive.py
```

`solution_catalog.csv` kaynak dosya, sayfa, kapsam, satır sayısı ve SHA-256 bütünlük özetini içerir.
