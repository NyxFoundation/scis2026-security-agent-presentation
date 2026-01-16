---
layout: default
---

# 予備3: 有効発見の具体例

<div class="mt-4 text-xs">

| クライアント | イシュー | 重大度 | 発見方法 |
|------------|---------|:-----:|---------|
| <img src="/images/eth_nimbus.png" class="w-4 h-4 inline" /> Nimbus | カストディローテーションDoS | **低** | 仕様ベース監査 |
| <img src="/images/eth_lodestar.png" class="w-4 h-4 inline" /> Lodestar | データカラムサイドカー範囲ガード欠落 | 情報 | 横展開 |
| <img src="/images/eth_grandine.png" class="w-4 h-4 inline" /> Grandine | バックフィル回復停止 | 情報 | 横展開 |
| <img src="/images/eth_erigon.png" class="w-4 h-4 inline" /> Erigon | 大阪前トランザクション残存 | 情報 | 横展開 |

<div class="mt-4 grid grid-cols-2 gap-3">

<div class="p-2 bg-blue-50 rounded border border-blue-200">
  <div class="font-bold mb-1">横展開の連鎖例</div>
  <div class="flex items-center gap-1">
    <span class="px-1 py-0.5 bg-white rounded border text-xs">Nimbus</span>
    <span class="text-gray-400">→</span>
    <span class="px-1 py-0.5 bg-white rounded border text-xs">Grandine</span>
    <span class="text-gray-400">→</span>
    <span class="px-1 py-0.5 bg-white rounded border text-xs">Lodestar</span>
  </div>
  <div class="text-gray-500 mt-1">同一パターンで3件発見</div>
</div>

<div class="p-2 bg-slate-100 rounded border border-slate-300">
  <div class="font-bold mb-1">クライアント別発見数</div>
  <div class="flex flex-wrap gap-1">
    <span class="px-1 py-0.5 bg-green-100 rounded text-xs">Nimbus: 6</span>
    <span class="px-1 py-0.5 bg-green-100 rounded text-xs">Grandine: 3</span>
    <span class="px-1 py-0.5 bg-green-100 rounded text-xs">Erigon: 2</span>
    <span class="px-1 py-0.5 bg-slate-200 rounded text-xs border border-slate-300">他: 各1</span>
  </div>
  <div class="text-gray-500 mt-1">9つのクライアントで有効発見</div>
</div>

</div>

</div>

<!--
有効発見の具体例です。

唯一の低重大度はNimbusのカストディローテーションDoSで、仕様に明記された上限値チェックの欠落でした。

他はすべて情報レベルですが、例えばデータカラムサイドカー範囲のガード欠落は、最初にLodestarで発見した後、GrandineとNimbusに横展開しました。

クライアント別ではNimbusが6件と最多で、9つのクライアントで有効発見がありました。
-->
