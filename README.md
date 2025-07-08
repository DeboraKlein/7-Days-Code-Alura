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

dados_emprestimos = dados_emprestimos.drop_duplicates()

dados_livros = pd.read_parquet('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_1-Importando_dados/Datasets/dados_exemplares.parquet')

dados_emprestimos_livros = dados_emprestimos.merge(dados_livros)

| Day | Theme | What I Did |
|-----|-------|------------|
| **2** | Data Transformation | Mapped CDU categories, converted user IDs, dropped irrelevant columns |

CDU_lista = []
for CDU in dados_emprestimos_livros['localizacao']:
    if CDU >= 0 and CDU <= 99:
        CDU_lista.append('Generalidades')

    elif CDU >= 100 and CDU <= 199:
        CDU_lista.append('Filosofia e psicologia')

    elif CDU >= 200 and CDU <= 299:
        CDU_lista.append('Religião')

    elif CDU >= 300 and CDU <= 399:
        CDU_lista.append('Ciências sociais')

    elif CDU >= 400 and CDU <= 499:
        CDU_lista.append('Classe vaga')

    elif CDU >= 500 and CDU <= 599:
        CDU_lista.append('Matemática e ciências naturais')

    elif CDU >= 600 and CDU <= 699:
        CDU_lista.append('Ciências aplicadas')

    elif CDU >= 700 and CDU <= 799:
        CDU_lista.append('Belas artes')

    elif CDU >= 800 and CDU <= 899:
        CDU_lista.append('Linguagem')

    elif CDU >= 900 and CDU <= 999:
        CDU_lista.append('Geografia, Biografia e História')

    else:
        CDU_lista.append('Não identificado')

dados_emprestimos_livros['CDU'] = CDU_lista

dados_emprestimos_livros = dados_emprestimos_livros.drop(columns='registro_sistema')

dados_emprestimos_livros['matricula_ou_siape'] = dados_emprestimos_livros['matricula_ou_siape'].astype(str)


| Day | Theme | What I Did |
|-----|-------|------------|
| **3** | Temporal Trends | Used `groupby()` + `Datetime` to analyze loan volume over time, plotted borrowing by year, month, and hour |

import datetime as dt
import time
import calendar
dados_emprestimos_livros['data_renovacao'] = pd.to_datetime(dados_emprestimos_livros['data_renovacao'])
dados_emprestimos_livros['data_devolucao'] = pd.to_datetime(dados_emprestimos_livros['data_devolucao'])

dados_emprestimos_livros['id_emprestimo'].value_counts()

total_emprestimos = len(dados_emprestimos_livros['id_emprestimo'].drop_duplicates())
print(total_emprestimos)

total_livros_emprestados = dados_emprestimos_livros['id_exemplar'].value_counts().sum()
print(total_livros_emprestados)

dados_emprestimos_livros['data_emprestimo'] = pd.to_datetime(dados_emprestimos_livros['data_emprestimo'])

# Extract the year from the 'data_emprestimo' column
dados_emprestimos_livros['ano'] = dados_emprestimos_livros['data_emprestimo'].dt.year

livros_emprestados_por_ano = dados_emprestimos_livros.groupby('ano').size().reset_index(name='quantidade_livros_emprestados')
livros_emprestados_por_ano.columns = ['data', 'quantidade_livros_emprestados']
livros_emprestados_por_ano = livros_emprestados_por_ano.sort_values(by='data')
print("Quantidade de livros emprestados por ano:")
display(livros_emprestados_por_ano)

import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 6))
sns.lineplot(x='data', y='quantidade_livros_emprestados', data=livros_emprestados_por_ano)
plt.title('Quantidade de Empréstimos por Ano')
plt.xlabel('Ano')
plt.ylabel('Quantidade de Empréstimos')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

emprestimos_total_por_mes = dados_emprestimos_livros.groupby('mes').size().reset_index(name='quantidade_total')

