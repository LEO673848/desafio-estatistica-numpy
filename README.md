# Desafio Estatística com NumPy
 
## Objetivo
Calcular o desvio padrão amostral de um conjunto de dados utilizando NumPy e visualizar os resultados em um histograma com a faixa correspondente a média ± desvio padrão.
 
## Código
 
```python
import numpy as np
import matplotlib.pyplot as plt
 
dados = [5, 6, 6, 7, 7, 7, 8, 8, 9, 10]
 
media = np.mean(dados)
desvio_padrao = np.std(dados, ddof=1)
 
intervalo_min = media - desvio_padrao
intervalo_max = media + desvio_padrao
 
print(f"Média: {media:.2f}")
print(f"Desvio padrão amostral: {desvio_padrao:.2f}")
print(f"Intervalo: [{intervalo_min:.2f}, {intervalo_max:.2f}]")
 
plt.hist(dados, bins=6, edgecolor='black')
 
plt.axvspan(
intervalo_min,
intervalo_max,
color='orange',
alpha=0.3,
label='Média ± Desvio Padrão'
)
 
plt.axvline(media, color='red', linestyle='--', label='Média')
 
plt.title('Histograma dos Dados')
plt.xlabel('Valores')
plt.ylabel('Frequência')
plt.legend()
plt.show()
