# Identificação de Operadores Ineficientes — CallMeMaybe

## 📋 Descrição
Análise de dados de chamadas de uma empresa de telefonia virtual para identificar, de forma objetiva, operadores de call center ineficientes, com dashboard interativo publicado no Tableau Public.

## 🎯 Objetivo
Dar aos supervisores um critério objetivo e baseado em dados para identificar operadores com baixo desempenho, substituindo decisões subjetivas por uma classificação estatística clara.

## 🗂️ Dados
Registros de chamadas (mais de 53 mil linhas) de uma empresa de telefonia virtual, unidos a uma base de clientes, com informações de direção da chamada, duração, tempo de espera e operador responsável.

## 🛠️ Tecnologias
- Python (Pandas, NumPy)
- SciPy (teste de Shapiro-Wilk, correlação de Spearman, teste de Mann-Whitney, tamanho de efeito rank-biserial)
- Matplotlib
- Tableau Public (dashboard interativo)

## 🔍 Etapas da análise
1. Limpeza dos dados: tratamento de tipos, remoção de valores ausentes e duplicatas
2. Análise exploratória, incluindo teste de normalidade (Shapiro-Wilk)
3. Cálculo de 3 KPIs por operador: taxa de chamadas perdidas, tempo de espera e volume de chamadas ativas
4. Criação de um Score de Ineficiência combinando os três KPIs por percentis
5. Testes estatísticos para validar hipóteses sobre o comportamento dos operadores
6. Classificação dos operadores em quatro níveis (eficiente, atenção, ineficiente, crítico) e exportação dos dados para um dashboard no Tableau

## 📊 Principais resultados
- 104 operadores (9,5% do total) foram sinalizados como precisando de atenção: 3 críticos (violam os três critérios) e 101 ineficientes (violam dois)
- Existe relação significativa entre tempo de espera e chamadas perdidas (Spearman = 0,31, p < 0,05)
- Não há diferença relevante na taxa de perdas entre chamadas internas e externas (p = 0,97)
- Há diferença real e expressiva de produtividade entre operadores de saída (p < 0,05): operadores de baixo volume fazem uma mediana de 3 chamadas, contra 224 dos de alto volume
- Recomendação: avaliação prioritária dos 3 operadores críticos e programa de treinamento para os 101 ineficientes

**Dashboard interativo no Tableau Public:** [ver aqui](https://public.tableau.com/app/profile/steffany.cardoso/viz/CallMeMaybe-OperadoresInefiente/DashboardCallMeMaybe)

## 🚀 Como executar
```bash
git clone https://github.com/steffanycardoso/callmemaybe-operadores-ineficientes.git
cd callmemaybe-operadores-ineficientes
pip install pandas numpy scipy matplotlib
jupyter notebook
```

## 📁 Estrutura do repositório
```
├── callmemaybe-operadores-ineficientes.ipynb
└── README.md
```