# Map month numbers to names for better readability
month_names = {
    1: 'Janeiro', 2: 'Fevereiro', 3: 'Março', 4: 'Abril', 5: 'Maio', 6: 'Junho',
    7: 'Julho', 8: 'Agosto', 9: 'Setembro', 10: 'Outubro', 11: 'Novembro', 12: 'Dezembro'
}
emprestimos_total_por_mes['mes'] = emprestimos_total_por_mes['mes'].map(month_names)

# Sort the table by total quantity for easier analysis
emprestimos_total_por_mes_sorted = emprestimos_total_por_mes.sort_values(by='quantidade_total', ascending=False)

print("Quantidade total de empréstimos por mês (2010-2020):")
display(emprestimos_total_por_mes_sorted)

ax = emprestimos_total_por_mes_sorted.plot(kind='bar', x='mes', y='quantidade_total', figsize=(10, 6), color='skyblue')
ax.set_xlabel('Mês')
ax.set_ylabel('Quantidade Total de Empréstimos')
ax.set_title('Quantidade Total de Empréstimos por Mês (2010-2020)')
plt.show()

dados_emprestimos_livros['hora_emprestimo'] = dados_emprestimos_livros['data_emprestimo'].dt.hour

# Group by hour and count the number of loans
emprestimos_por_hora = dados_emprestimos_livros.groupby('hora_emprestimo').size().reset_index(name='quantidade_emprestimos')

# Sort by hour for a chronological plot
emprestimos_por_hora = emprestimos_por_hora.sort_values(by='hora_emprestimo')

# Display the results
print("Quantidade de empréstimos por hora do dia:")
display(emprestimos_por_hora)

import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(12, 6))
sns.barplot(x='hora_emprestimo', y='quantidade_emprestimos', data=emprestimos_por_hora, palette='viridis')
plt.title('Quantidade de Empréstimos por Hora do Dia')
plt.xlabel('Hora do Dia')
plt.ylabel('Quantidade de Empréstimos')
plt.xticks(rotation=0) # Hours are discrete, no need to rotate
plt.tight_layout()
plt.show()

emprestimos_por_exemplar = dados_emprestimos_livros['id_exemplar'].value_counts().reset_index()
emprestimos_por_exemplar.columns = ['id_exemplar', 'quantidade_emprestimos']

# Sort by the number of loans in descending order
emprestimos_por_exemplar = emprestimos_por_exemplar.sort_values(by='quantidade_emprestimos', ascending=False)

# Display the top 10 most borrowed exemplars
print("Top 10 exemplares mais emprestados:")
display(emprestimos_por_exemplar.head(10))


| Day | Theme | What I Did |
|-----|-------|------------|
| **4** | Categorical Insights | Created frequency tables by User Type, Collection, Library, and CDU Category using custom functions |

dados_emprestimos_livros.tipo_vinculo_usuario.unique()

dados_emprestimos_livros.colecao.unique()

dados_emprestimos_livros.biblioteca.unique()

dados_emprestimos_livros.CDU.unique()

def tabela_frequencia(variavel):
    tabela = dados_emprestimos_livros[variavel].value_counts(normalize=True) * 100
    tabela_df = pd.DataFrame(tabela)
    tabela_df = tabela_df.reset_index()
    tabela_df.columns = [variavel, 'percentual']
    tabela_df[variavel] = tabela_df[variavel].astype(str)
    tabela_df['percentual'] = tabela_df['percentual'].map('{:.2f}%'.format)
    return tabela_df

tabela_frequencia('tipo_vinculo_usuario')
display(tabela_frequencia('tipo_vinculo_usuario'))

tabela_frequencia('colecao')
display(tabela_frequencia('colecao'))

tabela_frequencia('biblioteca')
display(tabela_frequencia('biblioteca'))

tabela_frequencia('CDU')
display(tabela_frequencia('CDU'))


