# Precificação de Passagens Aéreas

Este projeto foi desenvolvido como parte da disciplina de Aprendizado de Máquina do mestrado em Inteligência Computacional na Universidade Federal do Rio Grande do Norte (UFRN). O estudo tem como objetivo prever os preços de passagens aéreas utilizando algoritmos de aprendizado de máquina.

- **Notebook do Projeto**: [Flight_Price_Prediction.ipynb](./Flight_Price_Prediction.ipynb)
- **Artigo Final**: [Artigo - Precificação de Passagens Aéreas.pdf](./Artigo%20-%20Precificação%20de%20Passagens%20Aéreas.pdf)
- **Fonte dos Dados**: [Kaggle - Flight Price Prediction Dataset](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction)

## Objetivo

O projeto visa identificar o modelo preditivo mais adequado para prever preços de passagens aéreas, considerando variáveis como companhia aérea, cidade de origem e destino, duração do voo, e número de escalas.

## Metodologia

- **Base de Dados**: Dados coletados por 50 dias através da plataforma EaseMyTrip, contendo informações de voos entre as principais cidades da Índia. O dataset inclui 300.261 registros de opções de voos, com 11 variáveis relevantes (companhia aérea, tempo de partida e chegada, escalas, classe do assento, duração do voo, antecedência da reserva, entre outras).

- **Pré-processamento**: As variáveis foram tratadas para atender aos requisitos dos modelos de machine learning, incluindo normalização de variáveis numéricas e codificação de variáveis categóricas utilizando o `TargetEncoder` para modelos baseados em árvores e `OneHotEncoder` para a Regressão Ridge.

- **Modelos**: Foram testados três modelos baseados em árvores de decisão — XGBoost, LightGBM, e CatBoost — e um modelo linear, Regressão Ridge. Cada modelo foi avaliado com um pipeline de pré-processamento e validado por meio de métricas como MAE, MSE, RMSE e MAPE.

## Resultados

Para avaliar a precisão dos modelos na previsão dos preços de passagens aéreas, utilizamos a métrica **Mean Absolute Percentage Error (MAPE)** como critério principal. O MAPE mede o erro percentual médio das previsões em relação aos valores reais, oferecendo uma perspectiva relativa que facilita a interpretação e comparação de desempenho entre modelos, independentemente da unidade monetária.

A escolha do MAPE como métrica principal se justifica por sua interpretação intuitiva e aplicabilidade em cenários de precificação. Como o MAPE é expresso em termos percentuais, ele fornece uma estimativa direta do erro médio em relação ao valor real, o que permite interpretar a precisão do modelo de forma acessível. Nesse contexto, onde o preço das passagens é apresentado em Rupias Indianas (INR), uma unidade que pode não ser familiar para todos os usuários, o MAPE facilita a avaliação do desempenho do modelo sem exigir uma compreensão aprofundada dos valores monetários específicos. Além disso, em problemas de precificação, o MAPE é especialmente útil para capturar o desempenho do modelo ao longo de uma ampla faixa de valores de preços, garantindo que as previsões se mantenham proporcionais aos valores reais. Isso é particularmente relevante para modelos preditivos em mercados voláteis, como o de passagens aéreas, onde é essencial que o erro seja comparativamente baixo em relação ao valor da passagem. 

- **Modelo Destacado**: O XGBoost obteve o melhor desempenho com um MAPE de 14,39%, apresentando estabilidade e consistência nas previsões, o que o torna o modelo mais indicado para precificação de passagens aéreas.
  
- **Outros Modelos**: LightGBM e CatBoost também apresentaram bons desempenhos, enquanto a Regressão Ridge teve o pior resultado, com um MAPE de 42,70%, sugerindo uma limitação na captura das relações não-lineares dos dados.

## Conclusão

O XGBoost foi selecionado como o modelo mais adequado devido ao seu baixo MAPE e robustez nas previsões. Para aprimorar o modelo, sugerem-se futuras melhorias, como a inclusão de novas variáveis e ajustes de hiperparâmetros. Este projeto demonstra o potencial do aprendizado de máquina para auxiliar na precificação dinâmica no setor aéreo.

## Referências

- Hastie, T., Tibshirani, R., Friedman, J. H., & Friedman, J. H. (2009). *The elements of statistical learning: data mining, inference, and prediction*. Springer.
- Hyndman, R. (2018). *Forecasting: principles and practice*. OTexts.
- James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013). *An introduction to statistical learning*. Springer.
- Larose, D. T. (2015). *Data mining and predictive analytics*. John Wiley & Sons.
- Prokhorenkova, L., et al. (2018). *Catboost: unbiased boosting with categorical features*. Advances in Neural Information Processing Systems.

