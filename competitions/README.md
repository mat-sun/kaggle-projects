# competitions

各Kaggleコンペティションの作業ディレクトリを置く。

## Recommended Layout

```text
competitions/<competition-slug>/
├── README.md
├── notebooks/
├── src/
├── configs/
├── data/
├── models/
├── outputs/
├── submissions/
└── reports/
```

## Directory Roles

- `README.md`: コンペ概要、評価指標、データ、方針、結果まとめ
- `notebooks/`: EDA、実験、提出用Notebook
- `src/`: 再利用するPythonコード
- `configs/`: 実験設定、特徴量設定、モデル設定
- `data/`: Kaggleデータや前処理済みデータ
- `models/`: 学習済みモデル
- `outputs/`: OOF、予測値、中間生成物
- `submissions/`: 提出ファイルと提出ログ
- `reports/`: 分析メモ、図表、振り返り

`data/`, `models/`, `outputs/` の重いファイルはGit管理しない。必要な再現手順は各コンペのREADMEに残す。
