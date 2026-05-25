# <competition-name>

## Overview

- Competition:
- URL:
- Period:
- Task:
- Metric:
- Submission format:
- External data:
- Team / rule notes:

## Goal

このコンペで検証したいこと、到達したいスコア、学びたいテーマを書く。

## Data

```text
data/
├── raw/
├── processed/
└── external/
```

データ取得手順:

```powershell
# Example
kaggle competitions download -c <competition-slug> -p data/raw
```

## Local Validation

- CV strategy:
- Fold count:
- Group / time split:
- Leakage concerns:

## Experiments

実験ログは [experiment_log.md](./experiment_log.md) に記録する。

## Submissions

提出履歴は [submission_log.md](./submission_log.md) に記録する。

## Final Summary

### Best Submission

- Submission ID:
- Local CV:
- Public LB:
- Private LB:
- Description:

### What Worked

- TBD

### What Did Not Work

- TBD

### Knowledge To Move

`knowledge/` に移すべき汎用知見を書く。
