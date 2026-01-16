---
layout: default
---

# Ethereum Fusakaアップグレードの11クライアント監査で評価した

<div class="grid grid-cols-3 gap-4 mt-4">

<div>

| 項目 | 値 |
|------|-----|
| 対象 | Ethereum Fusaka |
| クライアント数 | 11 |
| 全参加者有効 | 101件 (27.6%) |
| **我々の有効** | **17件 (31.5%)** |

<div class="mt-2 p-2 bg-yellow-50 border-l-4 border-yellow-500 text-xs">

**注**: High = ネットワーク停止級の厳格な基準<br>
Low/Info も仕様違反として重要な報告

</div>

</div>

<div class="col-span-2">

<div class="text-sm font-bold mb-1">合意層 (6)</div>
<div class="flex gap-3 mb-3 text-xs">
<div class="text-center"><img src="/images/eth_nimbus.png" class="h-7 mx-auto"><div>Nimbus</div></div>
<div class="text-center"><img src="/images/eth_lighthouse.png" class="h-7 mx-auto"><div>Lighthouse</div></div>
<div class="text-center"><img src="/images/eth_prysm.png" class="h-7 mx-auto"><div>Prysm</div></div>
<div class="text-center"><img src="/images/eth_teku.png" class="h-7 mx-auto"><div>Teku</div></div>
<div class="text-center"><img src="/images/eth_lodestar.png" class="h-7 mx-auto"><div>Lodestar</div></div>
<div class="text-center"><img src="/images/eth_grandine.png" class="h-7 mx-auto"><div>Grandine</div></div>
</div>

<div class="text-sm font-bold mb-1">実行層 (5)</div>
<div class="flex gap-3 text-xs">
<div class="text-center"><img src="/images/eth_geth.png" class="h-7 mx-auto"><div>Geth</div></div>
<div class="text-center"><img src="/images/eth_reth.png" class="h-7 mx-auto"><div>Reth</div></div>
<div class="text-center"><img src="/images/eth_erigon.png" class="h-7 mx-auto"><div>Erigon</div></div>
<div class="text-center"><img src="/images/eth_nethermind.png" class="h-7 mx-auto"><div>Nethermind</div></div>
<div class="text-center"><img src="/images/eth_besu.png" class="h-7 mx-auto"><div>Besu</div></div>
</div>

</div>

</div>

<div class="mt-3 text-center">

有効率 **31.5%** で全体平均 (27.6%) を上回る

</div>

<!--
評価環境として、Ethereumの次期アップグレードであるFusakaの監査コンテストを使用しました。

Ethereumでは、ブロックの生成や検証を担当する「合意層」と、実際のトランザクション処理を行う「実行層」に分かれており、それぞれ複数の独立したクライアント実装があります。

今回は合意層6つ、実行層5つ、計11の本番クライアントが対象でした。

全参加者合計で366件の提出があり、101件が有効と判定され、全体の有効率は27.6%でした。我々は54件を提出し、17件が有効と認められ、有効率31.5%で全体平均を上回りました。
-->
