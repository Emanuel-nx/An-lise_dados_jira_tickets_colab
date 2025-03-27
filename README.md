# 📌 Análise de Tickets de Suporte no Jira

## 📖 Resumo
Este projeto tem como objetivo realizar a **análise de tickets de suporte** extraídos do **Jira**. O notebook processa os dados, gera insights e apresenta visualizações para entender melhor o fluxo de atendimento e desempenho da equipe de suporte.

---
## 🚀 Tecnologias Utilizadas
- **Python 3**
- **Pandas** (para manipulação de dados)
- **NumPy** (para operações matemáticas)
- **Matplotlib e Seaborn** (para visualizações de dados)
- **Jupyter Notebook / Google Colab** (para execução do código)
- **Jira API** (para extração de dados de tickets)

---
## 🎯 Como Executar no Google Colab

1. **Faça upload do arquivo `Jira_analise_tickets_suporte.ipynb`** no Colab.
2. **Instale as dependências (se necessário)** executando:
   ```python
   !pip install pandas numpy matplotlib seaborn requests
   ```
3. **Execute os blocos de código sequencialmente**.

---
## 💻 Como Clonar e Executar Localmente
1. **Clone o repositório:**
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```
2. **Crie um ambiente virtual (opcional, mas recomendado):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate  # Windows
   ```
3. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Execute o notebook:**
   ```bash
   jupyter notebook
   ```

---
## 📝 Explicação do Código
### 1️⃣ **Importação de Bibliotecas**
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import requests
```
Essas bibliotecas são essenciais para manipulação de dados e visualização.

### 2️⃣ **Processamento dos Dados**
```python
df['created'] = pd.to_datetime(df['fields.created'])
df['resolved'] = pd.to_datetime(df['fields.resolutiondate'])
df['tempo_resolucao'] = (df['resolved'] - df['created']).dt.days
```
Calculamos o tempo de resolução de cada ticket para análise.

### 3 **Visualização dos Dados**
```python
sns.histplot(df['tempo_resolucao'], bins=30, kde=True)
plt.title("Distribuição do Tempo de Resolução de Tickets")
plt.xlabel("Dias para resolução")
plt.ylabel("Frequência")
plt.show()
```
Criamos um histograma para entender a distribuição do tempo de resolução dos tickets.

---
## 📌 Conclusão
Este projeto permite analisar a eficiência da equipe de suporte, identificar padrões nos atendimentos e otimizar os processos baseados nos insights gerados.
Se precisar de melhorias ou novas funcionalidades, fique à vontade para contribuir! 🚀


