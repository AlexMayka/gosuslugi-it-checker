<div align="center">

# 🏛 Gosuslugi IT Checker

**Automated bulk verification of IT accreditation status for Russian companies**

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)](https://selenium.dev)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)

<br>

<table>
<tr>
<td align="center"><h3>🏢 Bulk check</h3><sub>hundreds of companies</sub></td>
<td align="center"><h3>🤖 Automated</h3><sub>no manual work</sub></td>
<td align="center"><h3>📄 CSV export</h3><sub>ready for analysis</sub></td>
<td align="center"><h3>📋 Logged</h3><sub>full execution trace</sub></td>
</tr>
</table>

</div>

---

## 💡 What It Does

Checks whether companies have **active IT accreditation** on the [Gosuslugi portal](https://www.gosuslugi.ru/itorgs) — in bulk, automatically.

**The problem:** Manually checking hundreds of companies one-by-one on the Gosuslugi website is tedious. HTTP-based scraping gets rate-limited and blocked quickly.

**The solution:** Selenium-driven browser automation that mimics real user behavior — processes a full list of INN numbers and exports results to CSV.

---

## 🔄 How It Works

```
CSV with INN numbers
        ↓
   Selenium opens Gosuslugi
        ↓
   For each INN:
   ├── Enter INN in search field
   ├── Read accreditation result
   ├── Save to DataFrame
   └── Clear field, next INN
        ↓
   Export to CSV:
   (INN, Company Name, Accreditation Status)
```

### Input

CSV file with **INN numbers** (company tax identification numbers)

### Output

CSV with three columns:
| Column | Description |
|--------|-------------|
| `inn` | Company tax ID |
| `name_of_company` | Official company name |
| `IT_accreditation` | Accreditation status |

---

## 🛠 Tech Stack

| | Technology | Purpose |
|-|------------|---------|
| 🐍 | **Python** | Core language |
| 🌐 | **Selenium** | Browser automation |
| 📊 | **Pandas + NumPy** | Data processing |
| 📝 | **Logging** | Execution tracking |

---

## 🚀 Quick Start

```bash
git clone https://github.com/AlexMayka/gosuslugi-it-checker.git
cd gosuslugi-it-checker
pip install selenium pandas numpy
python main.py
```

> Requires ChromeDriver matching your Chrome version in `Drivers/`

---

## 📁 Structure

```
├── main.py                   # Main script
├── inn_org/inn_org.csv       # Input: INN numbers
├── Result_work_selenium.csv  # Output: results
├── Drivers/                  # ChromeDriver binaries
└── img/                      # Screenshots & demo GIF
```

## License

MIT
