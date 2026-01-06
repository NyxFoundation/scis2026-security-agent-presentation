---
layout: default
---

# 発見した脆弱性の例

<div class="grid grid-cols-2 gap-6 mt-2">

<div class="border-2 border-blue-400 rounded-lg p-4 bg-blue-50">
  <div class="flex items-center gap-2 mb-2">
    <span class="bg-blue-600 text-white px-2 py-0.5 rounded text-xs">Low</span>
    <span class="font-bold">#109: Nimbus custody rotation DoS</span>
  </div>
  <div class="text-sm mb-2">
    <strong>手法:</strong> 仕様ベース静的検査
  </div>
  <div class="text-xs bg-white p-2 rounded mb-2">
    <strong>仕様要件:</strong> custody_group_count は NUMBER_OF_CUSTODY_GROUPS (128) を超えてはならない
  </div>
  <div class="text-xs bg-white p-2 rounded">
    <strong>発見した実装不備:</strong><br>
    <code class="text-red-600">while custody_groups.lenu64 < custody_group_count:</code><br>
    上限検証なしにループ条件で使用 → 無限ループによるDoS
  </div>
</div>

<div class="space-y-3">

<div class="border rounded-lg p-3 bg-gray-50">
  <div class="flex items-center gap-2 mb-1">
    <span class="bg-gray-500 text-white px-2 py-0.5 rounded text-xs">Info</span>
    <span class="font-bold text-sm">#45: Erigon pre-Osaka高ガスTx</span>
  </div>
  <div class="text-xs">
    <strong>手法:</strong> 類似探索 | フォーク後も旧Txが残存しブロック構築を阻害
  </div>
</div>

<div class="border rounded-lg p-3 bg-gray-50">
  <div class="flex items-center gap-2 mb-1">
    <span class="bg-gray-500 text-white px-2 py-0.5 rounded text-xs">Info</span>
    <span class="font-bold text-sm">#31-33: Grandine backfill系バグ</span>
  </div>
  <div class="text-xs">
    <strong>手法:</strong> 類似探索 | Lodestarで発見したパターンを横展開
  </div>
</div>

<div class="border rounded-lg p-3 bg-gray-50">
  <div class="flex items-center gap-2 mb-1">
    <span class="bg-gray-500 text-white px-2 py-0.5 rounded text-xs">Info</span>
    <span class="font-bold text-sm">#27: Prysm status応答偽装</span>
  </div>
  <div class="text-xs">
    <strong>手法:</strong> 類似探索 | 同期ノードが古いデータを要求し続ける
  </div>
</div>

</div>

</div>

<div class="mt-3 p-2 bg-yellow-50 rounded text-xs text-center">
  <strong>共通点:</strong> 類似探索で発見したバグは「既知パターンの横展開」が成功要因
</div>

<!--
発見した脆弱性の具体例を紹介します。

左側は唯一のLow脆弱性である#109です。
これは「仕様ベース静的検査」で発見しました。
仕様書には「custody_group_countは128を超えてはならない」と明記されているのに対し、Nimbusの実装では検証なしにループ条件として使用していました。
攻撃者が大きな値を送ると無限ループが発生し、DoS攻撃が可能になります。

右側は類似バグ探索で発見したInfoレベルの脆弱性です。
例えば#31-33は、Lodestarで発見したbackfill関連のバグパターンを、Grandineに横展開して発見しました。
このように、一つのクライアントで見つけたパターンを他に適用する戦略が非常に効果的でした。
-->