| Day | Theme | What I Did |
|-----|-------|------------|
| **5** | Boxplot Analysis | Compared monthly loan distributions (2010–2020) by undergrad & postgrad students using `Seaborn` |

import seaborn as sns
import matplotlib.pyplot as plt

alunos_graduacao = dados_emprestimos_livros.query('tipo_vinculo_usuario == "ALUNO DE GRADUAÇÃO"')
alunos_graduacao.colecao.value_counts()

import pandas as pd
alunos_graduacao_acervo_circulante = alunos_graduacao.query('colecao == "Acervo Circulante"')
alunos_graduacao_acervo_circulante = pd.DataFrame(alunos_graduacao_acervo_circulante)
alunos_graduacao_acervo_circulante['data_emprestimo'] = pd.to_datetime(alunos_graduacao_acervo_circulante['data_emprestimo'])
alunos_graduacao_acervo_circulante['ano'] = alunos_graduacao_acervo_circulante['data_emprestimo'].dt.year
alunos_graduacao_acervo_circulante['mes'] = alunos_graduacao_acervo_circulante['data_emprestimo'].dt.month
alunos_graduacao_acervo_circulante = alunos_graduacao_acervo_circulante.loc[:,['ano', 'mes']]
alunos_graduacao_acervo_circulante = alunos_graduacao_acervo_circulante.value_counts().to_frame('quantidade').reset_index()
alunos_graduacao_acervo_circulante


import matplotlib.ticker as ticker
import seaborn as sns
import matplotlib.pyplot as plt

def gera_box_plot(dataset, x, y, titulo, subtitulo):

  sns.set_theme(style="darkgrid", palette="Blues", font_scale=1.3)
  plt.figure(figsize=(16, 10))

  ax = sns.boxplot(x=x, y=y, data= dataset, color='#4171EF')

  formatter = ticker.FuncFormatter(lambda x, p: "{:,.0f}".format(int(x)).replace(",", "."))
  ax.yaxis.set_major_formatter(formatter)


  plt.ylim(0, max(dataset[y])*1.1) #Definir o limite do eixo Y
  plt.xlabel(None)
  plt.ylabel(None)

  ax.set_title(titulo+"\n", size=20, loc='left', weight='bold')
  ax.text(s=subtitulo, x=-0.5, y=max(dataset[y]*1.11), fontsize=18, ha='left', color='grey')

gera_box_plot(alunos_graduacao_acervo_circulante, 'ano', 'quantidade', 'Distribuição dos empréstimos mensais', 'Realizados pelos alunos de graduação no acervo circulante')

alunos_posgraduacao = dados_emprestimos_livros[dados_emprestimos_livros['tipo_vinculo_usuario'] == 'ALUNO DE PÓS-GRADUAÇÃO']
alunos_posgraduacao.colecao.value_counts()

import pandas as pd
alunos_posgraduacao_acervo_circulante = alunos_posgraduacao.query('colecao == "Acervo Circulante"')
alunos_posgraduacao_acervo_circulante = pd.DataFrame(alunos_posgraduacao_acervo_circulante)
alunos_posgraduacao_acervo_circulante['data_emprestimo'] = pd.to_datetime(alunos_posgraduacao_acervo_circulante['data_emprestimo'])
alunos_posgraduacao_acervo_circulante['ano'] = alunos_posgraduacao_acervo_circulante['data_emprestimo'].dt.year
alunos_posgraduacao_acervo_circulante['mes'] = alunos_posgraduacao_acervo_circulante['data_emprestimo'].dt.month
alunos_posgraduacao_acervo_circulante = alunos_posgraduacao_acervo_circulante.loc[:,['ano', 'mes']]
alunos_posgraduacao_acervo_circulante = alunos_posgraduacao_acervo_circulante.value_counts().to_frame('quantidade').reset_index()
alunos_posgraduacao_acervo_circulante

