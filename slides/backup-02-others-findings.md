---
layout: default
---

# Backup: 他の参加者が発見した高・中重大度

<div class="mt-2 text-xs">

| ID | 重大度 | クライアント | 発見概要 | 見逃し原因 |
|:---|:-------|:-------------|:---------|:-----------|
| #40 | High | Lighthouse | Proposer計算でlookahead未考慮 | 仕様の細部 |
| #190 | High | Prysm | キャッシュキーにkzg_commitments未含 | 仕様の細部 |
| #176 | High | Nethermind | blob tx長さ検証の欠如 | 仕様の細部 |
| #210 | High | Nethermind | blob hash数と実データ数の不一致許容 | 仕様の細部 |
| #203 | High | c-kzg-4844 | Fiat-Shamirチャレンジの実装誤り | 外部ライブラリ |
| #15 | Medium | Nimbus | metadata更新間のCGC変更でDoS | タイミング |
| #216 | Medium | Nimbus | Fork後に古いメタデータ使用 | タイミング |

</div>

<div class="mt-3 p-3 bg-yellow-50 border-l-4 border-yellow-500 text-sm">

**我々の見逃し原因**: 仕様の細部・暗黙の前提（4件）、タイミング/並行性（2件）、外部ライブラリ（1件）

</div>

<!--
他の参加者が発見した高・中重大度の脆弱性と、我々の見逃し原因の対応です。

4件は仕様の細部の見落としでした。キャッシュキーに何を含めるべきか、入力長さの検証など、仕様に書いてあるが見落としやすい部分です。チェックリストの粒度を上げることで改善可能です。

2件はタイミング/並行性の問題で、Fork遷移やmetadata更新のタイミングに起因します。静的分析では捉えにくい問題です。

1件は暗号ライブラリc-kzg-4844の実装誤りで、これは意図的にスコープ外としていました。
-->
