---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 提案：熟練監査員の思考を自動化する「AI監査エージェント」

<div class="text-sm text-gray-600 mb-2">
  単なる自動化ツールではなく、<strong>トップレベル専門家の知見をスケールさせる</strong>
</div>

<div class="grid grid-cols-2 gap-4">

<div>
  <div class="font-bold text-blue-700 mb-1 text-sm">Phase 1: 準備（知識の構造化）</div>
  <div class="p-2 bg-gray-50 rounded-lg text-xs space-y-1">
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-blue-100 rounded flex items-center justify-center text-xs">1</span>
      <span>仕様書 (EIP) から要件を抽出</span>
    </div>
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-blue-100 rounded flex items-center justify-center text-xs">2</span>
      <span>実装コードへのマッピング</span>
    </div>
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-blue-100 rounded flex items-center justify-center text-xs">3</span>
      <span>チェックリスト・類似バグリスト作成</span>
    </div>
  </div>

  <div class="font-bold text-green-700 mb-1 mt-2 text-sm">Phase 2: 監査（3戦略の並行実行）</div>
  <div class="p-2 bg-gray-50 rounded-lg text-xs space-y-1">
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-green-100 rounded flex items-center justify-center text-xs">A</span>
      <span>仕様ベース静的検査</span>
    </div>
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-green-100 rounded flex items-center justify-center text-xs">B</span>
      <span>類似バグ探索</span>
    </div>
    <div class="flex items-center gap-2">
      <span class="w-5 h-5 bg-green-100 rounded flex items-center justify-center text-xs">C</span>
      <span>動的テスト生成</span>
    </div>
  </div>
</div>

<div class="p-3 bg-blue-50 rounded-lg border border-blue-200">
  <div class="font-bold text-sm mb-2 text-center text-blue-800">処理フロー</div>
  <div class="text-xs space-y-2">
    <div class="flex items-center gap-2">
      <span class="bg-blue-200 px-2 py-0.5 rounded">仕様書</span>
      <span>→</span>
      <span class="bg-blue-200 px-2 py-0.5 rounded">仕様抽出</span>
      <span>→</span>
      <span class="bg-blue-200 px-2 py-0.5 rounded">実装マッピング</span>
    </div>
    <div class="text-center text-gray-400">↓</div>
    <div class="flex justify-center gap-4">
      <span class="bg-blue-100 px-2 py-0.5 rounded border border-blue-300">チェックリスト</span>
      <span class="bg-blue-100 px-2 py-0.5 rounded border border-blue-300">類似バグリスト</span>
    </div>
    <div class="text-center text-gray-400">↓</div>
    <div class="flex justify-center gap-2">
      <span class="bg-green-100 px-1.5 py-0.5 rounded text-xs">仕様検査</span>
      <span class="bg-green-100 px-1.5 py-0.5 rounded text-xs">類似探索</span>
      <span class="bg-green-100 px-1.5 py-0.5 rounded text-xs">動的テスト</span>
    </div>
    <div class="text-center text-gray-400">↓</div>
    <div class="flex justify-center">
      <span class="bg-yellow-200 px-3 py-1 rounded font-bold">レポート出力</span>
    </div>
  </div>
</div>

</div>

<!--
提案するAI監査エージェントの概要です。

本手法は単なる自動化ツールではありません。
トップレベルの専門家の知見をスケールさせることを目的としています。

Phase 1の準備フェーズでは、仕様書から要件を抽出し、実装へのマッピングを行い、チェックリストと類似バグリストを作成します。

Phase 2の監査フェーズでは、3つの戦略を並行実行します。
仕様ベース静的検査、類似バグ探索、動的テスト生成です。
各戦略の結果は検証・PoC作成を経て、最終レポートに統合されます。
-->