import matplotlib.ticker as ticker
import seaborn as sns
import matplotlib.pyplot as plt

def gera_box_plot(dataset, x, y, titulo, subtitulo):

  sns.set_theme(style="darkgrid", palette="Blues", font_scale=1.3)
  plt.figure(figsize=(16, 10))

  ax = sns.boxplot(x=x, y=y, data= dataset, color='#4171EF')

  # Custom formatter to use a period as the thousands separator
  formatter = ticker.FuncFormatter(lambda x, p: "{:,.0f}".format(int(x)).replace(",", "."))
  ax.yaxis.set_major_formatter(formatter)


  plt.ylim(0, max(dataset[y])*1.1) #Definir o limite do eixo Y
  plt.xlabel(None)
  plt.ylabel(None)

  ax.set_title(titulo+"\n", size=20, loc='left', weight='bold')
  ax.text(s=subtitulo, x=-0.5, y=max(dataset[y]*1.11), fontsize=18, ha='left', color='grey')

gera_box_plot(alunos_posgraduacao_acervo_circulante, 'ano', 'quantidade', 'Distribuição dos empréstimos mensais', 'Realizados pelos alunos de pós-graduação no acervo circulante')


| Day | Theme | What I Did |
|-----|-------|------------|
| **6** | Course-Based Loan Metrics | Merged Excel & JSON data sources, created pivot tables for loan activity across 6 degree programs |

cadastro_usuarios_antes_2010 = pd.read_excel('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/matricula_alunos.xlsx',
                                        sheet_name='Até 2010',skiprows=1)
cadastro_usuarios_depois_2010 = pd.read_excel('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/matricula_alunos.xlsx',
                                        sheet_name='Após 2010',skiprows=1)

cadastro_usuarios_antes_2010.columns = ['matricula_ou_siape', 'tipo_vinculo_usuario', 'curso']
display(cadastro_usuarios_antes_2010.head())

cadastro_usuarios_depois_2010.head()

cadastro_usuarios_depois_2010.head()

cadastro_usuarios_depois_2010.columns = ['matricula_ou_siape', 'tipo_vinculo_usuario', 'curso']
display(cadastro_usuarios_depois_2010.head())

cadastro_usuarios_excel = pd.concat([cadastro_usuarios_antes_2010, cadastro_usuarios_depois_2010], ignore_index=True)
cadastro_usuarios_excel.matricula_ou_siape = cadastro_usuarios_excel.matricula_ou_siape.astype(str)
cadastro_usuarios_excel.head()

cadastro_usuarios_json = pd.read_json('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/cadastro_alunos.json')
cadastro_usuarios_json

cadastro_usuarios_json = pd.read_json(cadastro_usuarios_json.registros[0])
cadastro_usuarios_json.head()

cadastro_usuarios_json.info()

cadastro_usuarios_json.matricula_ou_siape = cadastro_usuarios_json.matricula_ou_siape.astype(str)

cadastro_usuarios_cursos = pd.concat([cadastro_usuarios_excel,cadastro_usuarios_json],ignore_index=True)
cadastro_usuarios_cursos

matricula_data_de_emprestimo = dados_emprestimos_livros.query("tipo_vinculo_usuario == 'ALUNO DE GRADUAÇÃO'")
matricula_data_de_emprestimo = matricula_data_de_emprestimo.loc[:,['matricula_ou_siape','data_emprestimo']]
matricula_data_de_emprestimo = matricula_data_de_emprestimo.query('data_emprestimo > 2015')
matricula_data_de_emprestimo = matricula_data_de_emprestimo.reset_index(drop=True)
matricula_data_de_emprestimo

matricula_data_de_emprestimo.isna().sum()

cadastro_usuarios_cursos_selecionados = cadastro_usuarios_cursos.query("curso == ['BIBLIOTECONOMIA','CIÊNCIAS SOCIAIS','COMUNICAÇÃO SOCIAL','DIREITO','FILOSOFIA','PEDAGOGIA']")
cadastro_usuarios_cursos_selecionados

