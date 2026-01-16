---
layout: default
---

# 誤検知の原因分析

<div class="grid grid-cols-2 gap-6 mt-6 items-center">

<div>

```mermaid
pie showData title 誤検知原因（計37件）
    "脅威モデル不整合 56.8% (21件)" : 21
    "既知/重複 21.6% (8件)" : 8
    "分析エラー 13.5% (5件)" : 5
    "スコープ外 8.1% (3件)" : 3
```

</div>

<div>

<div class="text-sm font-bold mb-2">脅威モデル不整合の例</div>

<div class="flex items-center gap-3 text-sm">
<div class="p-2 bg-blue-100 border border-blue-400 rounded text-center flex-1">
<div class="text-xs text-gray-500">我々の前提</div>
<div class="font-bold">実行層を信頼しない</div>
</div>
<div class="text-2xl text-red-500">≠</div>
<div class="p-2 bg-orange-100 border border-orange-400 rounded text-center flex-1">
<div class="text-xs text-gray-500">コンテストの前提</div>
<div class="font-bold">実行層は信頼</div>
</div>
</div>

<div class="mt-3 p-2 bg-yellow-50 border-l-4 border-yellow-500 text-sm">
このズレだけで <span class="font-bold text-red-600">21件（56.8%）</span> の誤検知
</div>

</div>

</div>

<div class="mt-4 text-center">

前提を明示化すれば改善可能

</div>

<!--
37件の誤検知を分析した結果、最大の原因は「脅威モデル不整合」で56.8%を占めました。

脅威モデルとは、「誰が攻撃者になりうるか」「どこまでを信頼するか」という前提条件のことです。

具体的には、我々のプロンプトでは実行層を「信頼しない」と設定していましたが、コンテストのルールでは「信頼コンポーネント」として扱われていました。この前提条件のズレが21件の誤検知を生みました。

重要な洞察は、誤検知の過半数が大規模言語モデルの推論能力の問題ではなく、前提条件の不整合に起因しているという点です。これは、工程として前提を明示化することで改善可能です。
-->
