# 📊 Mini projekt - ještě na tom pracuji 
[🔗 Kaggle Dataset - edX Course Study](https://www.kaggle.com/datasets/edx/course-study)

## Jaká to jsou data? 🧐  

V roce **2012** spustily **Massachusettský technologický institut (MIT)** a **Harvardova univerzita** neziskovou vzdělávací platformu **edX**, která nabízí **otevřené online kurzy**. 🌐  

O čtyři roky později tato zpráva shrnuje:  
- **290 online kurzů** Harvardu a MIT 🎓  
- **250 tisíc udělených certifikátů** 🏅  
- **4,5 milionu účastníků** 👨‍🎓👩‍🎓  
- **28 milionů hodin** strávených na platformě edX ⏱️  

Data zachycují globální komunitu studentů a jejich zapojení do online vzdělávání prostřednictvím platformy edX od jejího spuštění. 🌍  

## Co si na projektu procvičím? 🛠️📚💡

- zpracování dat v **Python** 📊
- tvorba vizualizace v **Matplolib** 📈
- git 🖇️💾

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
```
---

## Jaký je podíl kurzů nabízených institucemi MITx 🎓 a HarvardX 🎓 na platformě edX 🌐?
---
```python
import matplotlib.pyplot as plt
import pandas as pd

# Načtení dat z tabulky "kurzy_cleaned.csv"
data = pd.read_csv("kurzy_cleaned.csv")

# Data pro pie chart
institutions = ["MITx", "HarvardX"]
courses_offered = [
    data[data["Institution"] == institution].shape[0] 
    for institution in institutions
]
colors = ['#e8bfb5', '#F2766B']  # Barvy

# Vytvoření pie chartu
plt.figure(figsize=(8, 8))
plt.pie(
    courses_offered,
    labels=institutions,
    autopct='%1.1f%%',
    startangle=140,
    colors=colors,
    textprops={'fontsize': 18, 'fontweight': 'bold', 'color': 'black'}
)

# Nastavení nadpisu
plt.title("Proportion of Courses Offered by Institutions", fontsize=24, fontweight='bold', pad=10)

# Zajištění kruhového tvaru
plt.axis('equal')

# Zobrazení grafu
plt.show()import matplotlib.pyplot as plt
import pandas as pd

# Načtení dat z tabulky "kurzy_cleaned.csv"
data = pd.read_csv("kurzy_cleaned.csv")

# Data pro pie chart
institutions = ["MITx", "HarvardX"]
courses_offered = [
    data[data["Institution"] == institution].shape[0] 
    for institution in institutions
]
colors = ['#e8bfb5', '#F2766B']  # Barvy

# Vytvoření pie chartu
plt.figure(figsize=(8, 8))
plt.pie(
    courses_offered,
    labels=institutions,
    autopct='%1.1f%%',
    startangle=140,
    colors=colors,
    textprops={'fontsize': 18, 'fontweight': 'bold', 'color': 'black'}
)

# Nastavení nadpisu
plt.title("Proportion of Courses Offered by Institutions", fontsize=24, fontweight='bold', pad=10)

# Zajištění kruhového tvaru
plt.axis('equal')

# Zobrazení grafu
plt.show()
```
---

