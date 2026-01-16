---
layout: default
---

# Backup: 高・中重大度の発見手法と我々の見逃し分析

<div class="grid grid-cols-2 gap-4 mt-2">

<div>
<div class="text-sm font-bold mb-1">他の参加者の発見手法</div>
<div class="text-xs">

| ID | 重大度 | 発見手法 |
|:---|:-------|:---------|
| #40 | 高 | 仕様精読 + PoC |
| #190 | 高 | 仕様・コード比較 |
| #203 | 高 | 暗号学的分析 |
| #176 | 高 | 入力検証分析 |
| #210 | 高 | 検証ギャップ分析 |
| #15 | 中 | レースコンディション |
| #216 | 中 | 状態遷移分析 |

</div>
</div>

<div>
<div class="text-sm font-bold mb-1">我々の見逃し原因</div>
<div class="text-xs">

| 原因 | 件数 |
|:-----|:-----|
| 複雑な状態遷移 | 3件 |
| 動的境界条件 | 2件 |
| 外部依存 | 1件 |
| 仕様ニュアンス | 1件 |

</div>
</div>

</div>

<div class="grid grid-cols-2 gap-4 mt-3 text-sm">

<div class="p-2 bg-gray-50 border rounded">
<div class="font-bold">高重大度発見者の特徴</div>
<div class="text-xs mt-1">専門特化（暗号学、状態遷移）+ PoC実証 → 深いが属人的</div>
</div>


</div>

<!--
コンテストのレポート内容から、高・中重大度を発見した参加者が実際にどのような手法を用いたかを分析しました。

共通するのは、表面的なコードレビューではなく、深いドメイン知識に基づく分析と、PoCによる実証を組み合わせている点です。
-->
