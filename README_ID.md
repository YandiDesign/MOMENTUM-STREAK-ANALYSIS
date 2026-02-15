 #  ANALISIS MOMENTUM STREAK

## Analisis Statistik Lengkap Pola Momentum Candle

---

##  RINGKASAN EKSEKUTIF

Analisis ini meneliti **pola momentum streak** di 10 instrumen trading selama periode 20 tahun (2005-2025). Studi ini mengungkapkan insight yang sangat kuat untuk trader:

**Temuan Utama:**
> **73,43% dari semua candle adalah bagian dari momentum streak**, sementara hanya **26,57% adalah candle reversal terisolasi**.

Ini berarti trading dengan momentum memberikan Anda **probabilitas 3x lebih tinggi** untuk berada di sisi yang benar pasar.

---

##  DATA HISTORIS

### Total Data yang Dianalisis

| No | Pair | Periode | Total Candle | Timeframe |
|----|------|---------|--------------|-----------|
| 1 | AUDUSD | 2005.01.01 - 2025.12.31 | 5.793 | Daily |
| 2 | EURUSD | 2005.01.03 - 2025.12.31 | 5.451 | Daily |
| 3 | GBPUSD | 2005.01.03 - 2025.12.31 | 5.449 | Daily |
| 4 | NZDUSD | 2005.01.03 - 2025.12.31 | 5.449 | Daily |
| 5 | USDCAD | 2005.01.03 - 2025.12.31 | 5.448 | Daily |
| 6 | USDCHF | 2005.01.03 - 2025.12.31 | 5.449 | Daily |
| 7 | USDJPY | 2005.01.03 - 2025.12.31 | 5.449 | Daily |
| 8 | XAGUSD | 2005.01.03 - 2025.12.31 | 5.435 | Daily |
| 9 | XAUUSD | 2005.01.03 - 2025.12.31 | 5.431 | Daily |
| 10 | XTIUSD | 2010.05.02 - 2025.12.31 | 4.197 | Daily |

### **TOTAL: 53.551 candle daily yang dianalisis**

### Kategori Instrumen
- **Major Forex Pairs (7):** EURUSD, GBPUSD, USDJPY, USDCHF, USDCAD, AUDUSD, NZDUSD
- **Precious Metals (2):** XAUUSD (Emas), XAGUSD (Perak)
- **Energy (1):** XTIUSD (Minyak Mentah WTI)

---

##  METODOLOGI

### 1. Klasifikasi Arah Candle

Setiap candle diklasifikasikan berdasarkan hubungan antara harga **Open** dan **Close**:

```
BULLISH : Close > Open (harga naik)
BEARISH : Close < Open (harga turun)
DOJI    : Close = Open (tidak ada perubahan)
```

### 2. Klasifikasi Doji

Ketika **Doji** terjadi (Close = Open), klasifikasi didasarkan pada panjang wick:

| Kondisi | Klasifikasi | Alasan |
|---------|-------------|--------|
| Upper Wick > Lower Wick | BEARISH | Rejection atas menunjukkan tekanan jual |
| Lower Wick > Upper Wick | BULLISH | Rejection bawah menunjukkan tekanan beli |
| Upper Wick = Lower Wick | Ikut candle sebelumnya | Indecision sejati |

```
Dimana:
- Upper Wick = High - Close
- Lower Wick = Close - Low
```

### 3. Definisi Momentum Streak

**Momentum Streak** didefinisikan sebagai **2 atau lebih candle berturut-turut dalam arah yang sama**.

```
Contoh momentum streak bullish 5 candle:

[BULL] [BULL] [BULL] [BULL] [BULL]
  ↑      ↑      ↑      ↑      ↑
  └──────┴──────┴──────┴──────┘
         Semua 5 candle adalah bagian dari momentum streak
```

### 4. Definisi Candle Reversal

**Candle Reversal** adalah **candle terisolasi** yang:
- Berubah arah dari candle sebelumnya
- TIDAK berlanjut (candle berikutnya berbalik lagi)

```
Contoh reversal terisolasi:

[BULL] [BULL] [BEAR] [BULL] [BULL]
               ↑
        Candle bearish ini TERISOLASI
        Ia berbalik tapi tidak berlanjut
        = CANDLE REVERSAL (terjebak/noise)
```

### 5. Metode Perhitungan

