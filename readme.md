# Projeto - Churn SaaS (TechGrow)

Estudo de cancelamento de clientes de uma empresa SaaS. O notebook reúne a exploração da base, a comparação de três modelos e a interpretação dos resultados para discutir possíveis ações de Produto e Customer Success.

## Estrutura final

- `visualization.ipynb`: notebook completo com EDA, preparacao de dados, treino dos modelos, avaliacao e interpretacao.
- `requirements.txt`: bibliotecas necessarias.
- `data/Caso_Pratico_base_churn_saas.csv`: base do desafio.

## Objetivo do notebook

Prever `churn` e explicar os fatores que mais influenciam cancelamento em um contexto SaaS.

## O que esta implementado

1. Exploracao inicial dos dados (shape, colunas, tipos, amostra).
2. Verificacao de qualidade (nulos, estatisticas descritivas, taxa geral de churn).
3. EDA visual:
   - distribuicao do target;
   - histogramas por churn;
   - boxplots por churn;
   - churn medio por variaveis categoricas;
   - heatmap de correlacao.
4. Preparacao dos dados:
   - exclusao de `id_cliente`;
   - One-Hot Encoding para categoricas;
   - StandardScaler para numericas;
   - remocao de colunas numericas redundantes por alta correlacao.
5. Split treino/teste com 70/30 e `stratify`.
6. Treino e comparacao dos modelos:
   - Logistic Regression (baseline),
   - Random Forest,
   - XGBoost.
7. Avaliacao com:
   - accuracy,
   - precision,
   - recall,
   - f1-score,
   - roc_auc_score,
   - matriz de confusao,
   - curva ROC.
8. Interpretacao:
   - importancias por modelo,
   - ranking consolidado de variaveis,
   - recomendacoes acionaveis para Produto/CS.

## Como executar

1. Instale dependencias:

```powershell
pip install -r requirements.txt
```

2. Abra o notebook `visualization.ipynb` no Jupyter/VS Code.

3. Execute as celulas em ordem.

## Observacao importante

Se a variavel `inadimplencia` separar churn quase perfeitamente, isso pode indicar leakage (ou regra de negocio extremamente deterministica). Nessa situacao, valide com dados adicionais antes de colocar o modelo em producao.

## Licença

Código e documentação autorais sob [MIT](license). Bases de dados, materiais de curso e outros conteúdos de terceiros mantêm seus termos próprios.
