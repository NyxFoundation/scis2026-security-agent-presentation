---
layout: default
---

# 見逃しの根本原因分析

<div class="mt-2 space-y-2">

<div class="p-2 border-l-4 border-red-500 bg-red-50 rounded-r">
  <div class="flex items-start gap-2">
    <span class="bg-red-600 text-white px-2 py-0.5 rounded text-xs font-bold">1</span>
    <div>
      <div class="font-bold text-red-800 text-sm">仕様外の暗号ライブラリバグ</div>
      <div class="text-xs">プロンプトが仕様書(EIP)からの逸脱検出に特化。外部ライブラリは対象外。</div>
      <div class="text-xs text-gray-500">該当: #203 (c-kzg-4844), #48 (rust-eth-kzg)</div>
    </div>
  </div>
</div>

<div class="p-2 border-l-4 border-orange-500 bg-orange-50 rounded-r">
  <div class="flex items-start gap-2">
    <span class="bg-orange-600 text-white px-2 py-0.5 rounded text-xs font-bold">2</span>
    <div>
      <div class="font-bold text-orange-800 text-sm">複雑な状態遷移の検出困難</div>
      <div class="text-xs">静的解析では検出困難な状態依存バグ。キャッシュ整合性やfork後の状態更新。</div>
      <div class="text-xs text-gray-500">該当: #190 (Prysmキャッシュ), #216 (fork後metadata)</div>
    </div>
  </div>
</div>

<div class="p-2 border-l-4 border-yellow-500 bg-yellow-50 rounded-r">
  <div class="flex items-start gap-2">
    <span class="bg-yellow-600 text-white px-2 py-0.5 rounded text-xs font-bold">3</span>
    <div>
      <div class="font-bold text-yellow-800 text-sm">EL (実行層) 固有の脆弱性</div>
      <div class="text-xs">CLに注力しELの解析が手薄。blob tx処理などEL特有ロジックを見落とし。</div>
      <div class="text-xs text-gray-500">該当: #176, #210 (Nethermind blob処理)</div>
    </div>
  </div>
</div>

<div class="p-2 border-l-4 border-blue-500 bg-blue-50 rounded-r">
  <div class="flex items-start gap-2">
    <span class="bg-blue-600 text-white px-2 py-0.5 rounded text-xs font-bold">4</span>
    <div>
      <div class="font-bold text-blue-800 text-sm">依存関係スキャン・動的解析の未実施</div>
      <div class="text-xs"><code>cargo audit</code>等の自動スキャン未統合。Fuzzingも不十分。</div>
      <div class="text-xs text-gray-500">該当: #308 (DoS), #371 (blob-fee計算)</div>
    </div>
  </div>
</div>

</div>

<!--
見逃しの根本原因を分析しました。

1つ目は「仕様外の暗号ライブラリバグ」です。
我々のエージェントはEIPなどの仕様書からの逸脱を検出することに特化していたため、外部ライブラリの脆弱性は監査対象外となっていました。

2つ目は「複雑な状態遷移」です。
キャッシュの整合性やfork後の状態更新といった、静的解析だけでは検出困難なバグを見落としました。

3つ目は「EL固有の脆弱性」です。
CLに注力するあまり、ELの解析が手薄になっていました。

4つ目は「依存関係スキャンや動的解析の未実施」です。
cargo auditのような自動スキャンや、Fuzzingを十分に行っていませんでした。
-->
