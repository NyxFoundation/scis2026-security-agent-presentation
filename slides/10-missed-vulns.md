---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜHigh/Mediumの脆弱性を見逃したのか？

<div class="grid grid-cols-2 gap-4 mt-2">

<div>
  <div class="bg-red-50 p-2 rounded-lg border-2 border-red-400 mb-2">
    <div class="text-center text-2xl font-bold text-red-600 mb-1">
      High/Medium: 発見率 0%
    </div>
    <div class="text-xs space-y-1">
      <div class="flex justify-between bg-red-100 p-1 rounded font-bold text-red-700">
        <span>High</span>
        <span>全体5件 → 発見0件</span>
      </div>
      <div class="flex justify-between bg-orange-100 p-1 rounded font-bold text-orange-700">
        <span>Medium</span>
        <span>全体2件 → 発見0件</span>
      </div>
      <div class="flex justify-between p-1">
        <span>Low</span>
        <span>全体8件 → 発見1件</span>
      </div>
    </div>
  </div>

  <div class="font-bold text-xs mb-1">根本原因</div>
  <div class="space-y-1 text-xs">
    <div class="flex items-start gap-2 p-1 bg-gray-50 rounded">
      <span class="bg-red-600 text-white px-1 rounded text-xs">1</span>
      <div><strong>仕様外バグ</strong>: 暗号ライブラリ等</div>
    </div>
    <div class="flex items-start gap-2 p-1 bg-gray-50 rounded">
      <span class="bg-orange-500 text-white px-1 rounded text-xs">2</span>
      <div><strong>複雑な状態遷移</strong>: キャッシュ整合性</div>
    </div>
    <div class="flex items-start gap-2 p-1 bg-gray-50 rounded">
      <span class="bg-yellow-500 text-white px-1 rounded text-xs">3</span>
      <div><strong>動的解析未実施</strong>: Fuzzing不足</div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-xs mb-1 text-red-700">見逃した重大バグの例</div>

  <div class="space-y-1 text-xs">
    <div class="p-2 border-l-4 border-red-500 bg-red-50 rounded-r">
      <div class="font-bold text-red-800">#203 (High): c-kzg Fiat-Shamir</div>
      <div class="text-gray-600">外部暗号ライブラリの脆弱性</div>
      <div class="text-blue-600">→ 仕様ベース監査ではスコープ外</div>
    </div>
    <div class="p-2 border-l-4 border-red-500 bg-red-50 rounded-r">
      <div class="font-bold text-red-800">#190 (High): Prysm キャッシュ</div>
      <div class="text-gray-600">inclusion proof検証結果のキャッシュ不備</div>
      <div class="text-blue-600">→ 静的解析では検出困難</div>
    </div>
    <div class="p-2 border-l-4 border-red-500 bg-red-50 rounded-r">
      <div class="font-bold text-red-800">#176 (High): Nethermind blob</div>
      <div class="text-gray-600">不正blob txでブロック生成停止</div>
      <div class="text-blue-600">→ EL解析が手薄だった</div>
    </div>
  </div>

  <div class="mt-2 p-2 bg-blue-50 rounded text-xs border border-blue-200">
    <strong>重要:</strong> これらは改善可能な課題
  </div>
</div>

</div>

<!--
ここからは失敗分析です。
正直に申し上げると、他チームが見つけたHigh/Mediumのバグを全て見逃してしまいました。

根本原因を分析したところ、3つの問題がありました。

1つ目は「仕様外のバグ」です。
#203は外部暗号ライブラリの脆弱性で、我々の仕様ベース監査ではスコープ外でした。

2つ目は「複雑な状態遷移」です。
#190のキャッシュ整合性のようなバグは、静的解析だけでは検出困難でした。

3つ目は「動的解析の未実施」です。
Fuzzingや依存関係スキャンを十分に行っていませんでした。

これらは重く受け止めるべき課題ですが、同時に改善可能な課題でもあります。
-->
