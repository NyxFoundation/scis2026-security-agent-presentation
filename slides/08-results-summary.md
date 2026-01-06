---
layout: default
---

# 結果サマリ: 報告件数No.1

<div class="flex justify-center items-center gap-12 mt-2 mb-6">
  <div class="text-center">
    <div class="text-6xl font-bold text-blue-600 mb-1">17件</div>
    <div class="text-sm text-gray-500">有効脆弱性</div>
  </div>
  <div class="text-sm border-l-2 pl-6 border-gray-300">
    <div><strong>総報告:</strong> 54件</div>
    <div><strong>Valid率:</strong> 31.5% (全体平均27.6%を上回る)</div>
    <div class="mt-2 text-red-600 font-bold text-lg">報告件数 No.1</div>
  </div>
</div>

<div class="grid grid-cols-2 gap-8">

<div>
  <div class="text-center font-bold mb-2 p-1 bg-blue-50 text-blue-800 rounded">
    Severity内訳
  </div>
  <table class="w-full text-sm text-center">
    <thead class="bg-gray-100">
      <tr><th>Severity</th><th>件数</th></tr>
    </thead>
    <tbody>
      <tr><td>High</td><td>0</td></tr>
      <tr><td>Medium</td><td>0</td></tr>
      <tr class="text-blue-700 font-bold"><td>Low</td><td>1</td></tr>
      <tr><td>Info</td><td>16</td></tr>
    </tbody>
  </table>
</div>

<div>
  <div class="text-center font-bold mb-2 p-1 bg-green-50 text-green-800 rounded">
    戦略別の有効性
  </div>
  <table class="w-full text-sm text-center">
    <thead class="bg-gray-100">
      <tr><th>戦略</th><th>件数</th><th>割合</th></tr>
    </thead>
    <tbody>
      <tr class="font-bold text-green-700 bg-green-50"><td>類似バグ探索</td><td>13</td><td>76.5%</td></tr>
      <tr><td>コード解析</td><td>3</td><td>17.6%</td></tr>
      <tr><td>Fuzzing</td><td>1</td><td>5.9%</td></tr>
    </tbody>
  </table>
</div>

</div>

<div class="mt-4 text-center text-sm text-gray-600">
  ※ 唯一のLow脆弱性 (#109) は「仕様ベース監査」で発見
</div>

<!--
結果の詳細です。
有効報告数は17件で、コンテスト参加者中、最多の報告件数となりました。
Valid率も31.5%と、全体平均の27.6%を上回っています。

ただし、Severityの内訳を見ると、Lowが1件、Infoが16件となっており、High/Mediumの致命的なバグは見つけることができませんでした。

右下の表をご覧ください。
戦略別の有効性では「類似バグ探索」が圧倒的で、有効なバグの76.5%を占めています。
これは、あるクライアントで見つかったバグを、他のクライアントに横展開して探索する戦略が非常に効果的だったことを示しています。
-->
