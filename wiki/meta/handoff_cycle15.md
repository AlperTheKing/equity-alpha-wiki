# Handoff Context Dump — Cycle 16 Öncesi (2026-05-01)

> Yeni Claude Code session açıldığında bu dosya + CLAUDE.md +
> log.md son 10 entry + meta/handoff.md (eski, Cycle 11 öncesi) +
> source_tier_list.md okunacak.
>
> **Bu wiki'nin 2. handoff'u.** Cycle 11 öncesi handoff'tan sonra
> Faz 1 omurgası tamamlandı; Cycle 16 öncesi F bloğu (intangibles)
> finalizasyonu açılıyor. Wiki gelişim hikayesi handoff'lar üzerinden
> okunabilsin diye **mevcut handoff.md OVERWRITE EDİLMEDİ**, ek
> dosya olarak yazıldı.

---

## 1. Mevcut state özeti

### Tamamlanan cycle'lar (1-15) blok gruplaması ile

**A bloğu — Foundational factor models (Cycle 1-4):**

| Cycle | Paper | Tarih |
|---|---|---|
| 1 | Fama-French 1993 (FF3) | 2026-04-27 |
| 2 | Fama-French 2015 (FF5) | 2026-04-27 |
| 3 | Carhart 1997 (4F + UMD) | 2026-04-27 |
| 4 | Cochrane 2011 (Discount Rates / Factor Zoo) | 2026-04-27 |

**B bloğu — Winner-loser identification (Cycle 5-8):**

| Cycle | Paper | Tarih |
|---|---|---|
| 5 | Piotroski 2000 (F-Score) | 2026-04-27 |
| 6 | Mohanram 2005 (G-Score) | 2026-04-27 |
| 7 | Li-Mohanram 2019 (F+G+V/P+PEG) | 2026-04-27 |
| 8 | Hou-Mo-Xue-Zhang 2020 (Security Analysis q5) | 2026-04-27 |

**C bloğu — Earnings quality / accruals / investment (Cycle 9-10):**

| Cycle | Paper | Tarih |
|---|---|---|
| 9 | Sloan 1996 (Accruals Anomaly) | 2026-04-28 |
| 10 | Cooper-Gulen-Ion 2018 (Asset Growth) | 2026-04-28 |

**D bloğu — Replication / multiple testing / decay / backtest overfitting (Cycle 11-14, EPISTEMIK OMURGA):**

| Cycle | Paper | Tarih | Bacak |
|---|---|---|---|
| 11 | McLean-Pontiff 2016 (Post-Publication Decay) | 2026-04-28 | behavioral decay |
| 12 | Harvey-Liu-Zhu 2016 (Multiple Testing) | 2026-04-28 | statistical FDR |
| 13 | Hou-Xue-Zhang 2020 (Replicating Anomalies) | 2026-04-30 | empirik replication |
| 14 | Bailey-López de Prado 2014 (Deflated Sharpe Ratio) | 2026-05-01 | backtest overfitting (5. darbe AÇILMADI) |

**F bloğu — Intangibles / R&D capitalization (Cycle 15+, Faz 1 finalizasyon):**

