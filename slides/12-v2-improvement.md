---
layout: two-cols
layoutClass: gap-6
---

# V2では脅威モデルを事前形式化して偽陽性を抑制する

<div class="text-xs mt-4">

<div class="p-2 bg-slate-200 rounded border border-slate-300 mb-3">
  <div class="font-bold text-gray-700 mb-1">V1: 暗黙の脅威仮定</div>
  <div class="flex items-center gap-1">
    <span class="px-2 py-0.5 bg-white rounded border text-xs">監査実行</span>
    <span class="text-gray-400">→</span>
    <span class="px-2 py-0.5 bg-red-100 rounded border border-red-300 text-red-700 text-xs">56.8% 偽陽性</span>
  </div>
</div>

<div class="p-2 bg-blue-50 rounded border border-blue-300">
  <div class="font-bold text-blue-700 mb-1">V2: 信頼モデル形式化</div>
  <div class="flex items-center gap-1 flex-wrap">
    <span class="px-2 py-0.5 bg-white rounded border border-blue-300 text-xs">信頼モデル定義</span>
    <span class="text-gray-400">→</span>
    <span class="px-2 py-0.5 bg-white rounded border border-blue-300 text-xs">フィルタリング</span>
    <span class="text-gray-400">→</span>
    <span class="px-2 py-0.5 bg-green-100 rounded border border-green-300 text-green-700 text-xs">偽陽性削減</span>
  </div>
</div>

</div>

::right::

<div class="text-xs mt-16">

<div class="p-2 bg-slate-100 rounded border border-slate-300">
  <div class="font-bold mb-1">信頼モデルの構造例</div>
  <div class="font-mono bg-white p-2 rounded border text-xs overflow-hidden">
    <div class="text-gray-500">// TRUSTMODEL.json</div>
    <div>{</div>
    <div class="ml-2">"actors": ["バリデータ",</div>
    <div class="ml-4">"ビルダー", "P2Pピア"],</div>
    <div class="ml-2">"trust_levels": [</div>
    <div class="ml-4">"信頼", "半信頼", "非信頼"],</div>
    <div class="ml-2">"boundary_edges": [...]</div>
    <div>}</div>
  </div>
</div>

<div class="mt-2 p-2 bg-yellow-50 rounded border border-yellow-300 text-center">
  <span class="font-bold text-yellow-700">注意:</span> V2は設計提案であり、本論文では実証評価は未実施
</div>

</div>

<!--
偽陽性分析に基づき、V2では信頼モデルの形式化を導入しました。

監査開始前に、アクター、信頼レベル、境界エッジを明示的に定義します。

これにより、コンテストルールと矛盾する前提に基づく指摘を事前にフィルタリングできます。

なお、V2は設計提案であり、本論文では実証評価は行っていません。
今後の検証課題として位置づけています。

最後に、本研究の持ち帰りメッセージをまとめます。
-->
