import pandas as pd

# 1.0 Carregar dados do CSV - Caminho do arquivo csv/ encoding do windows/ ; que será separado para melhor leitura do csv

df = pd.read_csv("C:/Users/nicol/OneDrive/Desktop/TABELA_BRASILEIRAO_SA.csv", encoding='ISO-8859-1', sep=';')
print(df.columns)
print(df.head())
print(df)

# 1.1 Definir nome das colunas
df.columns = ['Classificação', 'Time', 'P', 'J', 'V', 'E', 'D', 'GP', 'GC', 'SG', '%']

# 2.0 Criando um dataframe
data_times = {
    'Classificação': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20],
    'Time': ['Botafogo', 'Palmeiras', 'Fortaleza', 'Flamengo', 'São Paulo', 'Bahia', 'Cruzeiro', 'Internacional', 'Atlético=MG', 'Vasco', 'Juventude', 'Grêmio', 'Athletico-PR', 'Bragantino', 'Criciúma', 'Vitória', 'Corinthians', 'Fluminense', 'Cuiabá', 'Atlético-GO'],
    'P': [56, 53,52,45,44, 42, 42, 41, 36, 35, 32, 31, 31, 31, 29, 28, 28, 27, 23, 18],
    'J': [27, 27, 27, 26, 27, 27, 27, 25, 25, 26, 27, 25, 25, 26, 26, 27, 27, 26, 26, 27],
    'V': [17, 16, 15, 13, 13, 12, 12, 11, 9, 10, 8, 9, 8, 8, 7, 8, 6, 7, 5, 4],
    'E': [5, 5, 7, 6, 5, 6, 6, 8, 9, 5, 8, 4, 7, 7, 8, 4, 10, 6, 8, 6],
    'D': [5, 6, 5, 7, 9, 9, 9, 6, 7, 11, 11, 12, 10, 11, 11, 15, 11, 13, 13, 17],
    'GP': [46, 44, 36, 42, 35, 38, 34, 30, 35, 30, 31, 28, 27, 31, 32, 29, 26, 21, 23, 21],
    'GC': [25, 19, 26, 32, 29, 31, 27, 21, 36, 36, 37, 32, 29, 35, 40, 39, 33, 29, 38, 45],
    'SG': [21, 25, 10, 10, 6, 7, 7, 9, -1, -6, -6, -4, -2, -4, -8, -10, -7, -8, -15, -24],
    '%': [69, 65, 64, 57, 54, 51, 51, 54, 48, 44, 39, 41, 41, 39, 37, 34, 34, 34, 29, 22]
}

df = pd.DataFrame(data_times)

# 3.0 Adicionando colunas para calcular a quantidade de jogos que restam
df['Jogos Restantes'] = 38 - df['J']

#3.1 Imprimindo a quantidade de jogos que restam
for index, row in df.iterrows():
    print(f'Time: {row["Time"]} - Tem {row["J"]} jogos jogados e faltam {row["Jogos Restantes"]} para a rodada acabar')
    
# 3.2 Imprimindo a quantidade de pontos que cada time precisa para se manter na série A 
df['Pontos Restantes'] = 45 - df['P']
df['Pontos mínimos'] = 45


for index, row in df.iterrows():
    if row['P'] >= 45:
        print(f'O time {row["Time"]} atingiu os pontos mínimos que são {row["Pontos mínimos"]} e se mantém na série A')
    else:
        print(f'O time {row["Time"]} não atingiu os {row["Pontos mínimos"]} pontos para se manter na série A ainda e precisam de {row["Pontos Restantes"]}')

# 3.3 Calculando quanto falta para cada time ser campeão do campeonato

df['Meta Pontos'] = 75
df['C_Meta Pontos'] = 75 - df['P']

for index, row in df.iterrows():
    print(f'O Time {row["Time"]} tem {row["P"]} pontos e precisa de {row["C_Meta Pontos"]} pontos para atingir a meta de campeão que é {row["Meta Pontos"]}')


df.to_csv('Projeto_DA_Brasileirão.csv', index=False, encoding='utf-8')
