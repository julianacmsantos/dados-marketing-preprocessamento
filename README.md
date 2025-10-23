# 📊 Pré-processamento de Dados de Marketing

Este projeto realiza o **pré-processamento completo** do dataset `dados_marketing.csv`, com foco em limpeza, enriquecimento e preparação dos dados para análises exploratórias e modelagem preditiva.

## 🧰 Bibliotecas utilizadas

| Biblioteca | Finalidade |
|------------|------------|
| `pandas`   | Manipulação de dados tabulares, leitura de CSV, criação de colunas derivadas, tratamento de nulos, duplicatas e exportação final |
| `numpy`    | Criação de atributos binários (`np.where`), soma de colunas, operações vetoriais |
| `os`       | Verificação e criação de diretórios para salvar o arquivo final (`os.path.exists`, `os.makedirs`) |

## 📁 Estrutura do projeto

- `dados_marketing.csv`: arquivo original com os dados brutos  
- `dados_marketing_limpo.csv`: arquivo final após pré-processamento  
- `dados_marketing_limpo.ipynb`: notebook com todo o pipeline de limpeza e engenharia de atributos  

## ⚙️ Etapas do pré-processamento

### 1. Carregamento e inspeção
- Leitura do arquivo `.csv` com separador `;`
- Verificação de valores nulos

### 2. Tratamento de dados
- Remoção de registros com salário nulo
- Eliminação de duplicatas

### 3. Engenharia de atributos
- Conversão da data de cadastro para datetime
- Extração de componentes da data: ano, mês, nome do mês, dia, dia da semana, semana ISO
- Cálculo da idade com base no ano de nascimento
- Segmentação por faixa etária
- Criação de atributo binário para presença de filhos ou adolescentes

### 4. Criação de métricas derivadas
- Soma de gastos por categoria → `gasto_total`
- Soma de compras por canal → `total_compras`
- Engajamento em campanhas: contagem total e indicador binário

### 5. Padronização
- Conversão de tipos para `float64` e `int64`
- Mapeamento binário para `Sim/Não`
- Padronização de nomes de colunas (sem acentos, espaços ou caracteres especiais)

### 6. Tradução de datas
- Tradução de dias da semana e meses do inglês para português via mapeamento

### 7. Detecção e tratamento de outliers
- Identificação de outliers com base no IQR
- Remoção dos registros com ano de nascimento incoerente (antes de 1920), que também corrigem idades inválidas

### 8. Salvamento final
- Cálculo de métricas de limpeza (linhas removidas e porcentagem)
- Exportação do dataset limpo para `.csv` com encoding UTF-8

## 📦 Como usar
# Clone o repositório
git clone https://github.com/julianacmsantos/dados-marketing-preprocessamento.git

# Copie o caminho do arquivo dados_marketing.csv
Cole o caminho no notebook em:

"
df = pd.read_csv('/content/drive/MyDrive/Estudos/Dados/Marketing/dados_marketing.csv', sep=';')
"

# Instale as dependências
import pandas as pd
import os
import numpy as np

# Execute o notebook
# Você pode usar Jupyter Notebook, Google Colab ou outro ambiente compatível
