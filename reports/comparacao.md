# Comparação entre os modelos r1 e r2

## Alteração feita

O chamado 006 ("bloqueio de acesso") estava rotulado como comum. Pela regra de rotulagem
(bloqueio é urgente), o rótulo foi corrigido para urgente. O dataset passou de chamados-v1
para chamados-v2. A partição treino/teste (split.csv) não foi alterada.

## Métricas (mesma partição de teste, 4 exemplos)

| Métrica | r1 (dados v1) | r2 (dados v2) |
|---|---|---|
| Acurácia | 0.75 | 1.0 |
| Recall de urgentes | 0.5 | 1.0 |
| Recall de comuns | 1.0 | 1.0 |

## Hashes verificados no clone limpo (modelo-r1)

Commit selecionado: cdb5c93cd8239a179dad6b15881e01379bb49d8a

    data/chamados.csv   bc3fd86a3a5f598841a58839a9726d901fa7e8361ffe79c5b43873ad8a1328ac
    data/split.csv      2ef820171c1a4625fe216e6da67c7c8dcf9d97a08288c0239cd23f1a6961d981
    models/model.json   09d965544c9298c5586af0a1becbf07fb3f3c7b7c228a803ab91179f8b458a09

Os três hashes conferem com os registrados em reports/modelo.json da versão r1.

## Decisão

Critério: melhorar o recall de urgentes sem reduzir o recall de comuns, com a mesma
partição de teste.

**Decisão para este exercício: ACEITAR o modelo r2.**

Ressalva: o conjunto de teste tem apenas 4 exemplos, portanto a comparação demonstra o
efeito da correção neste exercício e não serve como evidência estatística geral.
