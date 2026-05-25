# CV設計

Local CVとPublic/Private LBの関係を安定させるための知見をまとめる。

## Checklist

- 評価指標と同じ目的でCVを作る
- train/testの生成過程を想像する
- グループ単位のリークを避ける
- 時系列データでは未来情報を使わない
- Stratified、Group、TimeSeriesなどの分割候補を比較する
- CVスコアの平均だけでなくfoldごとのばらつきを見る
- Public LBへ過剰適合していないか確認する

## Notes

まだ知見はない。コンペで得た学びを追記する。