```python
# Hitung semua candle dalam streak 2+ candle searah
streak_candles = count_candles_in_streaks(min_length=2)

# Hitung candle terisolasi (bukan bagian dari streak)
reversal_candles = total_candles - streak_candles

# Hitung persentase
streak_percentage = streak_candles / total_candles × 100
reversal_percentage = reversal_candles / total_candles × 100
```

### 6. Contoh Perhitungan

```
Urutan: [B] [B] [B] [B] [B] [Bear] [B] [B]

Analisis:
├── Candle 1-5: Bullish streak (5 candle) ✓ MOMENTUM
├── Candle 6: Bearish, terisolasi (berikutnya bullish) ✗ REVERSAL  
└── Candle 7-8: Bullish streak (2 candle) ✓ MOMENTUM

Hasil:
├── Candle Momentum Streak: 7 (87,5%)
└── Candle Reversal: 1 (12,5%)
```

---

##  HASIL KESELURUHAN

### Ringkasan Semua Pair (2005-2025)

| Rank | Pair | Total Candle | Dalam Streak | Reversal | Streak % |
|------|------|--------------|--------------|----------|----------|
|  1 | GBPUSD | 5.449 | 4.139 | 1.310 | **75,96%** |
|  2 | NZDUSD | 5.449 | 4.039 | 1.410 | **74,12%** |
|  3 | USDCAD | 5.448 | 4.027 | 1.421 | **73,92%** |
| 4 | EURUSD | 5.451 | 4.013 | 1.438 | **73,62%** |
| 5 | USDCHF | 5.449 | 3.996 | 1.453 | **73,33%** |
| 6 | AUDUSD | 5.793 | 4.247 | 1.546 | **73,31%** |
| 7 | USDJPY | 5.449 | 3.991 | 1.458 | **73,24%** |
| 8 | XTIUSD | 4.197 | 3.046 | 1.151 | **72,58%** |
| 9 | XAGUSD | 5.435 | 3.923 | 1.512 | **72,18%** |
| 10 | XAUUSD | 5.431 | 3.899 | 1.532 | **71,79%** |
| | **TOTAL** | **53.551** | **39.320** | **14.231** | **73,43%** |

### Representasi Visual

```
CANDLE DALAM MOMENTUM STREAK: 73,43%
████████████████████████████████████████████████████████████████████████▓░░░░░░░░

CANDLE REVERSAL TERISOLASI: 26,57%
██████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
```

### Ranking berdasarkan Momentum Streak %

```
 1. GBPUSD   75,96% ████████████████████████████████████████████████████████████████████████████
 2. NZDUSD   74,12% ██████████████████████████████████████████████████████████████████████████
 3. USDCAD   73,92% █████████████████████████████████████████████████████████████████████████
 4. EURUSD   73,62% █████████████████████████████████████████████████████████████████████████
 5. USDCHF   73,33% ████████████████████████████████████████████████████████████████████████
 6. AUDUSD   73,31% ████████████████████████████████████████████████████████████████████████
 7. USDJPY   73,24% ████████████████████████████████████████████████████████████████████████
 8. XTIUSD   72,58% ███████████████████████████████████████████████████████████████████████
 9. XAGUSD   72,18% ██████████████████████████████████████████████████████████████████████
10. XAUUSD   71,79% ██████████████████████████████████████████████████████████████████████
```

---

##  ANALISIS PER KATEGORI

### Major Forex Pairs

| Pair | Dalam Streak | Reversal | Streak % | Karakteristik |
|------|--------------|----------|----------|---------------|
| GBPUSD | 4.139 | 1.310 | **75,96%** | Paling trending |
| NZDUSD | 4.039 | 1.410 | **74,12%** | Momentum kuat |
| USDCAD | 4.027 | 1.421 | **73,92%** | Momentum kuat |
| EURUSD | 4.013 | 1.438 | **73,62%** | Konsisten |
| USDCHF | 3.996 | 1.453 | **73,33%** | Konsisten |
| AUDUSD | 4.247 | 1.546 | **73,31%** | Konsisten |
| USDJPY | 3.991 | 1.458 | **73,24%** | Konsisten |
| **RATA-RATA** | | | **73,93%** | |

### Precious Metals

