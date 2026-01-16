---
layout: two-cols
layoutClass: gap-6
---

# Ethereum Fusakaコンテストで11クライアントを対象に評価した

<div class="text-xs mt-4">

| 項目 | 値 |
|------|---:|
| 対象実装 | **11 クライアント** |
| 全参加者の総提出数 | 366 件 |
| 全参加者の有効イシュー数 | 101 件 |
| 全参加者の有効率 | 27.6% |

<div class="mt-3 p-2 bg-yellow-50 rounded border border-yellow-300 text-xs">
  <div class="font-bold text-yellow-700">重大度の閾値は非常に高い</div>
  <div class="text-gray-600 mt-1">
    高 = 33%超のネットワーク分断<br>
    → 低/情報でも実用的価値あり
  </div>
</div>

</div>

::right::

<div class="text-xs mt-16">

**対象クライアント**

<div class="p-2 bg-slate-100 rounded border border-slate-300">
  <div class="text-gray-500 mb-1">コンセンサス層（CL）</div>
  <div class="grid grid-cols-3 gap-1 mb-2">
    <div class="flex items-center gap-1">
      <img src="/images/eth_nimbus.png" class="w-4 h-4" />
      <span>Nimbus</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_lighthouse.png" class="w-4 h-4" />
      <span>Lighthouse</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_prysm.png" class="w-4 h-4" />
      <span>Prysm</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_teku.png" class="w-4 h-4" />
      <span>Teku</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_lodestar.png" class="w-4 h-4" />
      <span>Lodestar</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_grandine.png" class="w-4 h-4" />
      <span>Grandine</span>
    </div>
  </div>
  <div class="text-gray-500 mb-1">エグゼキューション層（EL）</div>
  <div class="grid grid-cols-3 gap-1">
    <div class="flex items-center gap-1">
      <img src="/images/eth_geth.png" class="w-4 h-4" />
      <span>Geth</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_reth.png" class="w-4 h-4" />
      <span>Reth</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_erigon.png" class="w-4 h-4" />
      <span>Erigon</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_nethermind.png" class="w-4 h-4" />
      <span>Nethermind</span>
    </div>
    <div class="flex items-center gap-1">
      <img src="/images/eth_besu.png" class="w-4 h-4" />
      <span>Besu</span>
    </div>
  </div>
</div>

</div>

<!--
評価環境はEthereum Fusakaアップグレードの監査コンテストです。

11のプロダクションクライアント、コンセンサス層6つとエグゼキューション層5つを対象としました。

全参加者で366件の提出があり、101件が有効と判定されました。

なお、このコンテストの重大度定義は非常に厳格で、「高」は「ネットワークの33%超に影響」を意味します。
そのため、「低」や「情報」レベルでも実運用上の価値があります。

私たちの結果を見ていきましょう。
-->
