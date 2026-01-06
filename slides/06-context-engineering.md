---
layout: default
---

# コンテキストエンジニアリング

数百万行規模のコードベースをLLMの限られたコンテキストウィンドウで扱うための工夫。

<div class="grid grid-cols-2 gap-6 mt-4">

<div>
  <div class="p-3 border-l-4 border-blue-500 bg-gray-50 mb-3">
    <div class="font-bold text-sm">1. 仕様サマリと脅威モデルの一本化</div>
    <div class="text-xs mt-1">各要件に一意な識別子 (Normative ID) を付与。後続モジュールはIDで仕様参照 → ハルシネーション低減</div>
  </div>

  <div class="p-3 border-l-4 border-green-500 bg-gray-50 mb-3">
    <div class="font-bold text-sm">2. スコープ縮小</div>
    <div class="text-xs mt-1">プロジェクト全体ではなく、仕様IDに関連する関数のみを抽出してLLMに入力</div>
  </div>

  <div class="p-3 border-l-4 border-purple-500 bg-gray-50 mb-3">
    <div class="font-bold text-sm">3. 粒度制御</div>
    <div class="text-xs mt-1">数十行規模のスニペット単位でコンテキストを切り出し、深い論理的推論を可能に</div>
  </div>

  <div class="p-3 border-l-4 border-orange-500 bg-gray-50">
    <div class="font-bold text-sm">4. 状態管理</div>
    <div class="text-xs mt-1">各工程の入出力をJSONで永続化。セッション再起動で履歴肥大化を防止</div>
  </div>
</div>

<div class="text-sm">

```json
// 仕様抽出の出力例 (01_SPEC.json)
{
  "spec_id": "PEERDAS-CUSTODY-001",
  "requirement": "custody_group_count は
    NUMBER_OF_CUSTODY_GROUPS (128) を
    超えてはならない",
  "priority": "high",
  "related_eips": ["EIP-7594"]
}
```

```json
// 実装マッピングの出力例 (02_ORDER.json)
{
  "spec_id": "PEERDAS-CUSTODY-001",
  "files": [
    "beacon_chain/peerdas_helpers.nim:42",
    "beacon_chain/gossip_processing.nim:128"
  ]
}
```

</div>

</div>

<!--
技術的な工夫として「コンテキストエンジニアリング」を行っています。
数百万行あるコードを全てLLMに読ませるのではなく、特定の仕様IDに関連する関数のみを抽出して渡すことで、探索範囲を適切に絞り込んでいます。
また、各工程の出力をJSONで永続化し、セッションを再起動しても必要な情報を引き継げる設計としています。
右側にJSONの出力例を示しています。仕様抽出の結果と、それに対応する実装ファイルのマッピングがこのように管理されます。
-->
