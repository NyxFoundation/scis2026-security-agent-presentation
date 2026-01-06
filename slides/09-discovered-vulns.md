---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 発見した脆弱性の実例：DoS攻撃のリスクを未然に防ぐ

<div class="text-sm text-gray-600 mb-3">
  具体的にどのような脆弱性を発見し、どのような被害を防いだのか
</div>

<div class="grid grid-cols-5 gap-4">

<div class="col-span-3 border-2 border-blue-500 rounded-lg p-3 bg-blue-50">
  <div class="flex items-center gap-2 mb-2">
    <span class="bg-blue-600 text-white px-2 py-0.5 rounded text-xs font-bold">Low</span>
    <span class="font-bold">#109: Nimbus custody rotation DoS</span>
  </div>

  <div class="bg-white p-2 rounded mb-2 text-sm">
    <strong class="text-blue-700">発見手法:</strong> 仕様ベース静的検査
  </div>

  <div class="grid grid-cols-2 gap-2 text-xs">
    <div class="bg-white p-2 rounded">
      <div class="font-bold text-gray-600 mb-1">仕様要件</div>
      <div>custody_group_count は<br><strong>128を超えてはならない</strong></div>
    </div>
    <div class="bg-white p-2 rounded">
      <div class="font-bold text-gray-600 mb-1">発見した実装不備</div>
      <div class="text-red-600">上限検証なしでループ条件に使用<br>→ 無限ループが発生可能</div>
    </div>
  </div>

  <div class="mt-2 p-2 bg-red-100 rounded text-xs">
    <strong>もし放置されていたら？</strong><br>
    攻撃者が不正な値を送信 → ノードが無限ループで停止 → ネットワークの一部がダウン
  </div>
</div>

<div class="col-span-2 space-y-2">
  <div class="text-xs font-bold text-gray-600 mb-1">その他の発見例（類似探索）</div>

  <div class="border rounded p-2 bg-gray-50 text-xs">
    <div class="flex items-center gap-1 mb-1">
      <span class="bg-gray-500 text-white px-1.5 py-0.5 rounded text-[10px]">Info</span>
      <span class="font-bold">#45: Erigon Tx残存</span>
    </div>
    <div class="text-gray-600">フォーク後も旧Txが残存しブロック構築を阻害</div>
  </div>

  <div class="border rounded p-2 bg-gray-50 text-xs">
    <div class="flex items-center gap-1 mb-1">
      <span class="bg-gray-500 text-white px-1.5 py-0.5 rounded text-[10px]">Info</span>
      <span class="font-bold">#31-33: Grandine backfill</span>
    </div>
    <div class="text-gray-600">Lodestarのパターンを横展開して発見</div>
  </div>

  <div class="border rounded p-2 bg-gray-50 text-xs">
    <div class="flex items-center gap-1 mb-1">
      <span class="bg-gray-500 text-white px-1.5 py-0.5 rounded text-[10px]">Info</span>
      <span class="font-bold">#27: Prysm status偽装</span>
    </div>
    <div class="text-gray-600">同期ノードが古いデータを要求し続ける</div>
  </div>

  <div class="mt-2 p-2 bg-green-50 rounded text-xs border border-green-300">
    <strong>共通点:</strong> 既知パターンの横展開が成功
  </div>
</div>

</div>

<!--
発見した脆弱性の具体例を紹介します。

左側は唯一のLow脆弱性である#109です。
これは「仕様ベース静的検査」で発見しました。

仕様書には「custody_group_countは128を超えてはならない」と明記されています。
しかしNimbusの実装では、この値を検証せずにループ条件として使用していました。

もしこのバグが放置されていたら、攻撃者が大きな値を送ることで無限ループが発生し、ノードが停止してネットワークの一部がダウンする可能性がありました。
これを未然に防いだことが、本研究の具体的な価値です。

右側は類似バグ探索で発見した例です。
Lodestarで見つかったパターンをGrandineに横展開するなど、一つの発見を複数のクライアントに適用することで効率的にバグを発見しました。
-->