| Pair | Dalam Streak | Reversal | Streak % | Karakteristik |
|------|--------------|----------|----------|---------------|
| XAGUSD | 3.923 | 1.512 | **72,18%** | Sedikit lebih choppy |
| XAUUSD | 3.899 | 1.532 | **71,79%** | Paling prone reversal |
| **RATA-RATA** | | | **71,99%** | |

### Energy

| Pair | Dalam Streak | Reversal | Streak % | Karakteristik |
|------|--------------|----------|----------|---------------|
| XTIUSD | 3.046 | 1.151 | **72,58%** | Momentum sedang |

---

##  ANALISIS TAHUNAN

### AUDUSD (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 313 | 222 | 91 | 70,93% |
| 2006 | 296 | 227 | 69 | **76,69%** |
| 2007 | 259 | 183 | 76 | 70,66% |
| 2008 | 260 | 193 | 67 | 74,23% |
| 2009 | 259 | 191 | 68 | 73,75% |
| 2010 | 265 | 193 | 72 | 72,83% |
| 2011 | 291 | 220 | 71 | 75,60% |
| 2012 | 288 | 210 | 78 | 72,92% |
| 2013 | 261 | 195 | 66 | 74,71% |
| 2014 | 264 | 167 | 97 | 63,26% ⚠️ |
| 2015 | 306 | 226 | 80 | 73,86% |
| 2016 | 309 | 212 | 97 | 68,61% |
| 2017 | 308 | 234 | 74 | 75,97% |
| 2018 | 297 | 208 | 89 | 70,03% |
| 2019 | 259 | 195 | 64 | 75,29% |
| 2020 | 260 | 211 | 49 | **81,15%**  |
| 2021 | 260 | 181 | 79 | 69,62% |
| 2022 | 260 | 208 | 52 | **80,00%** |
| 2023 | 259 | 189 | 70 | 72,97% |
| 2024 | 260 | 177 | 83 | 68,08% |
| 2025 | 259 | 198 | 61 | 76,45% |

---

### EURUSD (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 178 | 82 | 68,46% |
| 2006 | 259 | 184 | 75 | 71,04% |
| 2007 | 259 | 187 | 72 | 72,20% |
| 2008 | 260 | 177 | 83 | 68,08% |
| 2009 | 259 | 176 | 83 | 67,95% ⚠️ |
| 2010 | 260 | 199 | 61 | 76,54% |
| 2011 | 260 | 191 | 69 | 73,46% |
| 2012 | 260 | 202 | 58 | 77,69% |
| 2013 | 260 | 187 | 73 | 71,92% |
| 2014 | 260 | 174 | 86 | 66,92% |
| 2015 | 259 | 192 | 67 | 74,13% |
| 2016 | 260 | 180 | 80 | 69,23% |
| 2017 | 259 | 188 | 71 | 72,59% |
| 2018 | 259 | 194 | 65 | 74,90% |
| 2019 | 259 | 200 | 59 | 77,22% |
| 2020 | 260 | 201 | 59 | 77,31% |
| 2021 | 260 | 191 | 69 | 73,46% |
| 2022 | 260 | 209 | 51 | **80,38%**  |
| 2023 | 259 | 204 | 55 | 78,76% |
| 2024 | 260 | 186 | 74 | 71,54% |
| 2025 | 259 | 206 | 53 | **79,54%** |

---

### GBPUSD (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 204 | 56 | 78,46% |
| 2006 | 259 | 191 | 68 | 73,75% |
| 2007 | 259 | 202 | 57 | 77,99% |
| 2008 | 260 | 183 | 77 | 70,38% |
| 2009 | 259 | 199 | 60 | 76,83% |
| 2010 | 259 | 198 | 61 | 76,45% |
| 2011 | 260 | 202 | 58 | 77,69% |
| 2012 | 260 | 204 | 56 | 78,46% |
| 2013 | 260 | 182 | 78 | 70,00% ⚠️ |
| 2014 | 260 | 204 | 56 | 78,46% |
| 2015 | 259 | 199 | 60 | 76,83% |
| 2016 | 259 | 197 | 62 | 76,06% |
| 2017 | 259 | 199 | 60 | 76,83% |
| 2018 | 259 | 196 | 63 | 75,68% |
| 2019 | 259 | 191 | 68 | 73,75% |
| 2020 | 260 | 204 | 56 | 78,46% |
| 2021 | 260 | 188 | 72 | 72,31% |
| 2022 | 260 | 202 | 58 | 77,69% |
| 2023 | 259 | 208 | 51 | **80,31%**  |
| 2024 | 260 | 186 | 74 | 71,54% |
| 2025 | 259 | 192 | 67 | 74,13% |

