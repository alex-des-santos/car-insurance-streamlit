# Dashboard de Análise de Sinistros de Seguros - Streamlit

Dashboard interativo para análise de dados de sinistros de seguros de automóveis, desenvolvido com Streamlit.

## Visão Geral

Este projeto fornece uma análise completa da taxa de sinistro por segmentos de clientes, identificando sinais associados a maior risco para apoiar precificação, underwriting e retenção.

## Funcionalidades

### Página 1: Visão Geral
- KPIs principais (total de clientes, sinistros, taxa)
- Comparação de taxa de sinistro por idade
- Comparação de taxa de sinistro por experiência
- Distribuição de clientes por renda
- Balanceamento de classes

### Página 2: Drivers (Fatores de Risco)
- Filtros interativos por idade, experiência e renda
- Heatmap de taxa de sinistro (experiência × idade)
- Taxa de sinistro por ano do veículo
- Análise de quilometragem anual
- Estatísticas dos dados filtrados

### Página 3: Recomendações
- 5 ações práticas baseadas nos insights
- Roadmap de implementação
- Limitações do dataset
- Próximos passos

## Instalação

### Requisitos
- Python 3.8+
- pip

### Passos

1. Clone o repositório:
```bash
git clone https://github.com/alex-des-santos/Case-Study_car-insurance-analysis.git
cd car-insurance-streamlit
```

2. Crie um ambiente virtual:
```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

## Execução Local

```bash
streamlit run app.py
```

O dashboard abrirá em `http://localhost:8501`

## Deploy no Streamlit Cloud

1. Faça push do código para GitHub
2. Acesse [Streamlit Cloud](https://streamlit.io/cloud)
3. Clique em "New app"
4. Selecione o repositório e o branch
5. Configure o caminho do arquivo como `app.py`
6. Clique em "Deploy"

## Dataset

O projeto utiliza o dataset "Car Insurance Data" disponível no Kaggle:
- [Kaggle Dataset](https://www.kaggle.com/datasets/sagnik1511/car-insurance-data)
- 10.000 registros
- 19 colunas
- Taxa de sinistro: 31.33%

## Tratamento de Dados

- Valores faltantes em CREDIT_SCORE: imputados pela mediana por renda
- Valores faltantes em ANNUAL_MILEAGE: imputados pela mediana geral
- Sem duplicatas encontradas
- Balanceamento de classes: 68.67% sem sinistro, 31.33% com sinistro

## Insights Principais

1. **Idade Importa**: Jovens dirigem 7.3x mais arriscado
2. **Experiência é Tudo**: 97% de redução no risco com experiência
3. **Renda Fala Alto**: 4.9x diferença entre classes
4. **Carros Velhos**: 3.8x mais risco
5. **Paradoxo do Histórico**: Investigação necessária

## Modelo Interpretável

O projeto inclui um modelo de regressão logística com:
- AUC-ROC: 0.8861
- F1-Score: 0.7305
- Coeficientes interpretáveis para cada fator

## Limitações

- Snapshot no tempo (sem série histórica)
- Sem dados de severidade de sinistros
- Sem informações de localização geográfica
- Sem dados de comportamento de direção em tempo real

## Estrutura do Projeto

```
car-insurance-streamlit/
├── app.py                      # Aplicação principal do Streamlit
├── requirements.txt            # Dependências do projeto
├── README.md                   # Este arquivo
├── .streamlit/
│   └── config.toml            # Configuração do Streamlit
└── Car_Insurance_Claim.csv    # Dataset
```

## Autor

Desenvolvido como análise técnica de dados para seguradora de automóveis.

## Licença

MIT
