---
layout: two-cols
layoutClass: gap-6
---

# SpecAuditは2フェーズ・3戦略で監査を体系化する

<div class="text-xs mt-2">

<div class="p-3 bg-blue-50 rounded border border-blue-300 mb-3">
  <div class="font-bold text-blue-700 mb-2">フェーズ1: 知識構造化</div>
  <div class="space-y-1">
    <div class="flex items-center gap-2 bg-white p-1 rounded">
      <span class="w-5 h-5 bg-blue-200 rounded-full text-xs flex items-center justify-center">1</span>
      <span>仕様書（自然言語）</span>
    </div>
    <div class="text-center text-blue-400">↓</div>
    <div class="flex items-center gap-2 bg-white p-1 rounded">
      <span class="w-5 h-5 bg-blue-200 rounded-full text-xs flex items-center justify-center">2</span>
      <span>規範要件抽出</span>
    </div>
    <div class="text-center text-blue-400">↓</div>
    <div class="flex items-center gap-2 bg-white p-1 rounded">
      <span class="w-5 h-5 bg-blue-200 rounded-full text-xs flex items-center justify-center">3</span>
      <span>パターンDB構築</span>
    </div>
  </div>
</div>

</div>

::right::

<div class="text-xs mt-16">

<div class="p-3 bg-green-50 rounded border border-green-300">
  <div class="font-bold text-green-700 mb-2">フェーズ2: 体系的監査</div>
  <div class="space-y-1">
    <div class="flex items-center gap-2 bg-white p-1 rounded">
      <span class="w-5 h-5 bg-green-200 rounded-full text-xs flex items-center justify-center">A</span>
      <span>仕様ベース静的監査</span>
    </div>
    <div class="flex items-center gap-2 bg-white p-1 rounded border-2 border-green-500">
      <span class="w-5 h-5 bg-green-400 text-white rounded-full text-xs flex items-center justify-center">B</span>
      <span class="text-green-700 font-bold">横断実装チェック</span>
    </div>
    <div class="flex items-center gap-2 bg-white p-1 rounded">
      <span class="w-5 h-5 bg-green-200 rounded-full text-xs flex items-center justify-center">C</span>
      <span>動的テスト生成</span>
    </div>
  </div>
</div>

<div class="mt-3 p-2 bg-slate-200 rounded border border-slate-300">
  <div class="font-bold mb-1">生成される成果物</div>
  <div class="flex flex-wrap gap-1">
    <span class="px-2 py-0.5 bg-white rounded border text-xs">規範要件ID</span>
    <span class="px-2 py-0.5 bg-white rounded border text-xs">実装マッピング</span>
    <span class="px-2 py-0.5 bg-white rounded border text-xs">チェックリスト</span>
    <span class="px-2 py-0.5 bg-white rounded border text-xs">監査レポート</span>
  </div>
</div>

</div>

<!--
SpecAuditは2つのフェーズで構成されます。

フェーズ1では自然言語仕様から規範要件を抽出し、実装コードへのマッピングを構築します。

フェーズ2では3つの戦略で監査を実行します。
戦略Aは仕様に基づく直接検証、戦略Bは発見パターンの横展開、戦略Cは動的テスト生成です。

すべての工程で検査可能な成果物を生成し、再現性を担保します。

特に重要なのが戦略B、横断実装チェックです。
-->
