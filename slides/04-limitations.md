---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 迫り来る脅威：人手では追いつかない検証の限界

<div class="text-sm text-gray-600 mb-4">
  プロトコルアップグレードごとに、従来手法では限界が露呈している
</div>

<div class="grid grid-cols-2 gap-4">

<div class="p-4 border-2 border-gray-300 rounded-lg">
  <div class="font-bold mb-2 flex items-center gap-2">
    <span class="bg-gray-600 text-white px-2 py-0.5 rounded text-xs">従来手法①</span>
    人手による監査
  </div>
  <div class="text-sm space-y-2">
    <div class="flex items-center gap-2">
      <span class="text-red-500">✗</span>
      <span><strong>スケーラビリティ不足</strong></span>
    </div>
    <div class="flex items-center gap-2">
      <span class="text-red-500">✗</span>
      <span>コストが高い（専門家の時間単価）</span>
    </div>
    <div class="flex items-center gap-2">
      <span class="text-red-500">✗</span>
      <span>人材が限られる（世界で数百人程度）</span>
    </div>
  </div>
</div>

<div class="p-4 border-2 border-gray-300 rounded-lg">
  <div class="font-bold mb-2 flex items-center gap-2">
    <span class="bg-gray-600 text-white px-2 py-0.5 rounded text-xs">従来手法②</span>
    差分ファジング
  </div>
  <div class="text-sm space-y-2">
    <div class="flex items-center gap-2">
      <span class="text-red-500">✗</span>
      <span><strong>意味論的盲点</strong></span>
    </div>
    <div class="text-xs text-gray-500 ml-5">
      全員が同じ勘違い → 差分が出ず検知不可
    </div>
    <div class="flex items-center gap-2">
      <span class="text-red-500">✗</span>
      <span>Deep State への到達が困難</span>
    </div>
  </div>
</div>

</div>

<div class="mt-6 p-4 bg-blue-50 rounded-lg border-2 border-blue-400">
  <div class="text-center">
    <div class="text-lg font-bold text-blue-700 mb-2">
      研究課題 (Research Question)
    </div>
    <div class="text-sm">
      LLMエージェントを用いて、<br>
      <strong>「熟練監査員のワークフロー」</strong>を自動化できないか？
    </div>
  </div>
</div>

<!--
これまでの検証手法には限界がありました。

一つは「専門家によるマニュアル監査」です。
これはスケーラビリティに欠け、コストも莫大です。
世界中でイーサリアムクライアントを監査できる専門家は数百人程度と言われています。

もう一つは「差分ファジング」です。
同じ入力を各クライアントに与えて出力を比較する手法ですが、これには「意味論的盲点」という弱点があります。
仕様自体が曖昧で全員が同じように間違った実装をしていた場合、差分が出ず検知できません。

そこで本研究では、LLMエージェントを用いることで、仕様を理解し、熟練監査員のような手順でコードを検証するプロセスを自動化できないかと考えました。
-->
