---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 結果サマリー

<div class="text-sm text-gray-600 mb-3">
  Fusakaコンテストにおける我々の成績
</div>

<div class="grid grid-cols-2 gap-4">

<div>
  <div class="font-bold text-sm mb-2 text-center">報告件数と有効性</div>
  
  <div class="bg-blue-50 p-3 rounded-lg border border-blue-200 mb-3">
    <div class="grid grid-cols-3 gap-2 text-center">
      <div>
        <div class="text-2xl font-bold text-blue-700">54</div>
        <div class="text-xs text-gray-600">総報告数</div>
      </div>
      <div>
        <div class="text-2xl font-bold text-green-600">17</div>
        <div class="text-xs text-gray-600">Valid</div>
      </div>
      <div>
        <div class="text-2xl font-bold text-red-500">37</div>
        <div class="text-xs text-gray-600">Invalid</div>
      </div>
    </div>
    <div class="mt-2 text-center text-sm">
      <span class="text-green-600 font-bold">Valid率: 31.5%</span>
    </div>
  </div>

  <div class="bg-gray-50 p-2 rounded-lg text-xs">
    <div class="font-bold mb-1">重要度別 (Valid 17件)</div>
    <div class="grid grid-cols-4 gap-1 text-center">
      <div class="bg-red-100 p-1 rounded">
        <div class="font-bold text-red-600">0</div>
        <div class="text-[10px]">High</div>
      </div>
      <div class="bg-orange-100 p-1 rounded">
        <div class="font-bold text-orange-600">0</div>
        <div class="text-[10px]">Medium</div>
      </div>
      <div class="bg-yellow-100 p-1 rounded">
        <div class="font-bold text-yellow-600">1</div>
        <div class="text-[10px]">Low</div>
      </div>
      <div class="bg-blue-100 p-1 rounded">
        <div class="font-bold text-blue-600">16</div>
        <div class="text-[10px]">Info</div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-center">発見手法別の内訳</div>
  
  <div class="space-y-2">
    <div class="bg-green-50 p-2 rounded-lg border-l-4 border-green-500">
      <div class="flex justify-between items-center">
        <span class="font-bold text-sm">類似バグ探索</span>
        <span class="text-green-700 font-bold">13件 (76.5%)</span>
      </div>
      <div class="text-xs text-gray-600">既知パターンの横展開が最も効果的</div>
    </div>
    <div class="bg-blue-50 p-2 rounded-lg border-l-4 border-blue-500">
      <div class="flex justify-between items-center">
        <span class="font-bold text-sm">コード解析</span>
        <span class="text-blue-700 font-bold">3件 (17.6%)</span>
      </div>
      <div class="text-xs text-gray-600">仕様違反の静的検出</div>
    </div>
    <div class="bg-purple-50 p-2 rounded-lg border-l-4 border-purple-500">
      <div class="flex justify-between items-center">
        <span class="font-bold text-sm">Fuzzテスト</span>
        <span class="text-purple-700 font-bold">1件 (5.9%)</span>
      </div>
      <div class="text-xs text-gray-600">動的テストによる発見</div>
    </div>
  </div>

  <div class="mt-3 bg-yellow-50 p-2 rounded-lg border border-yellow-300">
    <div class="font-bold text-sm text-yellow-800 mb-1">監査者別 (Valid)</div>
    <div class="grid grid-cols-4 gap-1 text-center text-xs">
      <div class="bg-white p-1 rounded">
        <div class="font-bold">vita</div>
        <div class="text-yellow-700">8件</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold">gohan</div>
        <div class="text-yellow-700">7件</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold">adachi</div>
        <div class="text-yellow-700">1件</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold">tei</div>
        <div class="text-yellow-700">1件</div>
      </div>
    </div>
    <div class="text-[10px] text-gray-600 mt-1 text-center">
      非専門家(vita)が最多のバグを発見 → <strong>監査の民主化</strong>
    </div>
  </div>
</div>

</div>

<!--
結果サマリーです。

総報告数54件のうち、Valid判定は17件で、Valid率は31.5%でした。
重要度別では、High 0件、Medium 0件、Low 1件、Info 16件という結果でした。

発見手法別では、類似バグ探索が13件で76.5%と圧倒的に効果的でした。
コード解析が3件で17.6%、Fuzzテストが1件で5.9%でした。

監査者別では、非専門家のvitaが8件で最多、著者のgohanが7件、adachiとteiがそれぞれ1件でした。
特筆すべきは、非専門家のvitaが最多のバグを発見したことで、「監査の民主化」を実証しています。
-->