---

### NZDUSD (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 192 | 68 | 73,85% |
| 2006 | 259 | 189 | 70 | 72,97% |
| 2007 | 259 | 184 | 75 | 71,04% |
| 2008 | 260 | 192 | 68 | 73,85% |
| 2009 | 259 | 190 | 69 | 73,36% |
| 2010 | 259 | 194 | 65 | 74,90% |
| 2011 | 260 | 199 | 61 | 76,54% |
| 2012 | 260 | 186 | 74 | 71,54% |
| 2013 | 260 | 186 | 74 | 71,54% |
| 2014 | 260 | 183 | 77 | 70,38% |
| 2015 | 259 | 202 | 57 | 77,99% |
| 2016 | 259 | 196 | 63 | 75,68% |
| 2017 | 259 | 178 | 81 | 68,73% ⚠️ |
| 2018 | 259 | 181 | 78 | 69,88% |
| 2019 | 259 | 213 | 46 | **82,24%**  |
| 2020 | 260 | 198 | 62 | 76,15% |
| 2021 | 260 | 185 | 75 | 71,15% |
| 2022 | 260 | 201 | 59 | 77,31% |
| 2023 | 259 | 195 | 64 | 75,29% |
| 2024 | 260 | 192 | 68 | 73,85% |
| 2025 | 259 | 190 | 69 | 73,36% |

---

### USDCAD (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 197 | 63 | 75,77% |
| 2006 | 259 | 200 | 59 | 77,22% |
| 2007 | 259 | 172 | 87 | 66,41% ⚠️ |
| 2008 | 259 | 200 | 59 | 77,22% |
| 2009 | 259 | 182 | 77 | 70,27% |
| 2010 | 259 | 206 | 53 | **79,54%**  |
| 2011 | 260 | 186 | 74 | 71,54% |
| 2012 | 260 | 180 | 80 | 69,23% |
| 2013 | 260 | 198 | 62 | 76,15% |
| 2014 | 260 | 184 | 76 | 70,77% |
| 2015 | 259 | 193 | 66 | 74,52% |
| 2016 | 259 | 200 | 59 | 77,22% |
| 2017 | 259 | 190 | 69 | 73,36% |
| 2018 | 259 | 201 | 58 | 77,61% |
| 2019 | 259 | 204 | 55 | 78,76% |
| 2020 | 260 | 179 | 81 | 68,85% |
| 2021 | 260 | 187 | 73 | 71,92% |
| 2022 | 260 | 191 | 69 | 73,46% |
| 2023 | 259 | 192 | 67 | 74,13% |
| 2024 | 260 | 186 | 74 | 71,54% |
| 2025 | 259 | 190 | 69 | 73,36% |

---

### USDCHF (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 174 | 86 | 66,92% |
| 2006 | 259 | 179 | 80 | 69,11% |
| 2007 | 259 | 197 | 62 | 76,06% |
| 2008 | 260 | 178 | 82 | 68,46% |
| 2009 | 259 | 176 | 83 | 67,95% ⚠️ |
| 2010 | 260 | 194 | 66 | 74,62% |
| 2011 | 260 | 178 | 82 | 68,46% |
| 2012 | 260 | 193 | 67 | 74,23% |
| 2013 | 260 | 178 | 82 | 68,46% |
| 2014 | 260 | 177 | 83 | 68,08% |
| 2015 | 258 | 193 | 65 | 74,81% |
| 2016 | 259 | 202 | 57 | 77,99% |
| 2017 | 259 | 193 | 66 | 74,52% |
| 2018 | 259 | 197 | 62 | 76,06% |
| 2019 | 259 | 196 | 63 | 75,68% |
| 2020 | 260 | 200 | 60 | 76,92% |
| 2021 | 260 | 190 | 70 | 73,08% |
| 2022 | 260 | 207 | 53 | **79,62%**  |
| 2023 | 259 | 203 | 56 | 78,38% |
| 2024 | 260 | 181 | 79 | 69,62% |
| 2025 | 259 | 200 | 59 | 77,22% |

---

