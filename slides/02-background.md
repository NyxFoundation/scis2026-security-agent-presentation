---
layout: center
class: text-center
---

# イーサリアムの「クライアント多様性」

<div class="text-base mt-4 mb-6 text-gray-600">
  ノード運用者は<strong>実行層</strong>と<strong>合意層</strong>の実装を自由に組み合わせて選べる
</div>

<div class="flex justify-center items-center gap-4 mb-8 text-sm">
  <div class="px-3 py-1 bg-blue-100 rounded">Geth</div>
  <div class="px-3 py-1 bg-blue-100 rounded">Reth</div>
  <div class="px-3 py-1 bg-blue-100 rounded">Besu</div>
  <div class="text-gray-400">...</div>
  <div class="text-2xl text-gray-400 mx-2">×</div>
  <div class="px-3 py-1 bg-purple-100 rounded">Lighthouse</div>
  <div class="px-3 py-1 bg-purple-100 rounded">Prysm</div>
  <div class="px-3 py-1 bg-purple-100 rounded">Nimbus</div>
  <div class="text-gray-400">...</div>
</div>

<div class="flex justify-center">
<div class="space-y-3">

<div class="flex items-center gap-4">
  <div class="text-3xl">✓</div>
  <div class="text-left">
    <span class="font-bold text-green-600">耐障害性:</span>
    <span class="text-sm text-gray-600">1つにバグがあってもネットワークは止まらない</span>
  </div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">✗</div>
  <div class="text-left">
    <span class="font-bold text-red-600">検証コスト:</span>
    <span class="text-sm text-gray-600">全ての実装を検証しなければならない</span>
  </div>
</div>

</div>
</div>

<!--
イーサリアムには「クライアント多様性」という特徴があります。

ノード運用者は、実行層と合意層のソフトウェアを自由に組み合わせて選ぶことができます。
例えば、実行層はGeth、合意層はLighthouseという組み合わせも可能ですし、
実行層はReth、合意層はPrysmという組み合わせも可能です。

これには耐障害性というメリットがあります。
1つのソフトウェアにバグがあっても、他のソフトを使っているノードは影響を受けません。

一方で、全ての実装を検証しなければならないという課題もあります。
-->
