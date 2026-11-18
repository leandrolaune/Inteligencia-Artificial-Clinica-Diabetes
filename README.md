# 🩺 Sistema Preditivo de Diagnóstico de Diabetes com Random Forest

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

</div>

---

## 📋 Sobre o Projeto

Este repositório contém o código-fonte de um sistema inteligente de **Machine Learning** desenvolvido para a área da saúde, focado na predição de diabetes com base em dados clínicos de pacientes (derivados do tradicional dataset *Pima Indians Diabetes*). 

O projeto implementa um pipeline completo de Inteligência Artificial que abrange análise exploratória de dados (EDA), pré-processamento com normalização e balanceamento, treinamento de um classificador robusto baseado em **Random Forest** (Floresta Aleatória), e a criação de uma interface interativa baseada em widgets para simulações clínicas em tempo real.

---

## 🧬 Variáveis Analisadas (Features)

O modelo avalia 8 indicadores clínicos e biométricos para realizar a predição:

| Variável | Descrição | Unidade / Formato |
| :--- | :--- | :--- |
| `gravidez` | Número de gestações | Inteiro |
| `glicose` | Concentração de glicose no plasma | mg/dL |
| `pressao` | Pressão arterial diastólica | mm Hg |
| `espessura_pele` | Espessura da dobra cutânea do tríceps | mm |
| `insulina` | Insulina sérica de 2 horas | mu U/ml |
| `imc` | Índice de Massa Corporal | $\text{peso / altura}^2$ |
| `pedigree` | Função de histórico familiar de diabetes | Valor decimal |
| `idade` | Idade do paciente | Anos |

---

## 🛠️ Pipeline e Metodologia de IA

1. **Aquisição e Carga:** Importação automatizada dos dados clínicos via URL remota.
2. **Análise Exploratória (EDA):** Geração de gráficos de distribuição das classes e histogramas de frequência de glicose.
3. **Pré-processamento:** 
   - Normalização de *features* utilizando `StandardScaler`.
   - Divisão estratificada dos dados (`train_test_split` com `stratify=y`) para preservar a proporção das classes no treino e teste.
4. **Modelagem:** Implementação do `RandomForestClassifier` com hiperparâmetros ajustados:
   - `n_estimators = 400`
   - `max_depth = 12`
   - `class_weight = 'balanced'` (para mitigar o viés em classes desbalanceadas)
5. **Avaliação e Interpretabilidad:** Extração de métricas de acurácia e precisão, acompanhadas do gráfico de importância das variáveis (*feature importances*).
6. **Interface Interativa:** Utilização da biblioteca `ipywidgets` no Google Colab para construir um painel visual dinâmico de predição de risco.

---

## 🚀 Como Executar o Projeto

### 1. Via Google Colab (Recomendado)
Faça o upload do arquivo `.ipynb` para o [Google Colab](https://colab.research.google.com/) e execute as células sequencialmente. Na última seção, você poderá interagir diretamente com os sliders para testar diferentes perfis de pacientes.

### 2. Execução Local

Clone este repositório e instale as dependências necessárias:

```bash
git clone [https://github.com/leandrolaune/Nome-Do-Repositorio.git](https://github.com/leandrolaune/Nome-Do-Repositorio.git)
cd Nome-Do-Repositorio
