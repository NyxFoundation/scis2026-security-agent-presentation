---
layout: center
---

# 複数実装が「同じ誤解」を共有すると既存手法では検出できない

<div class="mt-6 text-sm">

<div class="flex justify-center mb-4">
  <div class="w-20 h-16 bg-slate-200 rounded flex flex-col items-center justify-center border-2 border-slate-400">
    <span class="text-lg">📄</span>
    <span class="text-xs">仕様書</span>
  </div>
</div>

<div class="flex justify-center items-center gap-4 mb-4">
  <div class="text-center">
    <div class="w-16 h-14 bg-blue-50 rounded flex items-center justify-center border border-blue-300 text-xs font-bold">実装A</div>
    <div class="text-xs text-red-500">誤解 ✗</div>
  </div>
  <span class="text-2xl text-gray-300">↔</span>
  <div class="text-center">
    <div class="w-16 h-14 bg-blue-50 rounded flex items-center justify-center border border-blue-300 text-xs font-bold">実装B</div>
    <div class="text-xs text-red-500">誤解 ✗</div>
  </div>
  <span class="text-2xl text-gray-300">↔</span>
  <div class="text-center">
    <div class="w-16 h-14 bg-blue-50 rounded flex items-center justify-center border border-blue-300 text-xs font-bold">実装C</div>
    <div class="text-xs text-red-500">誤解 ✗</div>
  </div>
</div>

<div class="flex justify-center mb-4">
  <div class="px-4 py-2 bg-yellow-100 rounded border border-yellow-400 text-center text-xs">
    <div class="font-bold">差分テスト結果: すべて「差分なし」</div>
    <div class="text-gray-600">→ バグは見逃される</div>
  </div>
</div>

<div class="flex justify-center mb-3">
  <div class="px-6 py-3 bg-red-100 rounded-lg border-2 border-red-400">
    <div class="text-xl font-bold text-red-700">意味的盲点</div>
    <div class="text-xs text-gray-600">Semantic Blind Spot</div>
  </div>
</div>

<div class="text-center text-xs text-gray-500">
  Knight & Leveson 1986「独立実装でも相関故障は起きる」
</div>

</div>

<!--
差分ファジングは複数実装の挙動差をオラクルとして活用する強力な手法です。

しかし、根本的な限界があります。すべての実装が同じ仕様の曖昧さを同じ方向に誤解していた場合、挙動の差分が出ないため、バグは見逃されます。

私たちはこれを「意味的盲点」と呼びます。

1986年のKnight & Levesonの研究でも、独立に開発された実装が共通して失敗する現象が報告されています。

この盲点に対処するのが、本研究の核心的アイデアです。
-->
