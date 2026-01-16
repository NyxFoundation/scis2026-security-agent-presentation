---
layout: two-cols
layoutClass: gap-6
---

# 見逃しは複雑状態遷移と動的境界条件に集中した

<div class="text-xs mt-4">

| カテゴリ | 件数 | 割合 |
|---------|---:|---:|
| **複雑状態遷移** | **3** | **42.9%** |
| **動的境界条件** | **2** | **28.6%** |
| 外部依存 | 1 | 14.3% |
| 仕様ニュアンス | 1 | 14.3% |

</div>

::right::

<div class="text-xs mt-16 space-y-3">

<div class="p-2 bg-orange-50 rounded border border-orange-300">
  <div class="font-bold text-orange-700">複雑状態遷移（42.9%）</div>
  <div class="text-gray-700 mt-1">
    長い状態遷移チェーンを経て初めて顕在化<br>
    → 静的な仕様チェックでは捕捉困難
  </div>
  <div class="text-gray-500 mt-1">例: 高#190 Prysmのキャッシュ実装バグ</div>
</div>

<div class="p-2 bg-blue-50 rounded border border-blue-300">
  <div class="font-bold text-blue-700">動的境界条件（28.6%）</div>
  <div class="text-gray-700 mt-1">
    実行時に決まる境界値の問題<br>
    → 静的解析だけでは不十分
  </div>
  <div class="text-gray-500 mt-1">例: 高#176, #210 Nethermindの境界チェック</div>
</div>

<div class="p-2 bg-gray-800 rounded text-center">
  <span class="font-bold text-white">モデル検査や性質ベーステストとの統合が改善方向</span>
</div>

</div>

<!--
見逃した7件の高/中重大度を分析しました。

最大カテゴリは「複雑状態遷移」で42.9%です。
例えば、長い状態遷移チェーンを経て初めて顕在化するバグは、静的な仕様チェックでは捕捉困難です。

次に「動的境界条件」が28.6%で、実行時に決まる境界値の問題です。

これらは、モデル検査や性質ベーステストとの統合が改善方向として示唆されます。

この分析に基づき、改善版V2を設計しました。
-->
