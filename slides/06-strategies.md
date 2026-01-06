---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# AIエージェントの3つの賢い戦略

<div class="text-sm text-gray-600 mb-4">
  それぞれ異なるアプローチで脆弱性を探索し、検出範囲を最大化
</div>

<div class="grid grid-cols-3 gap-4">

<div class="p-3 border-2 border-blue-400 rounded-lg bg-blue-50">
  <div class="font-bold text-blue-800 mb-2 text-sm">(i) 仕様ベース静的検査</div>
  <div class="p-2 bg-white rounded mb-2 text-xs">
    <div class="font-bold text-gray-600">比喩で言えば...</div>
    <div class="text-blue-700">「設計図と実物を見比べる」</div>
  </div>
  <div class="text-xs space-y-1">
    <div>仕様要件が実装で正しく守られているか検証</div>
    <div class="bg-white p-1.5 rounded mt-2">
      <strong>例:</strong> 「パラメータの上限値チェックが漏れている」
    </div>
  </div>
</div>

<div class="p-3 border-2 border-green-400 rounded-lg bg-green-50">
  <div class="font-bold text-green-800 mb-2 text-sm">(ii) 類似バグ探索</div>
  <div class="p-2 bg-white rounded mb-2 text-xs">
    <div class="font-bold text-gray-600">比喩で言えば...</div>
    <div class="text-green-700">「過去の失敗から学ぶ」</div>
  </div>
  <div class="text-xs space-y-1">
    <div>既知バグパターンを他クライアントに横展開</div>
    <div class="bg-white p-1.5 rounded mt-2">
      <strong>例:</strong> 「Aで見つかったバグ → B, Cにも同じパターンが？」
    </div>
  </div>
</div>

<div class="p-3 border-2 border-purple-400 rounded-lg bg-purple-50">
  <div class="font-bold text-purple-800 mb-2 text-sm">(iii) 動的テスト生成</div>
  <div class="p-2 bg-white rounded mb-2 text-xs">
    <div class="font-bold text-gray-600">比喩で言えば...</div>
    <div class="text-purple-700">「実際に動かして試す」</div>
  </div>
  <div class="text-xs space-y-1">
    <div>テストケース・Fuzzerを自動生成して実機検証</div>
    <div class="bg-white p-1.5 rounded mt-2">
      <strong>例:</strong> 「境界値での挙動を自動テスト」
    </div>
  </div>
</div>

</div>

<div class="mt-4 p-3 bg-yellow-50 rounded-lg border border-yellow-300">
  <div class="flex items-center gap-3">
    <div class="text-2xl">💡</div>
    <div class="text-sm">
      <strong>今回最も効果を発揮したのは「類似バグ探索」</strong><br>
      <span class="text-xs text-gray-600">発見された脆弱性の76.5%がこの戦略によるもの</span>
    </div>
  </div>
</div>

<!--
本手法では3つの異なる戦略を用いて脆弱性を探索します。

1つ目は「仕様ベース静的検査」です。
比喩で言えば「設計図と実物を見比べる」アプローチです。
仕様で定義された要件が、実装コード上で正しく守られているかを検証します。

2つ目は「類似バグ探索」です。
これは「過去の失敗から学ぶ」アプローチです。
あるクライアントで見つかったバグを、他のクライアントに横展開して探索します。
これが今回のコンテストで最も効果を発揮した戦略です。

3つ目は「動的テスト生成」です。
「実際に動かして試す」アプローチで、テストコードを自動生成して実機で確認します。
-->
