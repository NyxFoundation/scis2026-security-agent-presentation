---
layout: two-cols
layoutClass: gap-8
---

# LLMエージェントは監査のボトルネックを解消しうる

<div class="text-sm mt-4">

**従来の監査フロー（手動）**

<div class="space-y-2 mt-2">
  <div class="flex items-center gap-2">
    <span class="w-6 h-6 bg-blue-200 rounded-full text-xs flex items-center justify-center">1</span>
    <span>仕様書を読解</span>
  </div>
  <div class="flex items-center gap-2">
    <span class="w-6 h-6 bg-blue-200 rounded-full text-xs flex items-center justify-center">2</span>
    <span>要件を抽出</span>
  </div>
  <div class="flex items-center gap-2">
    <span class="w-6 h-6 bg-blue-200 rounded-full text-xs flex items-center justify-center">3</span>
    <span>コードへ対応付け</span>
  </div>
  <div class="flex items-center gap-2">
    <span class="w-6 h-6 bg-blue-200 rounded-full text-xs flex items-center justify-center">4</span>
    <span>検証・レポート</span>
  </div>
</div>

<div class="mt-3 p-2 bg-red-50 rounded text-xs border border-red-200">
  <span class="text-red-600 font-bold">課題:</span> 属人的・高コスト・スケールしない
</div>

</div>

::right::

<div class="text-sm mt-16">

**多実装環境の現実**

<div class="grid grid-cols-4 gap-1 my-3">
  <img src="/images/eth_nimbus.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_lighthouse.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_prysm.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_teku.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_geth.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_reth.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_erigon.png" class="w-8 h-8 mx-auto" />
  <img src="/images/eth_besu.png" class="w-8 h-8 mx-auto" />
</div>

<div class="text-center p-3 bg-slate-200 rounded border border-slate-300">
  <div class="text-2xl font-bold">11 クライアント</div>
  <div class="text-gray-600 text-xs">× 数万行のコード</div>
  <div class="text-red-600 font-bold mt-1">= 手動監査の限界</div>
</div>

<div class="mt-3 p-2 bg-blue-50 rounded text-xs border border-blue-200">
  <span class="text-blue-600 font-bold">LLMエージェント:</span> 反復的な知識作業を支援
</div>

</div>

<!--
高信頼ソフトウェアの監査は、自然言語仕様の読解、要件抽出、コードへの対応付けという属人的で高コストな作業を要します。

特に多実装環境では、同じ仕様を11ものチームが独立に実装しており、手動での網羅的検証は現実的ではありません。

LLMエージェントは、この反復的な知識作業を支援できる可能性があります。

しかし、多実装環境には特有の難しさがあります。
-->
