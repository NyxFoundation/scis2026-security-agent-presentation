---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 発見した脆弱性の実例：DoS攻撃のリスクを未然に防ぐ

<div class="text-sm text-gray-600 mb-2">
  具体的にどのような脆弱性を発見し、どのような被害を防いだのか
</div>

<div class="grid grid-cols-2 gap-3">

<div class="border-2 border-primary rounded-lg p-2 bg-primary-bg">
  <div class="flex items-center gap-2 mb-2">
    <span class="bg-yellow-600 text-white px-2 py-0.5 rounded text-xs font-bold">Low</span>
    <span class="font-bold text-sm">#109: Nimbus custody rotation DoS</span>
  </div>

  <div class="bg-white p-1.5 rounded mb-2 text-xs">
    <strong class="text-primary">発見手法:</strong> コード解析（仕様ベース静的検査）
  </div>

  <div class="grid grid-cols-2 gap-2 text-[10px]">
    <div class="bg-white p-1.5 rounded">
      <div class="font-bold text-gray-600 mb-1">仕様要件</div>
      <div>custody_group_count は<br><strong>128を超えてはならない</strong></div>
    </div>
    <div class="bg-white p-1.5 rounded">
      <div class="font-bold text-gray-600 mb-1">発見した実装不備</div>
      <div class="text-red-600">handle_custody_groupsが<br>値を検証せず受け入れ</div>
    </div>
  </div>

  <div class="mt-2 p-1.5 bg-red-50 rounded text-[10px] border border-red-200">
    <strong>影響:</strong> 攻撃者が不正な値を送信 → ノードが異常値を流す → ネットワーク障害
  </div>
</div>

<div class="border-2 border-green-400 rounded-lg p-2 bg-green-50">
  <div class="flex items-center gap-2 mb-2">
    <span class="bg-green-600 text-white px-2 py-0.5 rounded text-xs font-bold">類似探索</span>
    <span class="font-bold text-sm">横展開で発見した脆弱性群</span>
  </div>

  <div class="space-y-1.5 text-[10px]">
    <div class="bg-white p-1.5 rounded border">
      <div class="font-bold">#28-30: Nimbus blob/column上限</div>
      <div class="text-gray-600">スロット数制限だけでblob合計を制御できず大量送信を許容</div>
    </div>
    <div class="bg-white p-1.5 rounded border">
      <div class="font-bold">#31-33: Grandine backfill系</div>
      <div class="text-gray-600">earliest_available_slot比較ミスで保持外の列を要求し続ける</div>
    </div>
    <div class="bg-white p-1.5 rounded border">
      <div class="font-bold">#19: Lodestar ByRange</div>
      <div class="text-gray-600">保持範囲外リクエストを弾けずDoSになる（Fuzz発見）</div>
    </div>
  </div>

  <div class="mt-1.5 p-1.5 bg-yellow-100 rounded text-[10px] border border-yellow-300">
    <strong>共通点:</strong> 既知パターン（範囲チェック漏れ）の横展開が成功
  </div>
</div>

</div>

<div class="mt-2 p-2 bg-gray-100 rounded-lg">
  <div class="font-bold text-sm mb-1">Valid判定された全17件の内訳</div>
  <div class="grid grid-cols-9 gap-1 text-[9px]">
    <div class="bg-blue-100 p-1 rounded text-center">
      <div class="font-bold">Nimbus</div>
      <div>6件</div>
    </div>
    <div class="bg-green-100 p-1 rounded text-center">
      <div class="font-bold">Grandine</div>
      <div>3件</div>
    </div>
    <div class="bg-purple-100 p-1 rounded text-center">
      <div class="font-bold">Erigon</div>
      <div>2件</div>
    </div>
    <div class="bg-orange-100 p-1 rounded text-center">
      <div class="font-bold">Besu</div>
      <div>1件</div>
    </div>
    <div class="bg-pink-100 p-1 rounded text-center">
      <div class="font-bold">Lodestar</div>
      <div>1件</div>
    </div>
    <div class="bg-teal-100 p-1 rounded text-center">
      <div class="font-bold">Nethermind</div>
      <div>1件</div>
    </div>
    <div class="bg-indigo-100 p-1 rounded text-center">
      <div class="font-bold">Teku</div>
      <div>1件</div>
    </div>
    <div class="bg-amber-100 p-1 rounded text-center">
      <div class="font-bold">Prysm</div>
      <div>1件</div>
    </div>
    <div class="bg-lime-100 p-1 rounded text-center">
      <div class="font-bold">Reth</div>
      <div>1件</div>
    </div>
  </div>
</div>

<!--
発見した脆弱性の具体例を紹介します。

左側は#109、Nimbusのcustody rotation DoS脆弱性です。
これは「コード解析」で発見しました。

仕様書には「custody_group_countは128を超えてはならない」と明記されています。
しかしNimbusのhandle_custody_groups関数では、この値を検証せずに受け入れていました。
もしこのバグが放置されていたら、攻撃者が不正な値を送ることでノードが異常値を流し、ネットワーク障害を引き起こす可能性がありました。

右側は類似バグ探索で発見した例です。
Nimbusのblob/column上限問題、Grandineのbackfill系問題、LodestarのByRange問題など、「範囲チェック漏れ」という既知パターンを横展開することで効率的にバグを発見しました。

下部には、Valid判定された全17件のクライアント別内訳を示しています。
Nimbusが6件と最多で、Grandineが3件、Erigonが2件、残り6クライアント（Besu、Lodestar、Nethermind、Teku、Prysm、Reth）が各1件です。
Nimbusが最多なのは、言語仕様が関係していると考えられます。
-->
