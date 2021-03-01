# Stats - Rangkuman Wilayah

Daftar seluruh wilayah administrasi yang RWnya saat ini terdampak banjir.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| admin | Area mana yang laporannya ingin disajikan? \(saat ini hanya mendukung`ID-JK`\) | String | Tidak |

## GET /stats/floodedRegionsSummary

```text
curl "https://data.petabencana.id/stats/floodedRegionsSummary?admin=ID-JK"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "total number of regions with flooded RWs": 4,
  "regions with flooded RWs": [
    "KAPUK",
    "RAWA TERATE",
    "CIPINANG MELAYU",
    "CENGKARENG BARAT"
  ]
}
```

