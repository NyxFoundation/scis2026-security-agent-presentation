---
layout: two-cols
layoutClass: gap-6
---

# 偽陽性の56.8%は脅威モデル不整合に起因した

<div class="text-xs mt-4">

| 原因カテゴリ | 件数 | 割合 |
|------------|---:|---:|
| **脅威モデル不整合** | **21** | **56.8%** |
| 既知 / 重複 | 8 | 21.6% |
| 分析エラー | 5 | 13.5% |
| スコープ外 | 3 | 8.1% |
| **合計** | **37** | **100%** |

<div class="mt-3 p-2 bg-yellow-50 rounded border border-yellow-300">
  <div class="font-bold text-yellow-700">具体例</div>
  <div class="mt-1 grid grid-cols-2 gap-1">
    <div class="p-1 bg-white rounded border text-xs">
      <div class="font-bold">私たちのプロンプト</div>
      <div class="text-red-600">ELは信頼しない</div>
    </div>
    <div class="p-1 bg-white rounded border text-xs">
      <div class="font-bold">コンテストルール</div>
      <div class="text-green-600">ELは信頼コンポーネント</div>
    </div>
  </div>
</div>

</div>

::right::

<div class="mt-16 flex items-center justify-center">
  <div class="relative w-36 h-36">
    <div class="absolute inset-0 rounded-full border-8 border-red-400"></div>
    <div class="absolute inset-0 flex items-center justify-center flex-col">
      <div class="text-3xl font-bold text-red-600">56.8%</div>
      <div class="text-xs text-gray-600 text-center">脅威モデル<br>不整合</div>
    </div>
  </div>
</div>

<div class="mt-4 p-2 bg-gray-800 rounded text-center text-xs">
  <div class="font-bold text-white">LLMの推論能力の問題ではなく、事前の前提条件設定の問題</div>
  <div class="text-gray-300">→ 工程改善で対処可能</div>
</div>

<!--
無効37件の原因を分析したところ、最大カテゴリは「脅威モデル不整合」で56.8%、21件でした。

具体的には、私たちのプロンプトはエグゼキューション層を信頼しない設定でしたが、
コンテストルールではELは信頼コンポーネントと定義されていました。

この前提のズレにより、「ELが悪意を持つ」シナリオに基づく報告が全て無効となりました。

重要なのは、これはLLMの推論能力の問題ではなく、事前の前提条件設定の問題だということです。

では、高重大度のバグについてはどうだったでしょうか。
-->
