# India-Stocks-811-840-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 811 to 840)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-811-840-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (811 to 840)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 811 | `BLUSPRING` | Bluspring Enterprises Limited | `BLUSPRING.NS` |
| 812 | `BMWVENTLTD` | BMW Ventures Limited | `BMWVENTLTD.NS` |
| 813 | `BNAGROCHEM` | BN Agrochem Limited | `BNAGROCHEM.NS` |
| 814 | `BNALTD` | B & A Limited | `BNALTD.NS` |
| 815 | `BODALCHEM` | Bodal Chemicals Limited | `BODALCHEM.NS` |
| 816 | `BOHRAIND` | Bohra Industries Limited | `BOHRAIND.NS` |
| 817 | `BOMDYEING` | Bombay Dyeing & Mfg Company Limited | `BOMDYEING.NS` |
| 818 | `BONLON` | Bonlon Industries Limited | `BONLON.NS` |
| 819 | `BORANA` | Borana Weaves Limited | `BORANA.NS` |
| 820 | `BOROLTD` | Borosil Limited | `BOROLTD.NS` |
| 821 | `BORORENEW` | BOROSIL RENEWABLES LIMITED | `BORORENEW.NS` |
| 822 | `BOROSCI` | Borosil Scientific Limited | `BOROSCI.NS` |
| 823 | `BOSCH-HCIL` | BOSCH HOME COMFORT INDIA LIMITED | `BOSCH-HCIL.NS` |
| 824 | `BPL` | BPL Limited | `BPL.NS` |
| 825 | `BPLPHARMA` | Bharat Parenterals Limited | `BPLPHARMA.NS` |
| 826 | `BRAHMINFRA` | Brahmaputra Infrastructure Limited | `BRAHMINFRA.NS` |
| 827 | `BRIGHOTEL` | Brigade Hotel Ventures Limited | `BRIGHOTEL.NS` |
| 828 | `BRIGHTBR` | Bright Brothers Limited | `BRIGHTBR.NS` |
| 829 | `BRNL` | Bharat Road Network Limited | `BRNL.NS` |
| 830 | `BROOKS` | Brooks Laboratories Limited | `BROOKS.NS` |
| 831 | `BSHSL` | Bombay Super Hybrid Seeds Limited | `BSHSL.NS` |
| 832 | `BSL` | BSL Limited | `BSL.NS` |
| 833 | `BTML` | Bodhi Tree Multimedia Limited | `BTML.NS` |
| 834 | `BTTL` | Bhilwara Technical Textiles Limited | `BTTL.NS` |
| 835 | `BUILDPRO` | Shankara Buildpro Limited | `BUILDPRO.NS` |
| 836 | `BURNPUR` | Burnpur Cement Limited | `BURNPUR.NS` |
| 837 | `BUTTERFLY` | Butterfly Gandhimathi Appliances Limited | `BUTTERFLY.NS` |
| 838 | `BVCL` | Barak Valley Cements Limited | `BVCL.NS` |
| 839 | `BYKE` | The Byke Hospitality Ltd | `BYKE.NS` |
| 840 | `CALSOFT` | California Software Company Limited | `CALSOFT.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream BLUSPRING 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-811-840-Historical-Data/main/BLUSPRING/1m/2026/10/BLUSPRING_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
