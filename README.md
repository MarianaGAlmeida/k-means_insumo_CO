# k-means_insumo_CO

Em R: Uso do k-means como forma de agrupamento para análise das distribuidoras de acordo com a composição do insumo "custos operacionais reais".

Em Python: análise alternativa ao k-means:
```py
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import plotly.express as px

df_medias = pd.read_csv ('MEDIAS_16_18.csv', sep=';', na_values='ND')


## Adicionar coluna com a participação percentual da componente P (Pessoal) nos custos operacionais
df_medias['Part_Perc_P'] = df_medias['X18.2.Pessoal'] / df_medias['X18.1.Custos_Operacionais']
df_medias.head()


## Alternativa ao k-means : histograma com distribuidoras identificáveis
## mover mouse sobre o gráfico
grafico = px.histogram(df_medias, x="Part_Perc_P", color="EMPRESA")
grafico.show()
```
