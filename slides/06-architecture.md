---
layout: default
---

# 提案手法: 2フェーズ・3戦略

<div class="flex flex-col items-center gap-2 mt-2">

<!-- フェーズ1 -->
<div class="border-2 border-blue-400 rounded-lg p-3 w-full bg-blue-50">
<div class="font-bold text-blue-700 mb-2">フェーズ1: 知識構造化</div>
<div class="flex flex-col gap-2 text-sm">
<div class="flex items-center justify-center gap-2">
<span class="px-2 py-1 bg-white rounded border">仕様</span>
<span>→</span>
<span class="px-2 py-1 bg-white rounded border">要件抽出</span>
<span>→</span>
<span class="px-2 py-1 bg-yellow-100 rounded border border-yellow-400 font-bold">チェックリスト①</span>
</div>
<div class="flex items-center justify-center gap-2">
<span class="px-2 py-1 bg-white rounded border">各実装issue</span>
<span>→</span>
<span class="px-2 py-1 bg-white rounded border">パターン抽出</span>
<span>→</span>
<span class="px-2 py-1 bg-yellow-100 rounded border border-yellow-400 font-bold">チェックリスト②</span>
</div>
</div>
</div>

<div class="text-xl">↓</div>

<!-- フェーズ2 -->
<div class="border-2 border-green-400 rounded-lg p-3 w-full bg-green-50">
<div class="font-bold text-green-700 mb-2">フェーズ2: 体系的監査</div>
<div class="flex justify-center gap-6 text-sm">
<div class="px-3 py-1 bg-white rounded border text-center">
<span class="font-bold">戦略A: 静的監査</span><span class="text-gray-500"> (①)</span>
</div>
<div class="px-3 py-1 bg-white rounded border text-center">
<span class="font-bold">戦略B: 横展開</span><span class="text-gray-500"> (②)</span>
</div>
<div class="px-3 py-1 bg-white rounded border text-center">
<span class="font-bold">戦略C: 動的</span><span class="text-gray-500"> (①)</span>
</div>
</div>
</div>

<div class="text-xl">↓</div>

<span class="px-4 py-2 bg-purple-100 rounded-lg border-2 border-purple-400 font-bold">監査レポート</span>

</div>

<!--
本手法は2つのフェーズで構成されます。

フェーズ1は知識構造化です。2種類のチェックリストを作成します。1つ目は自然言語仕様から規範要件を抽出してチェックリスト化したもの。2つ目は各実装のissueをクローリングして脆弱性パターンを抽出したものです。

フェーズ2は体系的監査です。3つの戦略を適用します。戦略Aの静的監査と戦略Cの動的テストはチェックリスト①を使用します。戦略Bの横展開はチェックリスト②を使用し、ある実装で見つかった脆弱性パターンを他の実装にも適用します。

最終的に、証跡付きの監査レポートを生成します。
-->