### USDJPY (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 202 | 58 | 77,69% |
| 2006 | 259 | 192 | 67 | 74,13% |
| 2007 | 259 | 176 | 83 | 67,95% |
| 2008 | 260 | 171 | 89 | 65,77% ⚠️ |
| 2009 | 259 | 196 | 63 | 75,68% |
| 2010 | 259 | 196 | 63 | 75,68% |
| 2011 | 260 | 197 | 63 | 75,77% |
| 2012 | 260 | 176 | 84 | 67,69% |
| 2013 | 260 | 188 | 72 | 72,31% |
| 2014 | 260 | 199 | 61 | 76,54% |
| 2015 | 259 | 201 | 58 | 77,61% |
| 2016 | 259 | 182 | 77 | 70,27% |
| 2017 | 259 | 181 | 78 | 69,88% |
| 2018 | 259 | 187 | 72 | 72,20% |
| 2019 | 259 | 190 | 69 | 73,36% |
| 2020 | 260 | 182 | 78 | 70,00% |
| 2021 | 260 | 208 | 52 | **80,00%**  |
| 2022 | 260 | 198 | 62 | 76,15% |
| 2023 | 259 | 191 | 68 | 73,75% |
| 2024 | 260 | 179 | 81 | 68,85% |
| 2025 | 259 | 187 | 72 | 72,20% |

---

### XAGUSD - Perak (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 259 | 206 | 53 | **79,54%**  |
| 2006 | 259 | 189 | 70 | 72,97% |
| 2007 | 262 | 165 | 97 | 62,98% ⚠️ |
| 2008 | 263 | 200 | 63 | 76,05% |
| 2009 | 259 | 188 | 71 | 72,59% |
| 2010 | 259 | 172 | 87 | 66,41% |
| 2011 | 258 | 190 | 68 | 73,64% |
| 2012 | 258 | 184 | 74 | 71,32% |
| 2013 | 258 | 189 | 69 | 73,26% |
| 2014 | 258 | 179 | 79 | 69,38% |
| 2015 | 258 | 206 | 52 | **79,84%** |
| 2016 | 258 | 196 | 62 | 75,97% |
| 2017 | 257 | 187 | 70 | 72,76% |
| 2018 | 258 | 176 | 82 | 68,22% |
| 2019 | 258 | 175 | 83 | 67,83% |
| 2020 | 260 | 178 | 82 | 68,46% |
| 2021 | 260 | 194 | 66 | 74,62% |
| 2022 | 258 | 178 | 80 | 68,99% |
| 2023 | 258 | 203 | 55 | 78,68% |
| 2024 | 259 | 175 | 84 | 67,57% |
| 2025 | 258 | 186 | 72 | 72,09% |

---

### XAUUSD - Emas (2005-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2005 | 260 | 196 | 64 | 75,38% |
| 2006 | 259 | 179 | 80 | 69,11% |
| 2007 | 259 | 168 | 91 | 64,86% |
| 2008 | 260 | 212 | 48 | **81,54%**  |
| 2009 | 259 | 193 | 66 | 74,52% |
| 2010 | 259 | 166 | 93 | 64,09% ⚠️ |
| 2011 | 258 | 192 | 66 | 74,42% |
| 2012 | 258 | 191 | 67 | 74,03% |
| 2013 | 258 | 180 | 78 | 69,77% |
| 2014 | 258 | 176 | 82 | 68,22% |
| 2015 | 258 | 188 | 70 | 72,87% |
| 2016 | 258 | 196 | 62 | 75,97% |
| 2017 | 257 | 178 | 79 | 69,26% |
| 2018 | 258 | 170 | 88 | 65,89% |
| 2019 | 258 | 189 | 69 | 73,26% |
| 2020 | 260 | 184 | 76 | 70,77% |
| 2021 | 260 | 185 | 75 | 71,15% |
| 2022 | 259 | 191 | 68 | 73,75% |
| 2023 | 258 | 196 | 62 | 75,97% |
| 2024 | 259 | 189 | 70 | 72,97% |
| 2025 | 258 | 172 | 86 | 66,67% |

---

### XTIUSD - Minyak Mentah WTI (2010-2025)

