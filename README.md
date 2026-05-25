# kaggle-projects

Kaggleコンペティションへの参加記録と、分析手法・AIモデル開発手法のノウハウを蓄積するためのリポジトリである。

このリポジトリでは、Notebookを作って提出するだけでなく、次のコンペでも再利用できる判断材料を残すことを重視する。

- どの仮説を検証したか
- どの特徴量・モデル・CV設計が効いたか
- Public LBとLocal CVの差をどう解釈したか
- 失敗した実験から何を学んだか
- 提出直前に何を確認したか

## Repository Structure

```text
.
├── competitions/
│   └── <competition-slug>/
│       ├── README.md
│       ├── notebooks/
│       ├── src/
│       ├── configs/
│       ├── data/
│       ├── models/
│       ├── outputs/
│       ├── submissions/
│       └── reports/
├── knowledge/
│   ├── README.md
│   ├── cv.md
│   ├── eda.md
│   ├── feature_engineering.md
│   ├── modeling.md
│   └── submission.md
└── templates/
    └── competition/
        ├── README.md
        ├── experiment_log.md
        └── submission_log.md
```

## Directory Roles

### `competitions/`

各Kaggleコンペティションの作業場所である。コンペごとに1ディレクトリを作成する。

推奨名はKaggleのURL slugに合わせる。

```text
competitions/playground-series-s4e1/
competitions/titanic/
```

各コンペでは、Notebook、再利用コード、設定、実験ログ、提出履歴、分析メモをまとめる。

### `knowledge/`

コンペ横断で使える知見を蓄積する。

特定コンペの結果から得た知見も、再利用できる形に一般化できたらここへ移す。たとえば、CV設計、リーク検証、カテゴリ特徴量、時系列分割、LightGBM/XGBoost/CatBoost、NN、アンサンブル、提出前チェックなどである。

### `templates/`

新しいコンペを始めるときの雛形である。

`templates/competition/` をコピーして、`competitions/<competition-slug>/` に配置する。

## Competition Workflow

1. コンペ概要を読む
   - 評価指標
   - データ構造
   - 提出形式
   - ルール、外部データ可否、チーム制限

2. ベースラインを作る
   - 最小限のEDA
   - Local CVの作成
   - 単純なモデルで提出まで通す

3. 実験を積む
   - 1実験につき仮説を1つ明確にする
   - CV、Public LB、変更点、所感を記録する
   - よかった実験だけでなく、外した実験も残す

4. 提出を管理する
   - 提出ファイル名、生成元、CV、LB、コメントを残す
   - 最終提出候補を比較できる状態にする

5. 振り返る
   - 効いたこと、効かなかったことを整理する
   - 再利用できる知見を `knowledge/` に移す

## Data And Artifact Policy

Kaggleのデータ、学習済みモデル、重い中間生成物は原則としてGit管理しない。

Git管理するもの:

- コード
- Notebook
- 設定ファイル
- 実験ログ
- 提出履歴
- 軽量な分析メモ

Git管理しないもの:

- 生データ
- 大きな前処理済みデータ
- 学習済みモデル
- 大量の予測ファイル
- キャッシュや一時出力

必要に応じて、各コンペのREADMEにデータ取得手順や再現手順を書く。

## Naming Guidelines

Notebook名は、順序と目的が分かる形にする。

```text
001_eda.ipynb
002_baseline_lgbm.ipynb
003_feature_user_stats.ipynb
004_ensemble.ipynb
```

実験IDはNotebook、設定、提出履歴でそろえると追跡しやすい。

```text
exp001_baseline_lgbm
exp002_target_encoding
exp003_catboost
```

## Suggested Tools

このリポジトリでは、コンペごとに必要なライブラリを選ぶ。基本候補は次の通りである。

- Python
- Jupyter Notebook
- pandas / polars
- numpy
- scikit-learn
- LightGBM / XGBoost / CatBoost
- PyTorch
- matplotlib / seaborn / plotly
- optuna

## Notes

このREADMEは初版である。コンペを進めながら、実際に使いやすい運用へ更新していく。
