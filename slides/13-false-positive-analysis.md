---
layout: default
---

# 誤検知 (68.5%) の原因分析

<div class="mb-4 text-center">
  <div class="inline-block bg-gray-100 rounded-lg px-6 py-2">
    <span class="text-gray-600 mr-2">Valid率:</span>
    <span class="text-2xl font-bold text-blue-600">31.5%</span>
    <span class="mx-4 text-gray-300">|</span>
    <span class="text-gray-600 mr-2">Invalid率:</span>
    <span class="text-2xl font-bold text-red-500">68.5%</span>
  </div>
</div>

<div class="grid grid-cols-2 gap-4">

<div class="p-4 bg-red-50 rounded-lg border-l-4 border-red-500">
  <div class="font-bold text-red-800 text-lg mb-2">① 脅威モデルの不一致 (27.0%)</div>
  <div class="text-sm text-gray-700">
    <div class="flex justify-between mb-1">
      <span>Our Prompt:</span>
      <span class="font-bold">ELは信頼しない</span>
    </div>
    <div class="flex justify-between mb-2">
      <span>Contest Rule:</span>
      <span class="font-bold">ELは信頼できる</span>
    </div>
    <div class="bg-white p-2 rounded text-xs">
      ELからの入力を再検証すべきという指摘が、ルール上すべてInvalid判定に。
    </div>
  </div>
</div>

<div class="space-y-2">

<div class="p-3 bg-gray-50 rounded border-l-4 border-gray-400">
  <div class="font-bold text-sm mb-1">② 判断基準のズレ (21.6%)</div>
  <div class="text-xs text-gray-600">
    技術的には正しいが「Info」レベルとして報奨金対象外。<br>
    (例: ログ出力の不足、軽微なドキュメント不備)
  </div>
</div>

<div class="p-3 bg-gray-50 rounded border-l-4 border-gray-400">
  <div class="font-bold text-sm mb-1">③ 既知の防御/重複 (10-15%)</div>
  <div class="text-xs text-gray-600">
    テストコード・ドキュメントをコンテキストから除外していたため、実装済みの防御策を認識できず。
  </div>
</div>

<div class="p-3 bg-gray-50 rounded border-l-4 border-gray-400">
  <div class="font-bold text-sm mb-1">④ 到達可能性の検証不足</div>
  <div class="text-xs text-gray-600">
    ビルド対象外やモックコードを監査してしまった。
  </div>
</div>

</div>

</div>

<!--
誤検知の分析です。
6割以上がInvalid判定を受けましたが、これには明確な理由がありました。

最大の要因は「脅威モデルの不一致」です。
我々のプロンプトでは「実行層クライアントは信頼できない」という厳格なゼロトラスト設定をしていましたが、コンテストのルールでは「実行層は信頼できるものとする」と定義されていました。
このため、ELからの入力を疑う指摘がすべて「ルール上問題なし」として却下されました。

2つ目は「判断基準のズレ」です。技術的には正しい指摘でも、報奨金の対象となる深刻度に達していないものがありました。

3つ目は「既知の防御の見落とし」です。テストコードやドキュメントをコンテキストから除外していたため、すでに実装されている防御策を認識できませんでした。

これらは技術的な問題というより、事前のルール確認とプロンプト調整の問題です。
-->
