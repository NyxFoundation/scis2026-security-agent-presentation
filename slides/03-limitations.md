---
layout: default
---

# 既存手法の限界

プロトコルアップグレードごとの検証には、従来以下の手法が用いられてきたが、それぞれに限界がある。

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="p-4 border rounded bg-gray-50">
  <div class="font-bold mb-2">① 人手による監査</div>
  <ul class="text-sm list-disc pl-4 space-y-1">
    <li>専門家によるコードレビュー</li>
    <li><strong>スケーラビリティに欠ける</strong></li>
    <li>コストが高い・人材が限られる</li>
  </ul>
</div>

<div class="p-4 border rounded bg-gray-50">
  <div class="font-bold mb-2">② 差分ファジング (Fluffy, Forky等)</div>
  <ul class="text-sm list-disc pl-4 space-y-1">
    <li>同一入力を複数クライアントに与えて比較</li>
    <li><strong>意味論的盲点 (Semantic Blindness)</strong><br><span class="text-xs opacity-70">全員が同じ勘違いをしていると検知できない</span></li>
    <li>Deep Stateへの到達が困難</li>
  </ul>
</div>

</div>

<div class="mt-8 text-center font-bold text-xl text-blue-700">
  LLMエージェントを用いて「熟練監査員のワークフロー」を自動化できないか？
</div>

<!--
これまでの検証手法には限界がありました。
一つは「専門家によるマニュアル監査」ですが、これは当然スケーラビリティに欠け、コストも莫大です。
もう一つは「差分ファジング」です。同じ入力を各クライアントに食わせて出力を比較する手法ですが、これには「意味論的盲点」という弱点があります。
つまり、仕様自体が曖昧で全員が同じように間違った実装をしていた場合、差分が出ず検知できないのです。

そこで本研究では、LLMエージェントを用いることで、仕様を理解し、熟練監査員のような手順でコードを検証するプロセスを自動化できないかと考えました。
-->
