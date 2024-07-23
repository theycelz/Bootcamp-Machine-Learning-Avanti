### 1. Escreva uma função que receba uma lista de números e retorne outra lista com os números ímpares.
```python
def numeros_impares(lista):
    return [num for num in lista if num % 2 != 0]

```

### 2. Escreva uma função que receba uma lista de números e retorne outra lista com os números primos presentes.
```python
def eh_primo(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def filtra_primos(lista):
    return [num for num in lista if eh_primo(num)]
```

### 3. Escreva uma função que receba duas listas e retorne outra lista com os elementos que estão presentes em apenas uma das listas.
```python
def diferenca_simetrica(lista1, lista2):
    conjunto1 = set(lista1)
    conjunto2 = set(lista2)
    diferenca = conjunto1.symmetric_difference(conjunto2)
    return list(diferenca)
```
### 4. Dada uma lista de números inteiros, escreva uma função para encontrar o segundo maior valor na lista.
```python
def segundo_maior(lista):
    if len(lista) < 2:
        raise ValueError("A lista deve conter pelo menos dois elementos.")

    primeiro_maior = segundo_maior = float('-inf')
    
    for num in lista:
        if num > primeiro_maior:
            segundo_maior = primeiro_maior
            primeiro_maior = num
        elif primeiro_maior > num > segundo_maior:
            segundo_maior = num

    if segundo_maior == float('-inf'):
        raise ValueError("Todos os elementos da lista são iguais.")

    return segundo_maior
```

### 5. Crie uma função que receba uma lista de tuplas, cada uma contendo o nome e a idade de uma pessoa, e retorne a lista ordenada pelo nome das pessoas em ordem alfabética.
```python
def ordenar_por_nome(lista_de_pessoas):
    return sorted(lista_de_pessoas, key=lambda pessoa: pessoa[0])
```

### 6. Observe os espaços sublinhados e complete o código.
```python
import matplotlib.pyplot as plt
import numpy as np

fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5), layout="constrained")

for row in range(2):
    for col in range(2):
        axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5),
                              transform=axs[row, col].transAxes,
                              ha='center', va='center', fontsize=18,
                              color='darkgrey')
fig.suptitle('plt.subplots()')

```

### 7. Observe os espaços sublinhados e complete o código.
```python
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt
x = np.linspace(-2 * np.pi, 2 * np.pi, 100)
y = np.sin(x)
fig, ax = plt.subplots()
ax.plot(x, y)
plt.show()
```

### 8. Utilizando pandas, como realizar a leitura de um arquivo CSV em um DataFrame e exibir as primeiras linhas?
```python
import pandas as pd

df = pd.read_csv('arquivo.csv')
print(df.head())
```

### 9. Utilizando pandas, como selecionar uma coluna específica e filtrar linhas em um DataFrame com base em uma condição?
```python
import pandas as pd

df = pd.read_csv('caminho/para/o/arquivo.csv')
coluna = df['coluna_exemplo']
filtro = df['coluna_exemplo'] > 10
df_filtrado = df[filtro]

print(df_filtrado)

```

### 10. Utilizando pandas, como lidar com valores ausentes (NaN) em um DataFrame?
```python
import pandas as pd
import numpy as np

# Criar um DataFrame de exemplo com valores ausentes
data = {
    'Nome': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Idade': [24, np.nan, 30, np.nan, 22],
    'Cidade': ['Nova York', 'Los Angeles', np.nan, 'Chicago', 'Miami']
}

df = pd.DataFrame(data)

print("DataFrame original:")
print(df)

# 1. Verificando valores ausentes no DataFrame
print("\nVerificando valores ausentes:")
print(df.isna())

# 2. Contando total de valores ausentes por coluna
print("\nTotal de valores ausentes por coluna:")
print(df.isna().sum())

# 3. Removendo linhas com valores ausentes
df_removed = df.dropna()
print("\nDataFrame após remover linhas com NaN:")
print(df_removed)

# 4. Preenchendo valores ausentes com um valor específico
df_filled = df.fillna(value={'Idade': df['Idade'].mean(), 'Cidade': 'Desconhecida'})
print("\nDataFrame após preencher NaN com média da Idade e 'Desconhecida' para Cidade:")
print(df_filled)

# 5. Preenchendo valores ausentes usando o método 'ffill' (preenchimento para frente)
df_ffill = df.fillna(method='ffill')
print("\nDataFrame após preencher NaN usando o método 'ffill':")
print(df_ffill)

# 6. Preenchendo valores ausentes usando o método 'bfill' (preenchimento para trás)
df_bfill = df.fillna(method='bfill')
print("\nDataFrame após preencher NaN usando o método 'bfill':")
print(df_bfill)

```
