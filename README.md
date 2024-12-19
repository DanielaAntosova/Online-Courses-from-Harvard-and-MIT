# 📊 Mini projekt 
[🔗 Kaggle Dataset - edX Course Study](https://www.kaggle.com/datasets/edx/course-study)

## Jaká to jsou data? 🧐  

V roce **2012** spustily **Massachusettský technologický institut (MIT)** a **Harvardova univerzita** neziskovou vzdělávací platformu **edX**, která nabízí **otevřené online kurzy**. 🌐  

O čtyři roky později tato zpráva shrnuje:  
- **290 online kurzů** Harvardu a MIT 🎓  
- **250 tisíc udělených certifikátů** 🏅  
- **4,5 milionu účastníků** 👨‍🎓👩‍🎓  
- **28 milionů hodin** strávených na platformě edX ⏱️  

Data zachycují globální komunitu studentů a jejich zapojení do online vzdělávání prostřednictvím platformy edX od jejího spuštění. 🌍  

## 🧹 Čištění dat pro Tableau
---
```python
# Import knihovny
import pandas as pd

# Načtení dat ze souboru
kurzy = pd.read_csv("appendix.csv")

# Zobrazení informací o datasetu
kurzy.info()

# Převod názvů sloupců: mezery -> podtržítka
kurzy.columns = kurzy.columns.str.replace(' ', '_')

# Výpis sloupců pro kontrolu
print(kurzy.columns)

# Uložení vyčištěného souboru
kurzy.to_csv("kurzy_cleaned.csv", index=False)
