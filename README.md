# AlgorithmAnalysis
Análise de Algoritmos | Fatec Rubens Lara
- Algoritmo.mês.dia.ipynb

```{Python}
referencia = input('O que Gostaria de Procurar? ')
idx_ref = df.index[df['Modelo'] == referencia].tolist()[0] # Index da Referencia

resultados = []
for i in range(1, len(df)):
    index = similarity_scores[i][0]
    title = df['Modelo'].iloc[index]
    cosine_sim = similarity_scores[i][1]
    angle_in_degrees = (math.acos(cosine_sim) * 180) / np.pi
    resultados.append([i, title, cosine_sim, angle_in_degrees])

colunas = ['Rank', 'Modelo', 'Similaridade Cosseno', 'Ângulo em graus']
df_resultados = pd.DataFrame(resultados, columns=colunas)

display(df_resultados)
``` 
