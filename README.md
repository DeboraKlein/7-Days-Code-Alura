# 📚 7 Days of Code: Python + Pandas | UFRN Library Data Exploration

Welcome! This repository documents my learning journey through the **#7DaysOfCode** challenge by [Alura](https://7daysofcode.io/) — focused on mastering **Python** and **Pandas** using a real dataset from the university library system at **UFRN (Universidade Federal do Rio Grande do Norte)**.

Each day focused on a different step of the data workflow, from collection and cleaning, to visualization and insights that could help guide decision-making in a real institutional setting.

---

## 🚀 Overview

| Day | Theme | What I Did |
|-----|-------|------------|
| **1** | Unifying & Cleaning Raw Data | Imported data from GitHub (CSV & Parquet), merged datasets using `merge()`, dropped duplicates/nulls |

import pandas as pd

dados_2010_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20101.csv?raw=true')
dados_2010_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20102.csv?raw=true')
dados_2011_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20111.csv?raw=true')
dados_2011_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20112.csv?raw=true')
dados_2012_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20121.csv?raw=true')
dados_2012_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20122.csv?raw=true')
dados_2013_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20131.csv?raw=true')
dados_2013_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20132.csv?raw=true')
dados_2014_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20141.csv?raw=true')
dados_2014_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20142.csv?raw=true')
dados_2015_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20151.csv?raw=true')
dados_2015_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20152.csv?raw=true')
dados_2016_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20161.csv?raw=true')
dados_2016_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20162.csv?raw=true')
dados_2017_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20171.csv?raw=true')
dados_2017_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20172.csv?raw=true')
dados_2018_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20181.csv?raw=true')
dados_2018_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20182.csv?raw=true')
dados_2019_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20191.csv?raw=true')
dados_2019_2 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20192.csv?raw=true')
dados_2020_1 = pd.read_csv('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/blob/main/Dia_1-Importando_dados/Datasets/dados_emprestimos/emprestimos-20201.csv?raw=true')

dados_emprestimos = pd.concat([dados_2010_1, dados_2010_2, dados_2011_1, dados_2011_2, dados_2012_1, dados_2012_2, dados_2013_1, dados_2013_2, dados_2014_1, dados_2014_2,
                               dados_2015_1, dados_2015_2, dados_2016_1, dados_2016_2, dados_2017_1, dados_2017_2, dados_2018_1, dados_2018_2, dados_2019_1, dados_2019_2,
                               dados_2020_1], ignore_index=True)

| **2** | Data Transformation | Mapped CDU categories, converted user IDs, dropped irrelevant columns |
| **3** | Temporal Trends | Used `groupby()` + `Datetime` to analyze loan volume over time, plotted borrowing by year, month, and hour |
| **4** | Categorical Insights | Created frequency tables by User Type, Collection, Library, and CDU Category using custom functions |
| **5** | Boxplot Analysis | Compared monthly loan distributions (2010–2020) by undergrad & postgrad students using `Seaborn` |
| **6** | Course-Based Loan Metrics | Merged Excel & JSON data sources, created pivot tables for loan activity across 6 degree programs |
| **7** | Percentage Change + HTML Export | Calculated year-over-year percentage change per course, exported styled HTML table with custom CSS 💅 |

---

## 📊 Skills Practiced

- Python 🐍
- Pandas Data Manipulation
- Data Cleaning & Preparation
- Datetime Formatting & Time Series
- Exploratory Data Analysis (EDA)
- Data Visualization with `Seaborn`, `Matplotlib`, and `Plotly`
- HTML export with Pandas’ `.to_html()`
- Conditional formatting & custom CSS styling
- JSON and Excel data parsing

---

## 💡 Reflections

This project helped me reinforce core concepts of Python and Pandas through a real-world context. It wasn't just technical — I practiced translating raw data into strategic, actionable stories that could help guide decision-making within academic institutions.

It also reminded me how important it is to **ask the right questions** before jumping into analysis. From user behaviors to collection trends and institutional KPIs, data becomes powerful when it’s connected to its purpose. 💙

---


