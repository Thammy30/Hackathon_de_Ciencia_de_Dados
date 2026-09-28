

# Autópsia Estatística de 1936: Correção Forense de Viés e Pós-Estratificação na Eleição Americana
 
## 📌 Sobre o projeto
 
Este projeto investiga os mecanismos do severo **viés de amostragem** presente na pesquisa eleitoral realizada pela revista *Literary Digest* durante a eleição presidencial norte-americana de 1936.
 
A análise utiliza microdados históricos das eleições de **1932 e 1936** para identificar limitações metodológicas, desvios de representatividade e os efeitos da aplicação de técnicas estatísticas de correção.
 
O projeto também busca demonstrar, de forma transparente, que técnicas computacionais e modelos preditivos não eliminam automaticamente problemas originados na qualidade e representatividade dos dados.
 
---
 
## 🎯 Objetivo
 
Investigar os mecanismos responsáveis pelo viés de amostragem na pesquisa eleitoral da *Literary Digest* de 1936 e realizar uma análise crítica das limitações, desvios e erros encontrados durante as tentativas de calibração estatística das estimativas.
 
---
 
## 🔬 Metodologia
 
O estudo adotou uma abordagem **computacional e estatística**, utilizando microdados históricos relacionados às eleições presidenciais de 1932 e 1936.
 
O fluxo de análise foi desenvolvido em **Python**, utilizando o **Google Colab**, e envolveu:
 
- Curadoria e tratamento dos dados com **Pandas**;

- Análise exploratória dos microdados;

- Auditoria dos desvios entre estimativas e resultados eleitorais;

- Análise dos desvios por estado;

- Simulações de **reponderação por pós-estratificação**;

- Treinamento de modelos de **Regressão Linear** utilizando Scikit-Learn;

- Avaliação das limitações dos modelos e das estratégias de correção.
 
---
 
## 📊 Principais resultados
 
A exploração dos dados identificou **erros estruturais significativos** na base original da pesquisa.
 
Entre os principais resultados observados:
 
- Sobrestimação sistemática das estimativas em favor do candidato republicano;

- Viés médio de **+4,13 pontos percentuais (p.p.) em 1932**;

- Aumento do viés médio para **+18,80 p.p. em 1936**;

- Identificação de distorções superiores a **70 p.p. em determinados estados**;

- Limitações na capacidade de generalização de modelos de regressão linear simples;

- Assimetria no desempenho das estratégias de correção;

- Dificuldades na extrapolação de padrões temporais diante de ruídos e taxas elevadas de não resposta.
 
---
 
## 🧮 Análise do modelo
 
Foram utilizados modelos de **Regressão Linear** como parte da investigação das possibilidades de correção das estimativas.
 
Os resultados indicaram que modelos lineares simples e fatores estáticos de correção apresentaram limitações importantes de generalização.
 
A análise demonstra que a aplicação direta de padrões observados em um período não garante resultados confiáveis em outro contexto, especialmente quando existem problemas de representatividade e não resposta na origem dos dados.
 
---
 
## 🔎 Conclusão
 
O estudo evidencia que **algoritmos lineares básicos e correções empíricas univariadas não corrigem automaticamente anomalias metodológicas severas**.
 
Os resultados reforçam a importância de:
 
- Auditar a representatividade dos dados;

- Identificar possíveis vieses de seleção e amostragem;

- Avaliar taxas e padrões de não resposta;

- Validar modelos em diferentes contextos;

- Documentar limitações e falhas preditivas;

- Manter transparência durante todo o processo de análise.
 
Dessa forma, o caso da *Literary Digest* de 1936 permanece relevante para compreender os desafios envolvidos na aplicação de métodos estatísticos e computacionais a dados sociopolíticos.
 
---
 
## 🛠️ Tecnologias utilizadas
 
- **Python**

- **Google Colab**

- **Pandas**

- **Scikit-Learn**

- **Jupyter Notebook**

- **Excel**
 
---
 
## 📂 Estrutura do projeto
 
```text

📦 autopsia-estatistica-1936

│

├── 📓 notebooks/

│   └── analise_1936.ipynb

│

├── 📊 dados/

│   ├── LitDigestFull.xlsx

│   └── Literary Digest 1936 Sols.xlsx

│

├── 📄 README.md

│

└── 📑 referencias/

```
 
---
 
## 👥 Autores
 
**André Mitchel Ruiz Santos**  

**Franciellen Moreira Santos**  

**Maria Augusta dos Santos Toledo**  

**Thamirys Matos da Silva**
 
**Orientador:** Prof. Dr. Fabiano Menegidio
 
**Universidade de Mogi das Cruzes (UMC)**  

Projeto desenvolvido no contexto acadêmico da área de Ciência de Dados, Estatística e Inteligência Artificial.
 
---
 
## 📚 Referências
 
1. Robinson C. *Straw votes: a study of political predicting*. Columbia University Press; 1932.

2. Bruce P, Bruce A. *Estatística prática para cientistas de dados*. Alta Books; 2019.

3. Gelman A, et al. *Bayesian data analysis*. Chapman and Hall/CRC; 2013.

4. Géron A. *Mãos à obra: aprendizado de máquina*. Alta Books; 2019.
 
