# Stat - Rangkuman RW Banjir

Perhitungan semua RW terdampak banjir berdasarkan status tinggi banjir.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| admin | Area mana yang laporannya ingin disajikan? \(saat ini hanya mendukung`ID-JK`\) | String | Tidak |

## GET /stats/floodedRWsSummary

```text
curl "https://data.petabencana.id/stats/floodedRWsSummary?city=jbd"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "# hati-hati RWs": 0,
  "# 10-70cm RWs": 9,
  "# 71-150cm RWs": 0,
  "# 151cm+ RWs": 0
}
```