| Tahun | Total | Dalam Streak | Reversal | Streak % |
|-------|-------|--------------|----------|----------|
| 2010 | 209 | 160 | 49 | 76,56% |
| 2011 | 308 | 203 | 105 | 65,91% ⚠️ |
| 2012 | 311 | 226 | 85 | 72,67% |
| 2013 | 273 | 198 | 75 | 72,53% |
| 2014 | 258 | 175 | 83 | 67,83% |
| 2015 | 258 | 189 | 69 | 73,26% |
| 2016 | 258 | 196 | 62 | 75,97% |
| 2017 | 257 | 190 | 67 | 73,93% |
| 2018 | 258 | 178 | 80 | 68,99% |
| 2019 | 258 | 193 | 65 | 74,81% |
| 2020 | 259 | 189 | 70 | 72,97% |
| 2021 | 258 | 191 | 67 | 74,03% |
| 2022 | 258 | 191 | 67 | 74,03% |
| 2023 | 257 | 203 | 54 | **78,99%**  |
| 2024 | 259 | 184 | 75 | 71,04% |
| 2025 | 258 | 177 | 81 | 68,60% |

---

##  EKSTREM TAHUNAN

### Tahun dengan Streak Tertinggi (Terbaik untuk Trend Following)

| Rank | Pair | Tahun | Streak % | Event Pasar |
|------|------|-------|----------|------------|
|  1 | NZDUSD | 2019 | **82,24%** | Tren perang dagang |
|  2 | XAUUSD | 2008 | **81,54%** | Krisis finansial safe-haven |
|  3 | AUDUSD | 2020 | **81,15%** | Volatilitas COVID-19 |
| 4 | EURUSD | 2022 | **80,38%** | Perang Ukraina, inflasi |
| 5 | GBPUSD | 2023 | **80,31%** | Tren arah kuat |

### Tahun dengan Streak Terendah (Pasar Choppy)

| Rank | Pair | Tahun | Streak % | Event Pasar |
|------|------|-------|----------|------------|
| 1 | XAGUSD | 2007 | **62,98%** | Ketidakpastian pra-krisis |
| 2 | AUDUSD | 2014 | **63,26%** | Lingkungan volatilitas rendah |
| 3 | XAUUSD | 2010 | **64,09%** | Konsolidasi pasca-krisis |
| 4 | XAUUSD | 2007 | **64,86%** | Ketidakpastian pra-krisis |
| 5 | USDJPY | 2008 | **65,77%** | Puncak krisis finansial |

---

##  TEMUAN UTAMA

### 1. Momentum Mendominasi Pasar
**~73% dari semua candle adalah bagian dari momentum streak** di semua pair dan semua tahun. Ini adalah karakteristik pasar universal.

### 2. Candle Reversal Sering Kali "Jebakan"
Hanya **~27% adalah candle reversal terisolasi**. Ini sering kali candle "terjebak" yang tidak berlanjut - mereka berbalik tapi langsung berbalik lagi.

### 3. Konsistensi di Semua Instrumen
Semua 10 pair menunjukkan persentase streak antara **71-76%**, mengindikasikan ini bukan spesifik pair tapi perilaku pasar fundamental.

### 4. Tahun Krisis Menciptakan Tren Kuat
- **Krisis Finansial 2008**: XAUUSD menunjukkan 81,54% streak (tren safe-haven kuat)
- **COVID-19 2020**: AUDUSD menunjukkan 81,15% streak (pergerakan arah kuat)
- **Perang Ukraina 2022**: EURUSD menunjukkan 80,38% streak (tren kuat)

### 5. Volatilitas Rendah = Lebih Banyak Reversal
Tahun seperti 2014 secara konsisten menunjukkan persentase streak lebih rendah (~63-67%) di multiple pair karena kondisi choppy dan range-bound.

### 6. GBPUSD adalah Pair Paling Trending
Dengan 75,96% candle dalam streak, GBPUSD menunjukkan kecenderungan terkuat untuk melanjutkan arah yang sama.

### 7. Emas (XAUUSD) Paling Prone Reversal
Dengan tingkat streak 71,79% (terendah di antara semua pair), Emas menunjukkan reversal terisolasi relatif lebih banyak, meskipun tetap didominasi momentum.

---

##  IMPLIKASI TRADING

### Matematikanya Jelas

```
Trading DENGAN momentum streak:
├── Anda berada di sisi yang benar 73% dari waktu
├── Anda ride beberapa candle berturut-turut
├── Candle reversal adalah "noise" terisolasi
└── Probabilitas: ~3 dari 4 candle melanjutkan

Trading MELAWAN momentum (menangkap reversal):
├── Anda melawan tren 73% dari waktu
├── Kebanyakan reversal tidak berlanjut
├── Anda menangkap pisau jatuh
└── Probabilitas: Hanya ~1 dari 4 candle berbalik dan berlanjut
```

