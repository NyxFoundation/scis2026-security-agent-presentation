---
layout: default
---

# 見逃したHigh/Medium脆弱性

<div class="grid grid-cols-2 gap-6 mt-2">

<div>
  <div class="font-bold mb-2 text-red-800">見逃し率</div>
  <table class="w-full text-sm text-center">
    <thead class="bg-gray-100">
      <tr><th>Severity</th><th>全体</th><th>発見</th><th class="text-red-600">見逃し</th></tr>
    </thead>
    <tbody>
      <tr class="text-red-600 font-bold bg-red-50"><td>High</td><td>5</td><td>0</td><td>5</td></tr>
      <tr class="text-orange-600 font-bold bg-orange-50"><td>Medium</td><td>2</td><td>0</td><td>2</td></tr>
      <tr><td>Low</td><td>8</td><td>1</td><td>7</td></tr>
    </tbody>
  </table>
  <div class="mt-2 text-center text-sm text-red-600 font-bold">
    High/Medium: 発見率 0%
  </div>
</div>

<div class="text-sm space-y-2">

<div class="p-2 border-l-4 border-red-500 bg-red-50">
  <div class="font-bold text-red-800">#203 (High): c-kzg Weak Fiat-Shamir</div>
  <div class="text-xs">外部暗号ライブラリの脆弱性。無効なcell proofが検証を通過。</div>
</div>

<div class="p-2 border-l-4 border-red-500 bg-red-50">
  <div class="font-bold text-red-800">#190 (High): Prysm キャッシュ不備</div>
  <div class="text-xs">inclusion proof検証結果のキャッシュ不備。無効なdata column sidecarを受理。</div>
</div>

<div class="p-2 border-l-4 border-red-500 bg-red-50">
  <div class="font-bold text-red-800">#176 (High): Nethermind blob tx処理</div>
  <div class="text-xs">不正なblob txでバリデータのブロック生成が停止。</div>
</div>

<div class="p-2 border-l-4 border-orange-400 bg-orange-50">
  <div class="font-bold text-orange-800">#15 (Medium): Nimbus metadata DoS</div>
  <div class="text-xs">#109と類似だが別経路（metadata更新経由）。</div>
</div>

</div>

</div>

<!--
ここからは失敗分析です。
他チームが見つけたHigh/Mediumバグをすべて見逃してしまいました。

右側に具体例を示しています。
#203はc-kzg-4844という外部暗号ライブラリの脆弱性で、Fiat-Shamir変換の実装が弱く、無効な証明が検証を通過してしまうものでした。
#190はPrysmのキャッシュ実装の不備で、一度検証したdata column sidecarの結果を誤ってキャッシュしてしまう問題です。
#176はNethermindで、不正なblob transactionを受け取るとブロック生成が停止してしまう致命的なバグでした。

これらは全て、我々のエージェントでは発見できませんでした。
-->
