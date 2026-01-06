---
layout: default
---

# 3つの探索戦略

熟練監査員の思考プロセスを模倣するため、以下の3つの異なる戦略で脆弱性を探索。

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="p-4 border-2 border-blue-400 rounded-lg bg-blue-50">
  <div class="font-bold text-blue-800 mb-2">(i) 仕様ベース静的検査</div>
  <div class="text-sm">
    <div class="mb-2">仕様要件が実装で正しくガードされているか検証</div>
    <div class="text-xs bg-white p-2 rounded">
      <strong>狙い:</strong> 仕様と実装の乖離を検出<br>
      <strong>例:</strong> 「custody_group_countの上限検証」
    </div>
  </div>
</div>

<div class="p-4 border-2 border-green-400 rounded-lg bg-green-50">
  <div class="font-bold text-green-800 mb-2">(ii) 類似バグ探索</div>
  <div class="text-sm">
    <div class="mb-2">過去のCVE・既知バグパターンをFew-shotで提示し類似構造を探索</div>
    <div class="text-xs bg-white p-2 rounded">
      <strong>狙い:</strong> 既知パターンの横展開<br>
      <strong>例:</strong> 「Lodestarのバグ→他CLへ」
    </div>
  </div>
</div>

<div class="p-4 border-2 border-purple-400 rounded-lg bg-purple-50">
  <div class="font-bold text-purple-800 mb-2">(iii) 動的テスト生成</div>
  <div class="text-sm">
    <div class="mb-2">テストケース・簡易Fuzzerを自動生成して実機検証</div>
    <div class="text-xs bg-white p-2 rounded">
      <strong>狙い:</strong> エッジケースの挙動確認<br>
      <strong>例:</strong> 「境界値テストの自動生成」
    </div>
  </div>
</div>

</div>

<div class="mt-4 text-center text-sm text-gray-600">
  ※ 各プロンプトには「仕様書に記載のない仮定を禁止」「既知課題は除外」等の制約を明記
</div>

<!--
本手法では3つの異なる戦略を用いて脆弱性を探索します。

1つ目は「仕様ベース静的検査」です。仕様で定義された要件が、実装コード上で正しくガードされているかを検証します。

2つ目は「類似バグ探索」です。過去のイーサリアムクライアントで発見されたバグをFew-shot事例としてプロンプトに含め、類似した構造を持つコードを探索します。
これが今回のコンテストで最も効果を発揮した戦略です。

3つ目は「動的テスト生成」です。静的解析だけでは確証が得られない場合、テストコードを自動生成して実機で確認します。
-->
