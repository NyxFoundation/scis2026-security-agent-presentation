---
layout: center
---

# 仕様からチェックリストを抽出し横展開することで盲点に対処する

<div class="mt-4 text-sm">

<div class="flex justify-center items-center gap-4 mb-6">
  <div class="w-24 h-16 bg-slate-200 rounded flex flex-col items-center justify-center border-2 border-slate-400 text-xs">
    <span class="font-bold">仕様書</span>
    <span class="text-gray-500">MUST/SHOULD</span>
  </div>
  <span class="text-2xl text-gray-400">→</span>
  <div class="w-28 h-18 bg-blue-100 rounded flex flex-col items-center justify-center border-2 border-blue-500 p-2 text-xs">
    <span class="font-bold text-blue-700">チェックリスト</span>
    <div class="text-left mt-1">
      <div>□ REQ-001</div>
      <div>□ REQ-002</div>
    </div>
  </div>
  <span class="text-2xl text-gray-400">→</span>
  <div class="space-y-1">
    <div class="w-20 h-6 bg-green-50 rounded flex items-center justify-center border border-green-400 text-xs">実装A ✓</div>
    <div class="w-20 h-6 bg-red-50 rounded flex items-center justify-center border border-red-400 text-xs">実装B ✗</div>
    <div class="w-20 h-6 bg-red-50 rounded flex items-center justify-center border border-red-400 text-xs">実装C ✗</div>
  </div>
</div>

<div class="grid grid-cols-2 gap-4 max-w-xl mx-auto mb-4">
  <div class="p-3 bg-slate-100 rounded border border-slate-300 text-xs">
    <div class="font-bold mb-1">差分テスト</div>
    <div class="text-gray-600">「実装同士の比較」に依存 → 全員が間違えると検出不可</div>
  </div>
  <div class="p-3 bg-blue-50 rounded border border-blue-300 text-xs">
    <div class="font-bold text-blue-700 mb-1">本研究</div>
    <div class="text-gray-700">「<strong>仕様を真実の源泉</strong>」として監査 → 発見を全実装に展開</div>
  </div>
</div>

<div class="flex justify-center gap-4">
  <span class="px-3 py-1 bg-gray-800 text-white rounded text-xs font-bold">仕様チェックリスト化</span>
  <span class="px-3 py-1 bg-gray-800 text-white rounded text-xs font-bold">横断実装チェック</span>
</div>

</div>

<!--
本研究の核心は、仕様の規範要件をチェックリストとして固定し、それを複数実装に適用することです。

差分テストが「実装同士の比較」に依存するのに対し、私たちは「仕様を真実の源泉」として監査します。

さらに、1つの実装で見つけた問題パターンを他の全実装に横展開する「横断実装チェック」により、発見効率を高めます。

このアイデアを実現するSpecAuditの設計をご説明します。
-->
