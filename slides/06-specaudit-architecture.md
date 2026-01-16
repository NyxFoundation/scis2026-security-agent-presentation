---
layout: default
---

# SpecAuditは2フェーズ・3戦略で仕様準拠を体系的に監査する

<div class="flex flex-col items-center gap-3 mt-4">

<!-- フェーズ1 -->
<div class="border-2 border-blue-400 rounded-lg p-3 w-full max-w-2xl bg-blue-50">
<div class="text-sm font-bold text-blue-700 mb-2">フェーズ1: 知識構造化</div>
<div class="flex items-center justify-center gap-2 text-sm">
<span class="px-2 py-1 bg-white rounded border">仕様文書</span>
<span>→</span>
<span class="px-2 py-1 bg-white rounded border">規範要件抽出</span>
<span>→</span>
<span class="px-2 py-1 bg-white rounded border">実装マッピング</span>
<span>→</span>
<span class="px-2 py-1 bg-yellow-100 rounded border border-yellow-400">パターンDB</span>
</div>
</div>

<div class="text-2xl">↓</div>

<!-- フェーズ2 -->
<div class="border-2 border-green-400 rounded-lg p-3 w-full max-w-2xl bg-green-50">
<div class="text-sm font-bold text-green-700 mb-2">フェーズ2: 体系的監査</div>
<div class="flex justify-center gap-4 text-sm">
<span class="px-3 py-1 bg-white rounded border">戦略A: 静的監査</span>
<span class="px-3 py-1 bg-white rounded border">戦略B: 横展開</span>
<span class="px-3 py-1 bg-white rounded border">戦略C: 動的テスト</span>
</div>
</div>

<div class="text-2xl">↓</div>

<span class="px-4 py-2 bg-purple-100 rounded-lg border-2 border-purple-400 font-bold">監査レポート</span>

</div>

<div class="mt-3 text-center">

監査を**再現可能な工程**と**証跡付き成果物**として固定

</div>

<!--
SpecAuditは2つのフェーズで構成されます。

フェーズ1は知識構造化で、自然言語仕様から規範要件を抽出し、それをコードにマッピングし、既知の脆弱性パターンをデータベース化します。

フェーズ2は体系的監査で、3つの戦略を適用します。各戦略については次のスライドで詳しく説明します。

最終的に、証跡付きの監査レポートを生成し、人間による検証を支援します。重要なのは、監査を再現可能な工程と成果物として固定している点です。
-->
