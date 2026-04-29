# IDX Keterbukaan Informasi

Konversi data **keterbukaan informasi kepemilikan saham** dari [idx.co.id](https://www.idx.co.id) (format PDF) menjadi format JSON yang terstruktur dan mudah digunakan.

---

## 📂 Struktur Direktori

```
idx/
└── 1%/              # Data pemegang saham dengan kepemilikan ≥ 1%
    ├── 270226.json  # Data tanggal 27 Februari 2026
    ├── 310326.json  # Data tanggal 31 Maret 2026
    └── 300426.json  # Data tanggal 30 April 2026
```

Nama file menggunakan format **`DDMMYY.json`** (tanggal-bulan-tahun).

---

## 📄 Format Data JSON

Setiap file JSON memiliki struktur berikut:

```json
{
  "success": true,
  "data": [
    {
      "date": "27-Feb-2026",
      "shareCode": "AADI",
      "issuerName": "ADARO ANDALAN INDONESIA Tbk",
      "investorName": "ADARO STRATEGIC INVESTMENTS",
      "investorType": "CP",
      "localForeign": "L",
      "nationality": "INDONESIA",
      "domicile": "",
      "holdingsScriptless": 3200142830,
      "holdingsScript": 0,
      "totalHoldings": 3200142830,
      "percentage": 41.1
    }
  ]
}
```

### Penjelasan Field

| Field | Tipe | Keterangan |
|---|---|---|
| `date` | string | Tanggal data (DD-Mon-YYYY) |
| `shareCode` | string | Kode saham emiten (ticker) |
| `issuerName` | string | Nama emiten / perusahaan tercatat |
| `investorName` | string | Nama pemegang saham |
| `investorType` | string | Jenis pemegang saham: `CP` (perusahaan) atau `ID` (individu) |
| `localForeign` | string | `L` = Lokal, `F` = Asing |
| `nationality` | string | Kewarganegaraan / negara asal |
| `domicile` | string | Domisili pemegang saham |
| `holdingsScriptless` | number | Jumlah saham scriptless (elektronik) |
| `holdingsScript` | number | Jumlah saham script (fisik) |
| `totalHoldings` | number | Total kepemilikan saham |
| `percentage` | number | Persentase kepemilikan (%) |

---

## 🔗 Sumber Data

Data bersumber dari laporan keterbukaan informasi kepemilikan saham yang dipublikasikan oleh **Bursa Efek Indonesia (BEI / IDX)** di:

> [https://www.idx.co.id/id/data-pasar/laporan-statistik/keterbukaan-informasi](https://www.idx.co.id/id/data-pasar/laporan-statistik/keterbukaan-informasi)

Laporan tersebut diterbitkan secara berkala dalam format PDF dan dikonversi ke JSON untuk memudahkan konsumsi data secara programatik.

---

## 📌 Catatan

- Hanya pemegang saham dengan kepemilikan **≥ 1%** yang tercantum dalam laporan ini (sesuai ketentuan BEI).
- Data bersifat historis sesuai tanggal file masing-masing.
- Seluruh data merupakan milik BEI dan digunakan untuk keperluan informasi publik.
