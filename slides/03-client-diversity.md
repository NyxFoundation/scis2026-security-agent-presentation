---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# イーサリアムの心臓部を守る「クライアント」とは？

<div class="mt-4 mb-6 p-3 bg-blue-50 rounded-lg text-sm">
  <strong>クライアント</strong>とは、イーサリアムネットワークに参加するための<strong>ソフトウェア</strong>です。<br>
  PCで言えば「OS」、インターネットで言えば「Webブラウザ」のような役割を担います。
</div>

<div class="grid grid-cols-2 gap-6">

<div>
  <div class="font-bold text-center mb-3 text-blue-700">クライアント多様性</div>

  <div class="flex justify-center items-center gap-2 mb-4 text-xs">
    <div class="px-2 py-1 bg-blue-100 rounded">Geth</div>
    <div class="px-2 py-1 bg-blue-100 rounded">Reth</div>
    <div class="px-2 py-1 bg-blue-100 rounded">Besu</div>
    <div class="text-gray-400">...</div>
    <div class="text-lg text-gray-400 mx-1">×</div>
    <div class="px-2 py-1 bg-purple-100 rounded">Lighthouse</div>
    <div class="px-2 py-1 bg-purple-100 rounded">Prysm</div>
    <div class="text-gray-400">...</div>
  </div>

  <div class="text-xs text-center text-gray-500 mb-4">
    実行層 (EL) × 合意層 (CL) の組み合わせを自由に選択可能
  </div>
</div>

<div class="space-y-3">
  <div class="flex items-start gap-3 p-3 bg-green-50 rounded-lg">
    <div class="text-2xl text-green-600">✓</div>
    <div>
      <div class="font-bold text-green-700 text-sm">耐障害性（強み）</div>
      <div class="text-xs text-gray-600">1つのクライアントにバグがあっても<br>他を使うノードは影響を受けない</div>
    </div>
  </div>

  <div class="flex items-start gap-3 p-3 bg-red-50 rounded-lg">
    <div class="text-2xl text-red-600">✗</div>
    <div>
      <div class="font-bold text-red-700 text-sm">検証コスト（課題）</div>
      <div class="text-xs text-gray-600"><strong>全ての実装</strong>を検証しなければ<br>ネットワーク全体の安全性を保証できない</div>
    </div>
  </div>
</div>

</div>

<div class="mt-4 text-center text-sm font-bold text-gray-700">
  → 11種類もの異なるクライアントを、どのように効率的に検証するか？
</div>

<!--
イーサリアムには「クライアント多様性」という特徴があります。

クライアントとは、イーサリアムネットワークに参加するためのソフトウェアです。
PCで言えばOSのようなもの、インターネットで言えばWebブラウザのような役割です。

ノード運用者は、実行層と合意層のソフトウェアを自由に組み合わせて選ぶことができます。
例えば、実行層はGeth、合意層はLighthouseという組み合わせも可能です。

これには耐障害性というメリットがあります。
1つのソフトウェアにバグがあっても、他のソフトを使っているノードは影響を受けません。

一方で、全ての実装を検証しなければならないという課題もあります。
11種類もの異なるクライアントを、どのように効率的に検証するかが本研究の動機です。
-->
