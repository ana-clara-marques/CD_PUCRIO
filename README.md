# CD_PUCRIO
MVP — Machine Learning & Analytics: Detecção de Chuva

**Autora:** Ana Clara de Almeida Marques  
**Matrícula:** 4052025001106 
**Data:** 28/09/2025

## Descrição

Este projeto desenvolve um modelo de classificação binária para prever chuva vs. não chuva em registros horários de estações meteorológicas do INMET (Paraná, 2015–2019).
A proposta é utilizar apenas variáveis meteorológicas confiáveis (temperatura, umidade, radiação e vento) como preditores, evitando a dependência direta do pluviômetro, que é mais sujeito a falhas.

## Arquivos no repositório

- MVP_ML_&_Analytics_AnaClaraMarques_202509.ipynb → script principal em Jupyter Notebook (compatível com Google Colab)
- weather_PR_2015-2019_5estacoes.csv → dataset em CSV utilizado no experimento
- README.md → documentação do projeto

## Dataset

- Fonte: Estações meteorológicas automáticas do INMET (Paraná)
- Período: 2015–2019
- Frequência: registros horários
- Link CSV: (https://raw.githubusercontent.com/ana-clara-marques/CD_PUCRIO/refs/heads/main/weather_PR_2015-2019_5estacoes.csv)

**Variáveis:**
- rad_max (kJ/m²)
- temp_avg, temp_max, temp_min (°C)
- hum_max, hum_min (%)
- wind_max, wind_avg (m/s)
- rain_max (mm/h) → usada apenas para criar a variável alvo chuva

## Como Executar

- Google Colab (recomendado)
- Abra o notebook MVP_ML_&_Analytics_AnaClaraMarques_202509.ipynb diretamente no Colab.
- Todas as dependências já são suportadas.

## Dependências

Principais bibliotecas utilizadas:
- pandas, numpy — manipulação de dados
- matplotlib, seaborn — visualização
- scikit-learn — pré-processamento, pipelines, modelos e validação

## Modelos Avaliados

1. DummyClassifier (baseline)
2. LogisticRegression
3. LinearSVC
4. KNN
5. RandomForestClassifier

Validação com StratifiedKFold (k=10) e métrica principal F1 (classe chuva).

## Principas Resultados

Melhor modelo: LogisticRegression (C=1, balanced, SelectKBest(k=8))

Desempenho no teste:
- Accuracy ≈ 0.77
- F1 (chuva) ≈ 0.71
- Recall (chuva) ≈ 0.78

## Próximos Passos

- Adicionar variáveis temporais (lags, ciclos sazonais).
- Validação por estação (GroupKFold).
- Testar integração com dados de radar/satélite.

## Licença de uso dos dados
Os dados do INMET são públicos e de livre acesso para fins acadêmicos e científicos.
