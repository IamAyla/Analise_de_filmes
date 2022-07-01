#Importando os dados...
import pandas as pd

notas = pd.read_csv('ratings.csv')

#Colocando o nome das notas em português
notas.columns =( 'usuarioID', 'filmeID', 'nota', 'momento')

#Verificando a média e mediana
print('Media',notas.nota.mean())
print('Mediana',notas.nota.median())

#Verificando a distribuição das votações em geral
notas.nota.plot(kind='hist')

# Verificando onde se concentram o maior número de notas (quartis)
import seaborn as sns
sns.boxplot(notas.nota)

#Identificando o nome dos filmes e mudando colunas para português
filmes = pd.read_csv('movies.csv')
filmes.columns = ['filmesID','titulo','generos' ]


#Aprofundando a análise - Notas por filme (5 primeiros)
medias_por_filme = notas.groupby("filmeID").mean()["nota"]
medias_por_filme.head()

import matplotlib.pyplot as plt
plt.hist(medias_por_filme)
plt.title('Histogrma das médias dos filmes')

#Verificando os quartis 
import matplotlib.pyplot as plt

plt.figure(figsize=(5,8))
sns.boxplot(y=medias_por_filme)

# Comparando os 5...
sns.boxplot(x = 'filmeID', y = 'nota', data = notas.query('filmeID in [1,2,3,4,5]'))
