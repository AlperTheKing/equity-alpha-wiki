---
type: concept
name: expected_returns_vs_cash_flows
related_papers: [[cochrane2011_discount_rates]]
---

# Expected Returns vs. Cash Flows — Present-Value Decomposition

## Tanım

Bir hisse senedinin fiyatı bekleneninin iskonto edilmiş değeridir:

`P_t = E_t [ Σ_{j=1}^∞ M_{t,t+j} · D_{t+j} ]`

Bu identity'de **fiyat varyasyonunun** iki olası kaynağı vardır:

1. **Beklenen cashflow (E[D]) varyasyonu** — gelecekteki dividend / earnings
   beklentilerinin değişmesi
2. **Discount rate (M, expected return) varyasyonu** — beklenen-getirinin
   değişmesi

[[cochrane2011_discount_rates]] [Tablo II, s.2] kanıtı: P/D varyasyonunun
**neredeyse tamamı** discount rate varyasyonu (b_d ≈ 0).

## Campbell-Shiller (1988) approximate identity

Log-linearization ile:

`dp_t ≈ Σ_{j=1}^∞ ρ^{j-1} [ r_{t+j} − Δd_{t+j} ]`

- `dp_t = log(D_t/P_t)`
- `r = log return`
- `Δd = log dividend growth`
- `ρ ≈ 0.96` (ortalama D/P'ye bağlı yaklaşım sabiti)

Long-run regression ile:

`1 ≈ b_r(k) − b_d(k) + b_dp(k)`

[[cochrane2011_discount_rates]] [Tablo II, s.2] (CRSP value-weighted, 1947-2009):

| Yöntem | b_r | b_d | b_dp |
|---|---|---|---|
| Direct k=15 | 1.01 | -0.11 | -0.11 |
| VAR k=15 | 1.05 | 0.27 | 0.22 |
| VAR k=∞ | 1.35 | 0.35 | 0.00 |

**Yorumu:** P/D varyasyonunun **>%100'ü** discount rate (b_r > 1), dividend
büyümesi varyasyonu **negatif veya sıfır** etkide (b_d ≤ 0).

## Bu wiki'nin strateji tasarımına spesifik implikasyonu

- **Cross-section'da aynı mantık:** İki firma aynı E[D]'ye sahipken farklı
  P/D'ye sahipse, düşük P (yüksek E[R]) firma daha yüksek beklenen getiri taşır
  [[famafrench2015_five_factor]] [Eq.(1)-(3), s.2-3].
- **Wiki'nin amacı için anlamı:** Fundamental faktörler (B/M, P/E, P/CF) **bir
  noktaya kadar discount rate proxy'leridir.** Yüksek B/M = düşük P (yüksek E[R]).
  Yani [[HML]] aslında **bir discount rate spread mimicking portfolio**'dur
  [[cochrane2011_discount_rates]] yorumu.
- **Time-series tetik:** Bir stratejinin geçmiş performansının **gelecekte aynı
  kalmaması beklenir** çünkü discount rate'ler değişiyor. Bu, post-publication
  decay (McLean-Pontiff 2016) ve momentum crashes (Daniel-Moskowitz 2016) gibi
  fenomenlerin teorik beklentisidir.
- **Cashflow-based stratejiler için uyarı:** Eğer **E[D] iyi tahmin edilebilirse**
  (örn. yüksek-kaliteli analyst forecast'leri ile), o zaman cashflow-based
  signal *bağımsız bir alpha kaynağı* olabilir. Ancak Cochrane çerçevesinde
  pure-cashflow tahmin alpha kaynağı sınırlı — Faz 3'te tartışılır.

## İlgili paperlar (ingested)

- [[cochrane2011_discount_rates]] — kavramın bu wiki için kanonik kaynağı

## İlgili paperlar (henüz ingest edilmedi)

- Campbell-Shiller (1988) "The Dividend-Price Ratio and Expectations of Future
  Dividends and Discount Factors" — original identity (referans olarak)
- Frankel-Lee (1998) "Accounting Valuation, Market Expectation, and Cross-Sectional
  Stock Returns" — V/P ratio, accounting-based intrinsic value (Tier 1 #8)

## İlgili kavramlar

- [[discount_rates]]
- [[factor_zoo]]
- [[factor_model]]
