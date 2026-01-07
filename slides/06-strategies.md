---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# AIエージェントの3つの賢い戦略

<div class="text-sm text-gray-600 mb-3">
  それぞれ異なるアプローチで脆弱性を探索し、検出範囲を最大化
</div>

<div class="grid grid-cols-3 gap-3">

<div class="p-2 border-2 border-primary-light rounded-lg bg-primary-bg">
  <div class="font-bold text-primary-dark mb-1 text-sm">(i) 仕様ベース静的検査</div>
  <div class="p-1.5 bg-white rounded mb-1 text-xs">
    <div class="text-primary">「設計図と実物を見比べる」</div>
  </div>
  <div class="text-xs">仕様要件が実装で正しく守られているか検証</div>
  <div class="mt-1 bg-gray-100 p-1.5 rounded text-[9px] font-mono">
    <div class="text-gray-500">// 03_AUDITMAP.json</div>
    <div class="text-blue-700">id: "P2P-001"</div>
    <div class="text-blue-700">snippet: "readList(...)"</div>
    <div class="text-green-600">status: "ok" ← UDP MTU制約で保護</div>
  </div>
</div>

<div class="p-2 border-2 border-secondary-light rounded-lg bg-secondary-bg">
  <div class="font-bold text-secondary-dark mb-1 text-sm">(ii) 類似バグ探索 ⭐</div>
  <div class="p-1.5 bg-white rounded mb-1 text-xs">
    <div class="text-secondary">「過去の失敗から学ぶ」</div>
  </div>
  <div class="text-xs">既知バグパターンを他クライアントに横展開</div>
  <div class="mt-1 bg-gray-100 p-1.5 rounded text-[9px] font-mono">
    <div class="text-gray-500">// bugs_ethereum.json</div>
    <div class="text-orange-700">CVE-2023-42319: GraphQL DoS</div>
    <div class="text-orange-700">CL-2023-01: BlocksByRange溢れ</div>
    <div class="text-green-600">→ 類似パターンを全クライアントで探索</div>
  </div>
</div>

<div class="p-2 border-2 border-tertiary-light rounded-lg bg-tertiary-bg">
  <div class="font-bold text-tertiary-dark mb-1 text-sm">(iii) 動的テスト生成</div>
  <div class="p-1.5 bg-white rounded mb-1 text-xs">
    <div class="text-tertiary">「実際に動かして試す」</div>
  </div>
  <div class="text-xs">テストケース・Fuzzerを自動生成して実機検証</div>
  <div class="mt-1 bg-gray-100 p-1.5 rounded text-[9px] font-mono">
    <div class="text-gray-500">// 自動生成テスト例</div>
    <div class="text-purple-700">#[test] fn rejects_mismatch() {'{'}}</div>
    <div class="text-purple-700">  s.proofs.truncate(1);</div>
    <div class="text-green-600">  assert!(verify(&s).is_err());</div>
  </div>
</div>

</div>

<div class="mt-3 p-2 bg-yellow-50 rounded-lg border border-yellow-300">
  <div class="flex items-center gap-3">
    <div class="text-xl">💡</div>
    <div class="text-sm">
      <strong>今回最も効果を発揮したのは「類似バグ探索」</strong><br>
      <span class="text-xs text-gray-600">発見された脆弱性の<strong class="text-yellow-700">76.5% (13/17件)</strong>がこの戦略によるもの</span>
    </div>
  </div>
</div>

<div class="mt-2 grid grid-cols-3 gap-2 text-[10px]">
  <div class="bg-gray-50 p-1.5 rounded text-center">
    <div class="font-bold text-blue-600">仕様ベース</div>
    <div>3件 (17.6%)</div>
  </div>
  <div class="bg-yellow-100 p-1.5 rounded text-center border border-yellow-400">
    <div class="font-bold text-yellow-700">類似バグ探索</div>
    <div>13件 (76.5%)</div>
  </div>
  <div class="bg-gray-50 p-1.5 rounded text-center">
    <div class="font-bold text-purple-600">動的テスト</div>
    <div>1件 (5.9%)</div>
  </div>
</div>

<!--
本手法では3つの異なる戦略を用いて脆弱性を探索します。

1つ目は「仕様ベース静的検査」です。
比喩で言えば「設計図と実物を見比べる」アプローチです。
実際の出力例として、03_AUDITMAP.jsonでは各コードスニペットに対してリスクカテゴリと判定ステータスを記録します。

2つ目は「類似バグ探索」です。
これは「過去の失敗から学ぶ」アプローチです。
bugs_ethereum.jsonには、CVE-2023-42319のGraphQL DoSやCL-2023-01のBlocksByRange溢れなど、過去の脆弱性パターンが登録されています。
これが今回のコンテストで最も効果を発揮した戦略で、発見された脆弱性の76.5%、17件中13件がこの戦略によるものです。

3つ目は「動的テスト生成」です。
「実際に動かして試す」アプローチで、仕様IDと攻撃パスIDを紐付けたテストコードを自動生成して実機で確認します。
-->
