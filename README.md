# Predição de Compra de Carros por Comportamento de Clientes 🚗

Prever se um cliente comprará um carro com base em idade, salário anual e gênero usando Machine Learning.
O modelo principal é XGBoost, que captura padrões complexos e prioriza recall — identificar corretamente clientes que realmente irão comprar.

Base de Dados:

User ID (removido do modelo)

Gender (0/1)

Age

AnnualSalary

Purchased (0 = não, 1 = sim)

Distribuição: ~60% não compraram, 40% compraram.

Pré-processamento:

Remoção de User ID

Conversão de Gender para 0/1

Nenhum valor nulo encontrado

Separação em features (X) e target (Y)

Divisão: 70% treino / 30% teste

Modelo:

XGBoost Classifier com hiperparâmetros ajustados:

n_estimators=200

max_depth=4

learning_rate=0.1

subsample=0.8

colsample_bytree=0.8

scale_pos_weight=1.49

eval_metric='logloss'

Treino final: API nativa do XGBoost + early stopping.

Objetivo: maximizar recall — capturar a maior quantidade de compradores reais.

Resultados:

Acurácia: 90%

Recall (classe 1): 90%

Matriz de Confusão: acertos/erros detalhados por classe

Principais features:

Salário Anual 💰

Idade 🎂

Gênero 👤 (menos relevante, mas contribui para robustez)

Insights:

Clientes com maior renda e idade específica têm mais chance de comprar.

O modelo é útil para marketing e vendas direcionadas, focando nos clientes com maior probabilidade de compra.

Próximos Passos:

Adicionar variáveis comportamentais (ex.: histórico de compras, interações de marketing)

Ajustar thresholds para reforçar recall

Criar visualizações interativas de análise

Bibliotecas:

pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn, plotly

Estrutura:

data/ → CSV da base

notebooks/ → pré-processamento, treino e análise

src/ → scripts Python

README.md → descrição e resultados

