---
layout: two-cols
layoutClass: gap-6
---

# 横断実装チェックが有効発見の76.5%を占めた

<div class="text-xs mt-4">

| 戦略 | 有効発見数 | 割合 |
|------|---:|---:|
| **横断実装チェック** | **13** | **76.5%** |
| 仕様ベース静的監査 | 3 | 17.6% |
| 動的テスト生成 | 1 | 5.9% |
| **合計** | **17** | **100%** |

<div class="mt-3 p-2 bg-blue-50 rounded border border-blue-200">
  <div class="font-bold text-blue-700">私たちの成績</div>
  <div class="mt-1">
    提出: 54件 → 有効: 17件<br>
    <span class="font-bold">有効率 31.5%</span>（全体平均 27.6% を上回る）
  </div>
</div>

</div>

::right::

<div class="mt-16 flex items-end justify-center gap-6 h-44">
  <div class="text-center">
    <div class="w-16 bg-green-500 rounded-t" style="height: 160px;"></div>
    <div class="mt-1 font-bold text-sm">76.5%</div>
    <div class="text-xs text-gray-500">横断実装</div>
  </div>
  <div class="text-center">
    <div class="w-16 bg-gray-400 rounded-t" style="height: 37px;"></div>
    <div class="mt-1 font-bold text-sm">17.6%</div>
    <div class="text-xs text-gray-500">静的監査</div>
  </div>
  <div class="text-center">
    <div class="w-16 bg-gray-300 rounded-t" style="height: 12px;"></div>
    <div class="mt-1 font-bold text-sm">5.9%</div>
    <div class="text-xs text-gray-500">動的テスト</div>
  </div>
</div>

<div class="mt-2 p-2 bg-gray-800 rounded text-center text-xs">
  <span class="text-white font-bold">仕様チェックリストの横展開が多実装環境で極めて有効</span>
</div>

<!--
主要な結果です。

私たちの54件の提出のうち17件が有効と判定され、有効率は31.5%でした。

戦略別に見ると、横断実装チェックが76.5%、つまり17件中13件を占めています。
仕様ベース静的監査は17.6%、動的テストは5.9%でした。

この結果は、仕様チェックリストの横展開が多実装環境で極めて有効であることを示しています。

一方で、37件が無効と判定されました。その原因を分析します。
-->
