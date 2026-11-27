# aula-ml

Pipeline de Machine Learning versionado com DVC, feito como exercício de aula. Treina um classificador (parâmetros controlados por `params.json`) a partir dos dados em `data/`, salvando o modelo treinado em `models/` e métricas/relatórios em `reports/`. O código de treino fica em `src/train.py`.

## Estrutura

```
aula-ml/
├── data/           # dados de entrada (versionados via DVC)
├── models/         # modelos treinados (saída do pipeline)
├── reports/        # métricas e relatórios gerados
├── params.json     # hiperparâmetros/configuração do treino
└── src/
    └── train.py    # script principal de treinamento
```

Os dados (`chamados.csv`, `split.csv`) e o modelo treinado (`model.json`) são versionados via DVC (arquivos `.dvc` + `.dvcignore`), não via Git direto. O script `src/train.py` usa só bibliotecas da standard library do Python (csv, json, hashlib etc.) — não depende de scikit-learn/pandas.

## Como usar

```bash
dvc pull           # baixa os dados/; versionados (se houver um remote configurado)
python src/train.py
```

O resultado (modelo e métricas) é salvo em `models/` e `reports/` (`metrics.json`, `modelo.json`).