| Cycle | Paper | Tarih |
|---|---|---|
| 15 | Lev-Sougiannis 1996 (R&D Capitalization) | 2026-05-01 |
| 16 | Peters-Taylor 2017 (Intangible Capital) | (PDF hazır, Cycle 16'da ingest) |
| 17 | Lev-Srivastava 2020 (Value Failure Post-2010) | (PDF hazır, Cycle 17'de ingest) |

> 📝 Kullanıcının mental block yapısı ("E bloğu — large-cap reality")
> ile source_tier_list resmi yapısı farklı. Wiki'de sıralı blok
> A→B→C→D→F (E atlandı; Israel-Moskowitz 2013 + FF 2008 Faz 2'ye
> ertelendi — Cycle 14 mini consolidation kararları).

### Wiki sayfa sayısı (Cycle 15 sonu)

- **Papers:** 15 (FF93, **Lev-Sougiannis 1996**, Sloan 1996, Carhart
  1997, Piotroski 2000, Mohanram 2005, Cochrane 2011, Bailey-LdP 2014
  DSR, FF15, HLZ 2016, McLean-Pontiff 2016, CGS-Ion 2018, Li-Mohanram
  2019, HMXZ 2020 Security Analysis, HXZ 2020 Replicating Anomalies)
- **Factors:** 11 (Accruals, Asset_Growth, CMA, F_Score, G_Score, HML,
  Magic_Formula, MKT_RF, RMW, SMB, UMD)
- **Concepts:** 16 (accruals_anomaly, anomaly_replication,
  asset_growth_anomaly, **backtest_overfitting**, contextual_fundamental_analysis,
  discount_rates, earnings_quality, expected_returns_vs_cash_flows,
  factor_model, factor_zoo, fundamental_scoring, **intangibles_adjusted_accounting**,
  multiple_testing, post_publication_decay, value_premium,
  winner_loser_identification)
- **Comparisons:** 1 (f_score_vs_g_score)
- **Meta:** 7 (source_tier_list, MoC_papers, MoC_factors,
  open_questions, contradictions, data_gaps, handoff [eski Cycle 11
  öncesi]) + index, log, README, **handoff_cycle15** (bu dosya)
- **Strategies:** 0 (Faz 3'te dolacak)
- **Methodology:** 0 (Cycle 20 sonu açılacak)
- **Toplam .md dosya:** ~53

### Aktif open_questions

**Toplam Q sayısı:** 39 (Q1-Q39).

**Fully-answered:**
- **Q5** (Post-publication decay anchor) — fully-answered üç-bacak
  epistemik omurga tüm bacaklarda (MP behavioral + HLZ statistical +
  HXZ empirical); Sloan operating accruals dört darbenin TAMAMINDA
  hayatta kalan nadir anomaly
- **Q11** (SMB post-1991 + large-cap relevance) — fully-answered
  statistical düzeyde; HLZ Şekil 3 SMB never sig under multiple
  testing (Bonferroni / Holm / BHY hepsi insig)
- **Q17** (Cochrane #3 — kaç factor really matter) — fully-answered
  üç-bacak epistemik düzeyde; factor zoo gerçek replicable subset
  K=10-30 arası (behavioral %65 + statistical %10-30 + empirical %10
  net sig)

**Cycle 15 partial-stronger updates:**
- Q23 (NDX intangibles q-factor span) — Lev-Sougiannis methodology
  partial; tam cevap Peters-Taylor 2017 (Cycle 16) ile
- Q26 (tech firma accrual ölçümü R&D distortion) — Lev-Sougiannis
  mekanizma cevabı (R&D giderleştirme working capital azaltır)
- Q1 (S&P 500 value post-2000) — kavramsal hazırlık (B/M intangibles-
  yoğun firms'da yapay sinyal); tam cevap Lev-Srivastava 2020 (Cycle
  17) ile

**Cycle 15 yeni Q'lar:**
- Q38 (industry-spesifik R&D amortization NDX kalibrasyon) — Faz 3
  tasarım kararı
- Q39 (R&D capital stock vs flow ölçümü) — Faz 3 tasarım kararı;
  Lev-Sougiannis [s.133 fn 22] proper capitalization stock 3-yıl
  flow toplamı'ndan dramatic farklı

### 2 Contradictions entry

1. **HML faktörünün incremental information durumu — FF93 ↔ FF15
   evrimi** (Cycle 2; resolution: scope-dependent + sample-dependent;
   Cochrane #1 normal evrim)
2. **Aggregate anomaly survival rate — McLean-Pontiff 2016 ↔ HXZ 2020
   methodology farkı** (Cycle 13; resolution: scope-dependent;
   methodology disagreement; HXZ paper [s.3] MP'yi explicit eleştirir
   ama empirik çürütme değil)

### Bütünsel wiki sağlığı: **TEMIZ**

- 15 cycle'ın hepsi TEMIZ devam ile geçti
- Cycle 8 + 16 (4-cycle ardışık) §11.5 consolidation pass tetiklenmesi
  bekleniyordu; Cycle 8 yapıldı, Cycle 16 ardışık §11.5 consolidation
  pass Cycle 16 ingest sonrasında ZORUNLU
- Cycle 12 + Cycle 14 lint_pass entries (typo + meta-not düzeltmeleri)
- 2 contradictions entry resmi resolution
- Çerçeve genişleme disiplini meta-not'unun ilk gerçek testi (Cycle 14
  DSR) **GEÇTİ** — paper [s.8] complementary methods konumlandırması
  wiki kararıyla uyumlu
- D bloğu (epistemik omurga) Cycle 11-14 tamamlandı
- F bloğu (intangibles) Cycle 15-17 yol haritası açıldı

---

## 2. B+C bloğu kapanış cümleleri (Cycle 8 consolidation pass'inden, aynen kopya)

**B bloğu net çıkarım (4 cümle):**

1. Standalone fundamental scoring (F-Score, G-Score, V/P, PEG, Magic Formula) **anchor evrenlerinde** robust hedge return üretiyor — orijinal sample'larda +20-23%, modern replikasyonda +6-7% (post-publication decay + universe genişlemesi).

2. **Combined yaklaşımlar** (F&V/P, G&V/P) anchor evrenlerde standalone'un 2.5-3x'i hedge return üretiyor (G&V/P **+21.45%** Li-Mohanram'da en yüksek), quality ve value boyutlarının **negatif korelasyonundan** ötürü.

3. **q5 model lens'inde** fundamental skorların getirisi büyük cap segmentinde **risk premium exposure'ları üzerinden taşınıyor** (HMXZ); standalone alpha **microcap residual** + **active discretionary fund** (Buffett tipi) kalıntısına sınırlı.

4. Strateji tasarımı için **wiki'nin pratik pozisyonu**: large-cap evrene transfer için (1) S&P 500 → F-anchor + V/P combined; (2) Nasdaq 100 → G-anchor + NEGPEG combined; (3) baseline benchmark **q5 model alpha** kontrollü; (4) microcap effects ve Buffett-tipi alpha **scope dışı**.

**C bloğu (Cycle 9-10) kümülatif çıkarım (özet):**

- Sloan 1996 → F_ACCRUAL ve G3 binary versiyonların **origin paper'ı**; raw +10.4% headline (1962-1991, NYSE+AMEX) ama size-adjusted ~2.9% marjinal → anomaly **size-loaded** uyarısı
- CGS-Ion 2018 → CMA / q5 I/A factor'ün empirical performansı CGS asset growth ölçüsüne **kritik bağlı**; CAPX/PPE/intangibles ile değiştirilemiyor; "investment proxy" yorumu ⚠️ challenged
- Sloan accruals ↔ CGS asset growth **working capital overlap**; F_ACCRUAL ile CMA exposure birlikte kullanmak partial redundancy
- C bloğu wiki'ye **mekanizma çatallanması** ekledi: rational risk premium (HXZ q-theory) vs mispricing (Sloan/CGS); wiki taraf tutmaz, mathematical equivalence

---

## 2b. D bloğu kapanış cümleleri (Cycle 14 sonu, log entry'sinden aynen kopya)

**D bloğu net çıkarım (5 cümle, B bloğu Cycle 8 paterninde):**

1. **Üç-bacak epistemik omurga:** Behavioral decay (MP %35 sig 1%) + statistical FDR (HLZ `|t|>3.0` BHY 1%) + empirik replication (HXZ NYSE-VW %64-85 insig); üç ortogonal mekanizma, aynı conclusion — factor zoo'nun büyük çoğunluğu false discovery, gerçek replicable subset K=10-30 arası.

2. **Dört darbe çerçevesi:** Wiki ingested factor/strateji'leri için sentez (in-sample large-cap + post-pub decay + MT-corrected sig + methodology-robust replication); Sloan operating accruals + R&D-to-market + Earnings announcement Abr + Cash-based Cop dört darbeden 4/4 hayatta kalan factorler, F&V/P + G&V/P + G&NEGPEG combined 3/4 (Q31 ortogonal), UMD + CMA + HML 3/4 (q-factor span = exposure proxy).

3. **Backtest overfitting Sharpe-spesifik ek filter (DSR):** Bailey-LdP 2014 DSR formülü Faz 3 backtest spec için methodology baseline; trial-count HLZ Sharpe-uygulaması, skewness/kurtosis tam ortogonal yeni filter, sample length statistical correction; **çerçeve genişleme disiplini meta-not'a göre 5. darbe AÇILMADI** — DSR factor selection değil Sharpe reporting filter; çerçeve dört darbede sabitlendi.

4. **Çelişkiler ve resolution:** Wiki 2 contradictions entry tutuyor — HML evrimi FF93↔FF15 (scope+sample-dependent) + MP 2016 ↔ HXZ 2020 methodology farkı (scope-dependent); Q5 ve Q17 fully-answered üç-bacak omurga; Q11 fully-answered statistical (SMB never sig under MT).

5. **Faz 3'e geçiş disiplini:** D bloğu (epistemik omurga) tamamlandı; **Cycle 14 sonrası mini consolidation pass** (Faz 1 durumu + Tier 1 kalan paperlar + E/F bloğu kararı + Faz 1→Faz 2 sertifika kriterleri); methodology/backtest_spec.md ön-açma zamanı mini consolidation'da kararlaştırılır.

---

## 3. F bloğu (intangibles) progression

**F bloğu hedefi:** NDX strateji intangibles-aware methodology temeli.
Cycle 9-14 boyunca tekrarlanan "intangibles methodology eksikliği"
data_gaps boşluğunu kapatma. NDX evrene FAANG-dominant tech firmalar
için geleneksel HML/Bm + Sloan accruals + CMA factor'lerinin yapısal
bias'larının düzeltilmesi.

### Cycle 15 — Lev-Sougiannis 1996 (TAMAM, NDX yapısal foundation)

- R&D capitalization origin paper; industry-spesifik amortization rates
- 6 sektör: Pharma 9 yıl useful life, Scientific Instruments 5 yıl
- 20.55% earnings + 22.2% book equity understatement
- **R&D capital → 4.57% yıllık subsequent return implication** (RDC-yoğun
  firmalarda; [Tablo 5, s.132])
- **B/M coefficient kaybı** R&D-yoğun firms'da → HML factor R&D-yoğun
  firms'da yapay sinyal mi sorusu
- Mispricing vs extra-market risk yorumu açık [s.134] — wiki taraf
  tutmaz
- HXZ 2020 R&D-to-market dört darbe 4/4 hayatta kalan factor'ün
  methodology temeli
- Cycle 9 Sloan F_ACCRUAL/G3 origin pattern paralel: G6 (R&D/Assets)
  dual origin attribution (Mohanram conservatism + Lev-Sougiannis
  literatür hattı kökü)
- Concept açıldı: [[concepts/intangibles_adjusted_accounting]] F bloğu
  anchor concept

### Cycle 16 — Peters-Taylor 2017 (PDF hazır, ingest planı bekleniyor)

- `raw/papers/peters_taylor_2017_intangible_capital.pdf` (487 KB, 57 sayfa)
- "Intangible Capital and the Investment-q Relation" (JFE)
- Total intangible capital (R&D + advertising + organization) genişletme
- Lev-Sougiannis basic methodology'sini total capital'a çıkar
- CGS-Ion 2018 [s.5-6] paperde Peters-Taylor methodology'i kullanmıştı —
  "intangibles düzeltmesi yapılsa bile asset growth unique" bulgusu
  bu metodun Cycle 16 ingest sonrası tam dolacak
- ⚠️ **Cycle 16 §11.5 ZORUNLU 4-cycle ardışık consolidation pass
  tetiklenecek** (Cycle 12, 16, 20... pattern). Standart 6-spot audit
  yerine derin denetim pass'i.

### Cycle 17 — Lev-Srivastava 2020 (PDF hazır, ingest planı bekleniyor)

- `raw/papers/lev_srivastava_2020_value_failure.pdf` (1167 KB, 30 sayfa)
- "Explaining the Recent Failure of Value Investing"
- Post-2010 value collapse Lev-Sougiannis methodology üzerinden
  açıklama
- Q1 (S&P 500 value post-2000) tam cevabı için ön koşul
- F bloğu sonu kapanış sentezi (B+C+D paterninde)

### F bloğu sonu beklenen kapanış

NDX strateji intangibles-aware methodology temeli kurulmuş olur:
1. R&D capitalization (Lev-Sougiannis basic)
2. Total intangible capital (Peters-Taylor extension)
3. Post-2010 value collapse açıklaması (Lev-Srivastava)

[[concepts/intangibles_adjusted_accounting]] anchor concept tablosu
tamamen dolar; HML/Sloan/CMA/G6/R&D-to-market intangibles-aware
revisions için methodology baseline net olur.

---

## 4. Cycle 15-20 takvim hatırlatması

| Cycle | Paper / İş | Detay |
|---|---|---|
| **15** ✓ | Lev-Sougiannis 1996 | F bloğu #1 TAMAM (Cycle 15 sonu, bu handoff) |
| **16** | Peters-Taylor 2017 + **§11.5 ZORUNLU 4-cycle consolidation** | Total intangible capital; Cycle 12-16 consolidation pass |
| **17** | Lev-Srivastava 2020 | Post-2010 value collapse; Q1 tam cevap; F bloğu kapanış sentezi (5 cümle B/D paterninde) |
| **18** | Beneish 1999 | Tier 1 #15 forensic; M-Score; **son C/D hard kriter Tier 1 paperı** |
| **19** | **KARAR NOKTASI** | Cycle 18 sonu mini değerlendirme: Asness QMJ 2019 ekle/atla? Q2 (large-cap quality) ve Q14 (FF5 large-cap) durumuna bakarak. Şimdi karar yok. |
| **20** | **Faz 1 sertifikası** | (a) §11.5 consolidation pass; (b) **methodology/backtest_spec.md** açılır (DSR + walk-forward + NYSE-VW + dört darbe filter); (c) **CLAUDE.md §7 schema_update** (sayısal hedefler "25+ paper" yerine epistemik tamlık kriterleri); (d) Faz 2 plan |

> 📝 **Cycle 16 § 11.5 4-cycle consolidation pass içeriği** (CLAUDE.md
> §11.5'ten):
> - Orphan sayfa taraması
> - Çelişki taraması (HML evrimi + MP↔HXZ + yeni potansiyel)
> - Stale claim taraması (CGS-Ion challenged işaretleri + diğer)
> - MoC tutarlılığı
> - Broken wikilink taraması (Cycle 12'de eklenen Q-format check dahil)
> - Önerilen sonraki ingest (Cycle 17 Lev-Srivastava + sonrası)

---

## 5. Wiki disiplin patternları (yeni session için kritik)

### Otomatik audit cycle'ları

- **§11.2 6-spot audit** her ingest sonu **otomatik** (A factor entity
  + B Goal Alignment + C concept zenginleşmesi + D inbound link +
  E meta + F open_questions/data_gaps + Q-wikilink format check)
- **§11.5 4-cycle ardışık consolidation pass** ZORUNLU: Cycle 4, 8,
  12, 16, 20... (Cycle 8 ✓ + Cycle 12 ✓ + Cycle 16 BEKLENİYOR)
- **Mini consolidation pass** kullanıcı-istemi (Cycle 14 sonu yapıldı,
  Faz 1 finalizasyon karar noktası)

### Origin attribution dual pattern (Cycle 9 + Cycle 15)

Bir factor entity'nin "Origin" bölümünde iki kategori:
- **Paper-spesifik origin** (factor'u tanımlayan paper'ın özgün
  yorumu)
- **Literatür hattı kökü** (factor'un teorik dayanağı; ayrı bir
  paper tarafından kanıtlanan altyapı)

Kullanılan örnekler:
- Cycle 9: F-Score F_ACCRUAL → paper-spesifik Piotroski 2000 +
  literatür hattı Sloan 1996; G-Score G3 → paper-spesifik Mohanram
  2005 + literatür hattı Sloan 1996
- Cycle 15: G-Score G6 → paper-spesifik Mohanram 2005 conservatism
  yorumu + literatür hattı Lev-Sougiannis 1996 R&D capitalization

### Sayfa açma disiplini (CLAUDE.md §4)

- **Factor entity** (`/wiki/factors/`) — paper'da ortaya konan spesifik
  signal/factor; methodology paper için açılmaz (Cycle 15 örneği
  Lev-Sougiannis methodology paper, R&D-Intensity entity AÇILMADI)
- **Concept** (`/wiki/concepts/`) — ortogonal mekanizma + aggregate
  table + Faz 3 strateji girdi olan konu
- **Comparison** (`/wiki/comparisons/`) — head-to-head karşılaştırma,
  tablo formatı zorunlu
- **Strategy** (`/wiki/strategies/`) — Faz 2+ aday stratejiler

### "Üç darbe" → "Dört darbe" çerçeve genişleme disiplini meta-not (Cycle 13 + 14)

Yeni "darbe" eklenmesi için 3 kriter (CLAUDE.md §11.2 dışı, post_publication_decay
sayfasında):
- (a) ortogonal mekanizma
- (b) wiki'de aggregate tablosu olan
- (c) Faz 3 include/exclude doğrudan girdi olan

**5 darbe noktasında "yeniden dur ve değerlendir" disiplini.** İlk
gerçek test Cycle 14'te DSR ile yapıldı — kriterlerden 1/3 dolaylı +
1/3 kısmen + 1/3 reddedilir → 5. darbe AÇILMADI. Disiplin işledi.

### Q-wikilink format kuralı (Cycle 12 audit kuralı)

Q'lara wikilink referansı `[[meta/open_questions]] (QN)` formatında
yazılır; `[[QN]]` typo niteliğinde. Cycle 11'de Q5 typo'su Cycle 12'de
düzeltildi; Cycle 12 §11.2 audit Spot F'ye check eklendi. Wiki'de
aktif `[[QN]]` typo bulunmuyor (sadece log.md historical Cycle 12
lint_pass entry kaydı).

### Yazma disiplini (CLAUDE.md §6, NON-NEGOTIABLE)

- **Sayısal iddia kaynaksız geçemez** — her sayı paper sayfa atıflı
  veya `[[wikilink]]` ile gerekçelendirilir
- **Memory'den, training'den ekleme yasak** — wiki sadece raw/'daki
  kaynaklara dayanır
- **"muhtemelen", "genelde" hedge'leri yasak** — ya sayı ya kaynak
- **Çelişen kanıtları gizleme** — `contradictions.md`'de cross-reference
- **Türkçe wiki, paper isimleri/dergi isimleri İngilizce kalır**
- **YAML frontmatter zorunlu** (paper + factor + concept şablonlarında)
- **Wikilink syntax: `[[page_name]]`** (Obsidian-uyumlu)

### Epistemik pozisyonlar (wiki taraf tutmaz)

- **Mispricing vs risk premium yorumu açık** — Sloan/Piotroski/CGS/
  Lev-Sougiannis (mispricing eğilimi) vs HMXZ q5 model/HXZ Replicating
  (risk premium eğilimi) felsefi çatallanma; Cochrane mathematical
  equivalence ile her iki yorum aynı portföyü üretir
- **Methodology farkları çelişki olarak listelenmedi (scope-dependent
  resolution)** — örn. MP equal-weight all-stocks vs HXZ NYSE-VW
  microcap-arınmış: methodology disagreement, empirik çürütme değil

---

## 6. Yeni session "ilk 3 dakika" talimatı

Yeni Claude Code session açıldığında **sırayla**:

1. **CLAUDE.md oku** (operasyon kuralları, §11 self-audit governance,
   §4 sayfa şablonları)
2. **wiki/log.md son 10 entry oku**:
   ```
   grep "^## \[" wiki/log.md | tail -10
   ```
3. **wiki/meta/handoff.md oku** (eski, Cycle 11 öncesi — 10 cycle
   geçmişi; handoff_cycle15.md'den önce)
4. **wiki/meta/handoff_cycle15.md oku** (BU DOSYA — Cycle 15 sonu
   state)
5. **wiki/meta/source_tier_list.md oku** (Cycle 16 paper Peters-Taylor
   2017 Tier 2 #27)
6. Kullanıcıya tek cümleyle rapor: **"State refreshed, Cycle 16 ingest
   planına hazırım"**

Sonra kullanıcı "Cycle 16 ingest planını sun" dediğinde:
- Cycle 16 paper: Peters-Taylor 2017 (Tier 2 #27)
- PDF mevcut: `raw/papers/peters_taylor_2017_intangible_capital.pdf`
  (487 KB, 57 sayfa)
- F bloğu #2 ingest; Total intangible capital methodology
- ⚠️ **Cycle 16 ingest sonrası §11.5 ZORUNLU 4-cycle consolidation
  pass tetiklenir** (Cycle 12 + 16 + 20... pattern)

### Bağlam ipuçları (yeni session için)

- **Wiki dili Türkçe**, paper isimleri/dergi isimleri İngilizce kalır
- **Origin attribution dual pattern** Cycle 9 + 15'te kullanıldı,
  Cycle 16+'da Peters-Taylor için benzer pattern uygulanabilir (G6/G7
  organization capital + advertising bileşenleri için Lev-Sougiannis
  + Peters-Taylor dual origin)
- **Çerçeve genişleme disiplini meta-not** ([[post_publication_decay]])
  Cycle 14'te ilk testi geçti; Faz 2'de yeni paper'lar için aynı
  disiplin uygulanır
- **Faz 3 strateji tasarımı için pratik pozisyon**: S&P 500 → F+V/P
  combined; NDX → G+NEGPEG combined; q5 baseline kontrollü; **dört
  darbe çerçevesi** filter; **DSR-corrected Sharpe** reporting
- **PDF okuma:** Embedded text varsa `pdftotext -layout`; scanned
  ise PyMuPDF + multimodal Read tool (ff93 örneği)
- **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]`
  paper iç sayfa
- **PDF eksikliği durumunda:** kullanıcıdan yeniden adlandırma iste;
  CLAUDE.md slug standardı `firstauthor_year_short_topic.pdf` (Cycle
  15 başlangıcı 3 PDF örnekledi)

### Tetikleyici cümleler (CLAUDE.md §11.6)

- **"TEMIZ devam"** → audit sonrası bir sonraki cycle plan
- **"KÜÇÜK fix devam"** → düzeltme + sonraki cycle
- **"YAPISAL fix"** → kullanıcı talimatını bekle
- **"ABORT"** → ingest geri sar
- **"audit"** → mevcut sayfa(lar)a 6-spot audit
- **"consolidation"** → §11.5 derin denetim
- **"freeze ingest"** → ingest workflow durdur
- **Yeni Cycle 14 pattern:** disiplin meta-not testi paper okuma sonrası
  hipotez teyit/red

---

**Dosya yazıldı: 2026-05-01.** Cycle 15 ingest sonu state. Sonraki
session Cycle 16'ya başlayacak (Peters-Taylor 2017 + §11.5 zorunlu
consolidation pass).

**Bu wiki'nin 2. handoff'u.** İlk handoff (handoff.md) Cycle 11 öncesi
yazıldı, A-B-C bloğu (10 cycle) state'i içeriyor. İkinci handoff (bu
dosya) Cycle 16 öncesi, A-B-C-D-F[1] (15 cycle) state'i içeriyor.
Wiki gelişim hikayesi handoff'lar üzerinden okunabilir.
