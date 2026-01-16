---
layout: default
---

# Ethereumの11クライアント監査コンテストで評価

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

| 項目 | 値 |
|------|-----|
| 対象 | Ethereum Fusaka |
| クライアント数 | 11 |
| 全参加者有効 | 101件 (27.6%) |
| **我々の有効** | **17件 (31.5%)** |

<div class="mt-4 p-2 bg-yellow-50 border-l-4 border-yellow-500 text-md">

**注**: High = ネットワーク停止級の厳格な基準<br>
Low/Info も仕様違反として重要な報告

</div>

</div>

<div>

<div class="p-3 bg-blue-50 rounded mb-3">
<div class="text-sm font-bold mb-2">合意層 (6)</div>
<div class="grid grid-cols-6 gap-1 text-xs text-center">
<div><img src="/images/eth_nimbus.png" class="h-6 mx-auto mb-1">Nimbus</div>
<div><img src="/images/eth_lighthouse.png" class="h-6 mx-auto mb-1">Lighthouse</div>
<div><img src="/images/eth_prysm.png" class="h-6 mx-auto mb-1">Prysm</div>
<div><img src="/images/eth_teku.png" class="h-6 mx-auto mb-1">Teku</div>
<div><img src="/images/eth_lodestar.png" class="h-6 mx-auto mb-1">Lodestar</div>
<div><img src="/images/eth_grandine.png" class="h-6 mx-auto mb-1">Grandine</div>
</div>
</div>

<div class="p-3 bg-green-50 rounded">
<div class="text-sm font-bold mb-2">実行層 (5)</div>
<div class="grid grid-cols-5 gap-1 text-xs text-center">
<div><img src="/images/eth_geth.png" class="h-6 mx-auto mb-1">Geth</div>
<div><img src="/images/eth_reth.png" class="h-6 mx-auto mb-1">Reth</div>
<div><img src="/images/eth_erigon.png" class="h-6 mx-auto mb-1">Erigon</div>
<div><img src="/images/eth_nethermind.png" class="h-6 mx-auto mb-1">Nether.</div>
<div><img src="/images/eth_besu.png" class="h-6 mx-auto mb-1">Besu</div>
</div>
</div>

</div>

</div>

<!--
評価環境として、Ethereumの次期アップグレードであるFusakaの監査コンテストを使用しました。

Ethereumでは、ブロックの生成や検証を担当する「合意層」と、実際のトランザクション処理を行う「実行層」に分かれており、それぞれ複数の独立したクライアント実装があります。

今回は合意層6つ、実行層5つ、計11の本番クライアントが対象でした。

全参加者合計で366件の提出があり、101件が有効と判定され、全体の有効率は27.6%でした。我々は54件を提出し、17件が有効と認められ、有効率31.5%で全体平均を上回りました。

なお、このコンテストではHighの基準が非常に厳格で、ネットワーク停止レベルの深刻な脆弱性のみがHighと判定されます。そのため、LowやInfoと判定された報告も、仕様違反として重要な発見です。
-->
