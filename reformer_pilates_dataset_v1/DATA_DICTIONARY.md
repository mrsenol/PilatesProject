# Veri sözlüğü

Her tablo `instance_id` üzerinden birleştirilir. Kaynak Excel'deki parasal `revenue` alanı kaynakta hangi birimle tanımlandıysa o şekilde korunur; para birimi veya dönem ölçeği bu sürümde varsayılmamıştır.

## `instances.csv`

- `instance_id`: benzersiz sentetik senaryo kimliği.
- `source_book`: köken çalışma kitabı.
- `seed`: örnek üretimindeki deterministik rastgele tohum.
- `machines`: kullanılabilir Reformer makine sayısı.
- `max_slots_per_instructor_per_day`: eğitmen başına günlük en fazla ders slotu.
- `family`: örnek boyutu ailesi (`small`, `medium`, `large`, `extra`).

## `instructors.csv`

- `instructor_id`: örnek-içi eğitmen kimliği.
- `level`: eğitmen beceri seviyesi.
- `qualified_types`: virgülle ayrılmış hizmet/müşteri tipi uygunluk listesi.

## `requests.csv`

- `request_kind`: `individual` veya `group`.
- `request_id`: örnek-içi müşteri/talep kimliği.
- `customer_type`: talep edilen hizmet veya seviye türü.
- `package_size`: haftalık ziyaret/ders sayısı.
- `zone`: tercih edilen zaman bölgesi (`morning`, `midday`, `evening`).
- `revenue`: kabul edilmesi durumunda modelde kullanılan gelir değeri.
- `is_group_eligible`: 1 ise grup eşleştirmesine uygun, 0 ise değil.

## `candidate_pairs.csv`

- `pair_id`: aday grup çifti kimliği.
- `g1`, `g2`: eşleştirilebilecek iki grup müşteri kimliği.
- `customer_type`, `package_size`, `zone`, `revenue`: çift için geçerli ortak özellikler/değer.

## `day_patterns.csv`

- `pattern_id`: haftalık ziyaret deseni kimliği.
- `package_size`: desenin kapsadığı haftalık ders sayısı.
- `days`: virgülle ayrılmış ders günleri.

## `sources.csv`

- `source_book`: girdi Excel çalışma kitabı.
- `sha256`: tam dosya bütünlük özeti.
