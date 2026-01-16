---
layout: center
---

# 高/中重大度脆弱性の検出率は0%だった

<div class="mt-6 text-sm">

<table class="mx-auto">
  <thead>
    <tr class="bg-slate-200">
      <th class="px-4 py-2 text-left border">重大度</th>
      <th class="px-4 py-2 text-center border">コンテスト全体</th>
      <th class="px-4 py-2 text-center border">私たちの発見</th>
      <th class="px-4 py-2 text-center border">検出率</th>
    </tr>
  </thead>
  <tbody>
    <tr class="bg-red-50">
      <td class="px-4 py-2 border font-bold">高</td>
      <td class="px-4 py-2 border text-center">5</td>
      <td class="px-4 py-2 border text-center">0</td>
      <td class="px-4 py-2 border text-center font-bold text-red-600">0%</td>
    </tr>
    <tr class="bg-red-50">
      <td class="px-4 py-2 border font-bold">中</td>
      <td class="px-4 py-2 border text-center">2</td>
      <td class="px-4 py-2 border text-center">0</td>
      <td class="px-4 py-2 border text-center font-bold text-red-600">0%</td>
    </tr>
    <tr>
      <td class="px-4 py-2 border">低</td>
      <td class="px-4 py-2 border text-center">8</td>
      <td class="px-4 py-2 border text-center">1</td>
      <td class="px-4 py-2 border text-center">12.5%</td>
    </tr>
  </tbody>
</table>

<div class="mt-6 flex justify-center">
  <div class="px-6 py-3 bg-red-100 rounded-lg border-2 border-red-400">
    <div class="text-2xl font-bold text-red-700 text-center">高/中: 0%</div>
    <div class="text-xs text-gray-600 text-center mt-1">根本的な限界を示唆</div>
  </div>
</div>

<div class="mt-4 flex justify-center">
  <div class="px-3 py-1 bg-slate-200 rounded border border-slate-300 text-center text-xs">
    <span class="text-gray-500">私たちの発見分布:</span>
    <span class="font-bold ml-1">低 1件 / 情報 16件</span>
  </div>
</div>

</div>

<!--
正直に限界を開示します。

高・中重大度の脆弱性について、私たちの検出率は0%でした。

コンテスト全体では高5件、中2件が発見されていましたが、私たちはいずれも見逃しています。

発見できたのは低1件と情報レベル16件のみでした。

この結果は、仕様チェックリスト駆動の監査に根本的な限界があることを示唆しています。

なぜ検出できなかったのか、分析しました。
-->
