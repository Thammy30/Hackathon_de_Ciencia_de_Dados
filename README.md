# 📊 Hackathon de Ciência de Dados — Análise Eleitoral de 1936

Projeto desenvolvido para o **Hackathon de Ciência de Dados**, utilizando Python e técnicas de tratamento, análise e modelagem de dados para investigar os resultados da pesquisa eleitoral da **Literary Digest** nas eleições presidenciais dos Estados Unidos de 1936.

O projeto busca demonstrar como o tratamento estatístico de uma amostra pode ajudar a identificar e corrigir distorções presentes nos dados.

---

## 🎯 Objetivo do Projeto

O objetivo deste projeto é analisar os dados da pesquisa realizada pela **Literary Digest em 1936**, identificando problemas de estrutura e possíveis vieses na amostra.

A partir do tratamento dos dados, são aplicadas técnicas de **pós-estratificação, calibração estatística e regressão linear**, permitindo comparar:

* 📋 A pesquisa original da Literary Digest;
* ⚖️ Os resultados após a calibração estatística;
* 🗳️ O resultado oficial da eleição de 1936.

---

## 🗂️ Dataset

O projeto utiliza o arquivo:

```text
LitDigestFull.csv
```

Os dados contêm informações relacionadas aos estados norte-americanos, votos eleitorais e resultados da pesquisa envolvendo:

* Alf Landon (Republicano);
* Franklin D. Roosevelt (Democrata);
* Votos do Colégio Eleitoral;
* Informações históricas utilizadas na análise.

Durante o projeto, o dataset original passa por diversas etapas de tratamento até chegar à versão:

```text
dataset_1936_saneado.csv
```

---

## 🛠️ Tecnologias Utilizadas

* 🐍 **Python**
* 🐼 **Pandas**
* 🔢 **NumPy**
* 🤖 **Scikit-Learn**
* 📈 **Matplotlib**
* 📊 **Seaborn**
* ☁️ **Google Colab**
* 📓 **Jupyter Notebook**

---

## 🔎 Etapas do Projeto

### 1. Carregamento dos dados

O arquivo CSV é carregado utilizando o **Pandas**, com validação inicial da quantidade de linhas e colunas.

```python
df = pd.read_csv('LitDigestFull.csv', sep=';', encoding='utf-8')
```

---

### 2. Tratamento e saneamento dos dados

O dataset original apresenta problemas de estrutura e alinhamento.

Foi realizado:

* Correção do separador do CSV;
* Correção do desalinhamento entre colunas;
* Padronização dos nomes das colunas;
* Remoção de colunas vazias;
* Remoção de cabeçalhos duplicados;
* Tratamento de valores ausentes;
* Conversão de valores para formato numérico.

A base tratada é salva como:

```text
dataset_1936_saneado.csv
```

---

### 3. Tratamento dos valores numéricos

Foi criada uma função específica para realizar o saneamento dos valores:

```python
def limpar_numeros(valor):
```

Essa função trata:

* Valores vazios;
* Valores nulos;
* Traços (`-`);
* Separadores de milhar;
* Vírgulas e pontos decimais;
* Conversão dos valores para `float`.

---

### 4. Correção de registros inconsistentes

O projeto também identifica registros que poderiam distorcer a análise, como a linha:

```text
State unknown
```

Os votos eleitorais associados a esse registro são tratados para evitar que dados sem identificação de estado interfiram na soma do Colégio Eleitoral.

---

## ⚖️ 5. Pós-Estratificação e Calibração

Nesta etapa é aplicada uma reponderação dos dados para investigar o impacto do viés de amostragem.

Foram utilizados os seguintes fatores de calibração:

```python
peso_republicano = 0.782
peso_democrata = 1.197
```

Os pesos são aplicados aos resultados da pesquisa:

```python
df['Landon_Ajustado'] = df['Landon'] * peso_republicano
df['Roosevelt_Ajustado'] = df['Roosevelt (D)'] * peso_democrata
```

Depois disso, os vencedores estaduais antes e depois da calibração são comparados.

---

## 🤖 6. Modelagem com Regressão Linear

O projeto utiliza o **Scikit-Learn** para aplicar um modelo de Regressão Linear.

Primeiramente é calculada a proporção de votos de Landon na pesquisa:

```python
Prop_Landon_Pesquisa
```

Em seguida, o modelo é utilizado para gerar uma previsão calibrada:

```python
Pred_Landon_Regressao
```

A implementação utiliza a classe:

```python
LinearRegression()
```

e o método:

```python
predict()
```

---

## 📊 7. Avaliação dos resultados

Os resultados são avaliados utilizando métricas de erro, incluindo:

* **MAE — Mean Absolute Error**
* **MSE — Mean Squared Error**

O projeto compara o erro entre os dados originais da pesquisa e os dados após a calibração estatística.

Também é realizada uma comparação do resultado do Colégio Eleitoral entre:

1. Pesquisa original;
2. Modelo calibrado;
3. Resultado histórico oficial.

---

## 🗳️ 8. Análise do Colégio Eleitoral

O notebook consolida os votos eleitorais por estado para comparar as diferentes abordagens.

A análise considera a maioria necessária no Colégio Eleitoral em 1936:

```text
266 votos
```

O projeto apresenta a diferença entre a projeção obtida diretamente pela pesquisa e o resultado após a aplicação da calibração estatística.

---

## 📈 9. Visualização dos resultados

Ao final, é gerado um gráfico comparativo contendo:

* Resultado da pesquisa original;
* Resultado do modelo calibrado;
* Resultado oficial da eleição de 1936;
* Linha de referência da maioria do Colégio Eleitoral.

O gráfico é exportado em alta resolução:

```text
grafico_comparativo_1936.png
```

com:

```text
300 DPI
```

---

## 📁 Estrutura do Projeto

```text
📦 Hackathon-de-Ciencia-de-Dados
│
├── 📓 Hackathon_de_Ciência_de_Dados.ipynb
├── 📄 LitDigestFull.csv
├── 📄 dataset_1936_saneado.csv
├── 🖼️ grafico_comparativo_1936.png
└── 📄 README.md
```

---

## 📚 Principais bibliotecas

### Pandas

Utilizado para:

* Leitura do CSV;
* Manipulação dos DataFrames;
* Limpeza dos dados;
* Filtragem;
* Agrupamentos;
* Exportação dos dados.

### NumPy

Utilizado para:

* Operações matemáticas;
* Tratamento numérico;
* Cálculo das proporções;
* Operações condicionais.

### Scikit-Learn

Utilizado para:

* Regressão Linear;
* Geração das previsões;
* Cálculo das métricas de avaliação.

### Matplotlib e Seaborn

Utilizados para a construção das visualizações dos resultados.

---

## 💡 O que este projeto demonstra

Este projeto demonstra, na prática, algumas etapas importantes de um fluxo de **Ciência de Dados**:

```text
Dados Brutos
     ↓
Tratamento dos Dados
     ↓
Saneamento
     ↓
Análise do Viés
     ↓
Pós-Estratificação
     ↓
Modelagem
     ↓
Avaliação
     ↓
Visualização
```

Além da utilização de ferramentas de Python, o projeto mostra a importância de verificar a qualidade e a representatividade dos dados antes de utilizar uma base para realizar análises ou previsões.
⭐ Se este projeto foi útil para você, considere deixar uma estrela no repositório!

