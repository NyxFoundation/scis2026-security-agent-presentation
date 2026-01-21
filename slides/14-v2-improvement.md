---
layout: default
---

# V2改善: プログラムグラフによる仕様形式化

<div class="grid grid-cols-2 gap-6 mt-2">

<!-- 左側: プログラムグラフ -->
<div>
<img src="/images/program_graph_eip4844.png" class="w-full rounded border shadow" />
</div>
<!-- 右側: V2フェーズと成果物 -->
<div class="text-sm">

| フェーズ | 成果物 | V1課題への対応 |
|---------|--------|---------------|
| **SPEC** | ノード、エッジ、データ構造 | 仕様の細部を網羅 + スコープ拡大 |
| **TRUSTMODEL** | アクター、境界エッジ | 脅威モデル不整合を解消 |
| **CHECKLIST** | 220項目 | 粒度向上 |
| **AUDITMAP** | 静的監査レポート | — |

<div class="mt-2 p-1.5 bg-gray-100 rounded text-xs text-center">
<span class="text-gray-500">未対応:</span> タイミング/並行性（静的分析の限界）
</div>

</div>

</div>

<!--
V1の分析を踏まえ、V2では4つのフェーズで改善しました。

左の図はEIP-4844のBLOBHASH opcodeをプログラムグラフとして形式化した例です。

誤検知の最大原因だった脅威モデル不整合については、TRUSTMODELフェーズで信頼境界を明示的に形式化することで対応しました。

仕様の細部についてはグラフ化とチェックリストの粒度向上で対応し、220項目のチェックリストを生成しています。外部ライブラリについてはスコープを拡大しました。

一方、タイミングや並行性の問題は静的分析の限界であり、今後の課題として残っています。
-->