cadastro_usuarios_cursos_selecionados = matricula_data_de_emprestimo.merge(cadastro_usuarios_cursos_selecionados)
cadastro_usuarios_cursos_selecionados

cadastro_usuarios_cursos_selecionados.data_emprestimo = cadastro_usuarios_cursos_selecionados.data_emprestimo.dt.year

emprestimos_cursos_selecionados = cadastro_usuarios_cursos_selecionados.iloc[:,[1,3]].value_counts().reset_index()
emprestimos_cursos_selecionados.columns = ['ANO','CURSO','QUANTIDADE_EMPRESTIMOS']
emprestimos_cursos_selecionados


emprestimos_tipo_usuario_curso_pivot = emprestimos_cursos_selecionados.pivot_table(
        index = 'CURSO',
        columns = 'ANO',
        values = 'QUANTIDADE_EMPRESTIMOS',
        fill_value = '-',
        aggfunc= sum,
        margins = True,
        margins_name = 'TOTAL',
)
emprestimos_tipo_usuario_curso_pivot


| Day | Theme | What I Did |
|-----|-------|------------|
| **7** | Percentage Change + HTML Export | Calculated year-over-year percentage change per course, exported styled HTML table with custom CSS 💅 |

cadastro_usuarios_antes_2010 = pd.read_excel('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/matricula_alunos.xlsx',
                                        sheet_name='Até 2010',skiprows=1)
cadastro_usuarios_depois_2010 = pd.read_excel('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/matricula_alunos.xlsx',
                                        sheet_name='Após 2010',skiprows=1)

cadastro_usuarios_antes_2010.columns = ['matricula_ou_siape','tipo_vinculo_usuario','curso']

cadastro_usuarios_depois_2010

cadastro_usuarios_excel = pd.concat([cadastro_usuarios_antes_2010,cadastro_usuarios_depois_2010],ignore_index=True)
cadastro_usuarios_excel.matricula_ou_siape = cadastro_usuarios_excel.matricula_ou_siape.astype('string')
cadastro_usuarios_excel

cadastro_usuarios_json = pd.read_json('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_6-Novos_dados_novas_analises/Datasets/cadastro_alunos.json')
cadastro_usuarios_json

cadastro_usuarios_posgraduacao_json = pd.read_json(cadastro_usuarios_json.registros[1])

cadastro_usuarios_posgraduacao_json

cadastro_usuarios_posgraduacao_json.info()

cadastro_usuarios_posgraduacao_json.matricula_ou_siape = cadastro_usuarios_posgraduacao_json.matricula_ou_siape.astype('float')
cadastro_usuarios_posgraduacao_json.matricula_ou_siape = cadastro_usuarios_posgraduacao_json.matricula_ou_siape.astype('string')

cadastro_usuarios_cursos = pd.concat([cadastro_usuarios_excel,cadastro_usuarios_posgraduacao_json],ignore_index=True)
cadastro_usuarios_cursos

cadastro_usuarios_cursos_pos_graduacao = cadastro_usuarios_posgraduacao_json.query("tipo_vinculo_usuario == 'ALUNO DE PÓS-GRADUAÇÃO'")
cadastro_usuarios_cursos_pos_graduacao

matricula_data_de_emprestimo_pos_graduacao = dados_emprestimos_livros.loc[:,['matricula_ou_siape','data_emprestimo']]
matricula_data_de_emprestimo_pos_graduacao = matricula_data_de_emprestimo_pos_graduacao.query('data_emprestimo > 2017')
matricula_data_de_emprestimo_pos_graduacao = matricula_data_de_emprestimo_pos_graduacao.reset_index(drop=True)
matricula_data_de_emprestimo_pos_graduacao

