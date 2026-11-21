# aula-ml

Atividade Prática 07 (CK0444 — UFC): versionamento de dados e modelos com Git + DVC.
Um rótulo errado de um chamado sintético é corrigido, um novo classificador é treinado
e as duas versões são comparadas com a mesma partição de teste.

## Pré-requisitos

- Git
- Python 3.10 ou superior (o classificador usa só a biblioteca padrão)
- DVC 3 (por exemplo: `pipx install 'dvc>=3,<4'`)

## Armazenamento DVC

O Git guarda código, tags, descritores `.dvc` e relatórios. Os CSVs e o modelo ficam no
armazenamento DVC, configurado como remote padrão `storage` na pasta irmã `../dvc-storage`:

```bash
dvc remote add -d storage ../dvc-storage
```

O clone deve ficar ao lado da pasta `dvc-storage` para que o caminho relativo funcione.

## Restaurar uma versão

```bash
git clone https://github.com/joaoatilamonteiro/aula-ml.git aula-ml-restauracao
cd aula-ml-restauracao
git switch --detach modelo-r1     # ou dados-v1, dados-v2, modelo-r2
dvc pull
```

Depois, confira os hashes dos arquivos com os valores de `reports/modelo.json`.

## Tags

| Tag | Conteúdo |
|---|---|
| dados-v1 | dataset e partição iniciais (com erro de rótulo no ID 006) |
| modelo-r1 | modelo treinado com o dataset v1 |
| dados-v2 | dataset com o ID 006 corrigido |
| modelo-r2 | modelo treinado com o dataset v2 |

O relatório da comparação está em `reports/comparacao.md`.
