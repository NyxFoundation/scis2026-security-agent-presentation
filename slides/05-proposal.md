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

<div class="absolute bottom-2 left-2 text-[8px] text-gray-400 max-w-[90%] leading-relaxed">
  <div><strong class="text-gray-500">[LLM監査の先行研究]</strong> RepoAudit: https://arxiv.org/abs/2501.18160 | LLM4Vuln: https://arxiv.org/abs/2401.16185</div>
</div>

<!--
提案手法である「AI監査エージェント」のアーキテクチャについて説明します。

本手法の核心は、単なるツール実行の自動化ではなく、「熟練監査員の思考プロセス」の構造化にあります。

Phase 1は「知識の構造化」フェーズです。
仕様書（EIP）から要件を構造データとして抽出し、実装コードとマッピングを行います。これにより、AIが「何を検証すべきか」を正確に理解できる状態を作ります。

Phase 2は「監査の実行」フェーズです。
ここでは「仕様ベース静的検査」「類似バグ探索」「動的テスト生成」という、監査員が実際に行う3つの戦略を並行して実行させます。

このように、人間の専門知見をプロンプトとして形式化し、それをAIによってスケールさせることが本研究の狙いです。
-->
