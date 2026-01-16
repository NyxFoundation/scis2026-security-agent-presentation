---
layout: two-cols
layoutClass: gap-6
---

# 予備2: 評価環境の詳細（重大度定義と賞金構造）

<div class="text-xs mt-4">

**重大度定義**

| 重大度 | 影響閾値 |
|-------|---------|
| 致命的 | 50%超のスラッシュ、無限ETH生成等 |
| 高 | 33%超のネットワーク分断/停止 |
| 中 | 5%超の分断/停止 |
| 低 | 0.01%超の分断/停止 |
| 情報 | クライアントが修正価値を認めた場合 |

</div>

::right::

<div class="text-xs mt-16">

**賞金構造**

<div class="p-3 bg-slate-100 rounded border border-slate-300">
  <div class="text-center mb-3">
    <div class="text-gray-500 text-xs">総額</div>
    <div class="text-2xl font-bold">$2,000,000</div>
  </div>
  <div class="space-y-1">
    <div class="flex justify-between">
      <span>致命的</span>
      <span class="font-bold">30 pt</span>
    </div>
    <div class="flex justify-between">
      <span>高</span>
      <span class="font-bold">10 pt</span>
    </div>
    <div class="flex justify-between">
      <span>中</span>
      <span class="font-bold">5 pt</span>
    </div>
    <div class="flex justify-between">
      <span>低</span>
      <span class="font-bold">2 pt</span>
    </div>
  </div>
</div>

<div class="mt-2 p-2 bg-blue-50 rounded border border-blue-200 text-center">
  <span class="font-bold text-blue-700">閾値が非常に高いため、低/情報でも実運用上の価値がある</span>
</div>

</div>

<!--
重大度の詳細定義です。

「高」は「ネットワークの33%超に影響」という非常に高い閾値で定義されています。

そのため、「低」（0.01%超）や「情報」（クライアントが修正を認めたもの）でも、実運用上は意味のある発見です。

賞金プールは200万ドル、ポイント配分は致命的30点から低2点までの傾斜があります。
-->
