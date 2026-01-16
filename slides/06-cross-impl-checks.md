---
layout: default
---

# 横断実装チェックは1つの発見を複数実装に展開する

<div class="mt-4 text-sm">

<div class="flex justify-center items-center gap-3 mb-4">
  <div class="w-28 h-16 bg-red-50 rounded flex flex-col items-center justify-center border border-red-400 p-1 text-xs">
    <span class="font-bold">クライアントAで発見</span>
    <span class="text-red-600">スロットガード欠落</span>
  </div>
  <span class="text-xl text-gray-400">→</span>
  <div class="w-28 h-16 bg-blue-50 rounded flex flex-col items-center justify-center border border-blue-400 p-1 text-xs">
    <span class="font-bold">パターン抽象化</span>
    <span class="text-blue-600">「範囲ガード欠落」</span>
  </div>
  <span class="text-xl text-gray-400">→</span>
  <div class="space-y-0.5">
    <div class="w-24 h-5 bg-red-100 rounded flex items-center justify-center text-xs border border-red-300">クライアントB ✗</div>
    <div class="w-24 h-5 bg-red-100 rounded flex items-center justify-center text-xs border border-red-300">クライアントC ✗</div>
    <div class="w-24 h-5 bg-green-100 rounded flex items-center justify-center text-xs border border-green-300">クライアントD ✓</div>
  </div>
</div>

<table class="w-full text-xs mx-auto max-w-2xl">
  <thead>
    <tr class="bg-slate-200">
      <th class="px-2 py-1 text-left border">元の発見</th>
      <th class="px-2 py-1 text-left border">パターン</th>
      <th class="px-2 py-1 text-left border">横展開結果</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="px-2 py-1 border">クライアントA: スロットガード欠落</td>
      <td class="px-2 py-1 border">範囲ガード欠落</td>
      <td class="px-2 py-1 border text-red-600">B, C 同様に欠落</td>
    </tr>
    <tr class="bg-slate-100">
      <td class="px-2 py-1 border">クライアントC: バッチ境界不整合</td>
      <td class="px-2 py-1 border">配列境界チェック</td>
      <td class="px-2 py-1 border text-red-600">A でも発見</td>
    </tr>
    <tr>
      <td class="px-2 py-1 border">クライアントB: 上限値未適用</td>
      <td class="px-2 py-1 border">上限値検証</td>
      <td class="px-2 py-1 border text-red-600">3クライアントで追加発見</td>
    </tr>
  </tbody>
</table>

<div class="mt-4 p-3 bg-gray-800 rounded text-center text-sm">
  <span class="font-bold text-white">仕様の曖昧な部分は複数チームが同様に誤解しやすい</span>
  <span class="text-gray-300 ml-2">→ 1つの発見が複数の発見に繋がる</span>
</div>

</div>

<!--
横断実装チェックの仕組みを説明します。

まず、ある実装で問題を発見したら、その問題を抽象的なパターンとして一般化します。
例えば「最古スロットガードの欠落」は「範囲ガード欠落パターン」になります。

次に、このパターンを他の全実装で検索します。

仕様の曖昧な部分は複数チームが同様に誤解しやすいため、1つの発見が複数の発見に繋がります。

この手法を実運用環境で評価しました。
-->