### Rekomendasi Strategi

| Strategi | Rekomendasi | Alasan |
|----------|-------------|--------|
| **Trend Following** | ✅ SANGAT DIREKOMENDASIKAN | 73% candle dalam streak |
| **Breakout Trading** | ✅ DIREKOMENDASIKAN | Selaras dengan kelanjutan streak |
| **Mean Reversion** | ⚠️ RISIKO TINGGI | Hanya 27% reversal sejati |
| **Counter-Trend** | ❌ TIDAK DIREKOMENDASIKAN | Melawan probabilitas 73% |

### Pair Terbaik untuk Trend Following

| Rank | Pair | Streak % | Rekomendasi |
|------|------|----------|------------|
| 1 | GBPUSD | 75,96% | ⭐⭐⭐ Excellent |
| 2 | NZDUSD | 74,12% | ⭐⭐⭐ Excellent |
| 3 | USDCAD | 73,92% | ⭐⭐⭐ Excellent |
| 4 | EURUSD | 73,62% | ⭐⭐ Sangat Baik |
| 5 | USDCHF | 73,33% | ⭐⭐ Sangat Baik |

---

## ️ DETAIL TEKNIS

### Format Data Sumber
```
<DATE>    <OPEN>    <HIGH>    <LOW>    <CLOSE>    <TICKVOL>    <VOL>    <SPREAD>
2005.01.03    1.3555    1.3574    1.3465    1.3510    89234    0    0
```

### Algoritma (Python Pseudocode)
```python
def analyze_momentum_streaks(candles):
    directions = [get_direction(c) for c in candles]
    
    # Temukan semua streak 2+ candle searah berturut-turut
    streaks = find_consecutive_streaks(directions, min_length=2)
    
    # Tandai candle yang bagian dari streak
    candles_in_streak = set()
    for streak in streaks:
        for i in range(streak.start, streak.end + 1):
            candles_in_streak.add(i)
    
    # Hitung
    in_streak_count = len(candles_in_streak)
    reversal_count = total_candles - in_streak_count
    
    return {
        'streak_percentage': in_streak_count / total_candles * 100,
        'reversal_percentage': reversal_count / total_candles * 100
    }
```

### Tools yang Digunakan
- Python 3.x
- CSV module untuk parsing data
- Analisis dilakukan: Januari 2025

---

##  KESIMPULAN

```
╔═══════════════════════════════════════════════════════════════════╗
║                                                                   ║
║   73% CANDLE BERADA DALAM MOMENTUM STREAK                        ║
║   27% ADALAH REVERSAL TERISOLASI                                 ║
║                                                                   ║
║   "THE TREND IS YOUR FRIEND" - DIBUKTIKAN OLEH DATA              ║
║                                                                   ║
╚═══════════════════════════════════════════════════════════════════╝
```

### Poin-Poin Penting

1. **Momentum mendominasi** - Hampir 3 dari 4 candle melanjutkan arah yang sama
2. **Reversal adalah jebakan** - Kebanyakan candle reversal terisolasi dan tidak berlanjut
3. **Pola universal** - Ini berlaku di semua 10 instrumen selama 20 tahun
4. **Trading dengan tren** - Data sangat mendukung strategi trend-following
5. **Hindari counter-trend** - Melawan momentum berarti melawan probabilitas 73%

### Rekomendasi Akhir

> **Selalu trading dalam arah momentum streak saat ini. Probabilitasnya sangat mendukung Anda.**

---

## ⚠️ DISCLAIMER

1. Hasil ini berdasarkan data historis dan tidak menjamin hasil di masa depan
2. Analisis ini hanya memeriksa pola arah candle, bukan:
   - Ukuran body candle
   - Volume
   - Konteks struktur pasar
   - Event fundamental
3. Selalu gunakan manajemen risiko yang tepat terlepas dari edge statistik
4. Performa masa lalu tidak menjamin hasil di masa depan

---

##  LISENSI

MIT License - Bebas digunakan, dimodifikasi, dan didistribusikan.

---

*Dokumentasi ini berdasarkan analisis 53.551 candle daily dari 10 instrumen trading selama periode 2005-2025.*

*Analisis dilakukan: Januari 2025*