emprestimos_pos_graduacao_desde_2017 = matricula_data_de_emprestimo_pos_graduacao.merge(cadastro_usuarios_cursos_pos_graduacao)
emprestimos_pos_graduacao_desde_2017

emprestimos_pos_graduacao_desde_2017.data_emprestimo = emprestimos_pos_graduacao_desde_2017.data_emprestimo.dt.year

emprestimos_pos_graduacao_desde_2017 = emprestimos_pos_graduacao_desde_2017.iloc[:,[1,3]].value_counts().reset_index()
emprestimos_pos_graduacao_desde_2017.columns = ['ANO','CURSO','QUANTIDADE_EMPRESTIMOS']
emprestimos_pos_graduacao_desde_2017.head()

emprestimos_pos_graduacao_e_curso_pivot = emprestimos_pos_graduacao_desde_2017.pivot_table(
        index = 'CURSO',
        columns = 'ANO',
        values = 'QUANTIDADE_EMPRESTIMOS'
)
emprestimos_pos_graduacao_e_curso_pivot

previsao_2022 = pd.read_table('https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/raw/main/Dia_7-Apresentando_resultados_em_HTML/Dataset/previsao')

previsao_2022 = previsao_2022['curso previsao_2022'].str.split(' ',expand=True)
previsao_2022

emprestimos_pos_graduacao_e_curso_pivot

previsao_2022.index = emprestimos_pos_graduacao_e_curso_pivot.index
emprestimos_pos_graduacao_e_curso_pivot['2022'] = previsao_2022.iloc[:,1]
emprestimos_pos_graduacao_e_curso_pivot

emprestimos_pos_graduacao_e_curso_pivot['2022'] = emprestimos_pos_graduacao_e_curso_pivot['2022'].astype('int')

emprestimos_pos_graduacao_e_curso_pivot

def diferenca_percentual_ano_anterior(x,y):
  return round(((x / y * 100) - 100),2)

percentual_2018 = diferenca_percentual_ano_anterior(emprestimos_pos_graduacao_e_curso_pivot.iloc[:,1],emprestimos_pos_graduacao_e_curso_pivot.iloc[:,0])
percentual_2019 = diferenca_percentual_ano_anterior(emprestimos_pos_graduacao_e_curso_pivot.iloc[:,2],emprestimos_pos_graduacao_e_curso_pivot.iloc[:,1])
percentual_2022 = diferenca_percentual_ano_anterior(emprestimos_pos_graduacao_e_curso_pivot.iloc[:,3],emprestimos_pos_graduacao_e_curso_pivot.iloc[:,2])

percentual = pd.DataFrame({'2018':percentual_2018,
                           '2019':percentual_2019,
                           '2022':percentual_2022})
percentual

percentual.reset_index(inplace=True)
percentual.columns = percentual.columns.str.capitalize()
percentual.Curso = percentual.Curso.str.capitalize()

percentual

th_props = [
  ('font-size', '1.4rem'),
  ('text-align', 'center'),
  ('font-weight', 'bold'),
  ('color', 'whitesmoke'),
  ('background-color', '#001692'),
  ('border-radius', '0.25rem'),
  ('box-shadow','0 0 1rem gray')
  ]

td_props = [
  ('font-size', '1rem'),
  ('padding','0.5rem'),
  ('text-align', 'left'),
  ('font-weight', 'bold'),
  ('border-bottom','0.1rem solid lightgray')
  ]

styles = [
  dict(selector="th", props=th_props),
  dict(selector="td", props=td_props)
  ]

percentual.style.text_gradient(cmap='RdYlGn',low=1, axis=1,vmax=0.1,vmin=0)\
                              .format('{:.2f} %',subset=['2018','2019','2022'])\
                              .hide(axis="index")\
                              .set_table_styles(styles)\
                            #  .to_html('teste.html',doctype_html =True,
                            #           table_attributes='ALIGN=LEFT WIDTH=50% CELLSPACING = 5')

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


