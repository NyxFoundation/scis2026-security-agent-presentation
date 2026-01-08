---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜHigh/Mediumの脆弱性を見逃したのか？

<div class="bg-red-50 p-2 rounded-lg border-2 border-red-400 mb-3 text-center">
  <div class="text-sm text-gray-700">
    コンテストで報告されたHigh 5件・Medium 2件のうち、<strong class="text-red-600">我々が発見できたのは0件</strong>。
  </div>
</div>

<div class="grid grid-cols-2 gap-3">

<div>
  <div class="font-bold text-[11px] mb-0.5 text-gray-700">見逃したHigh脆弱性（5件）</div>
  <div class="space-y-0.5 text-[9px]">
    <div class="bg-red-50 p-1 rounded border border-red-200">
      <div class="flex items-center gap-1">
        <span class="bg-red-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">High</span>
        <span class="font-bold">#40: Proposer計算エラー</span>
      </div>
      <div class="text-gray-600">proposer lookaheadの考慮漏れ</div>
    </div>
    <div class="bg-red-50 p-1 rounded border border-red-200">
      <div class="flex items-center gap-1">
        <span class="bg-red-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">High</span>
        <span class="font-bold">#190: Prysm キャッシュ汚染</span>
      </div>
      <div class="text-gray-600">data column sidecar検証のキャッシュ不整合</div>
    </div>
    <div class="bg-red-50 p-1 rounded border border-red-200">
      <div class="flex items-center gap-1">
        <span class="bg-red-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">High</span>
        <span class="font-bold">#203: c-kzg Fiat-Shamir</span>
      </div>
      <div class="text-gray-600">外部暗号ライブラリの脆弱性</div>
    </div>
    <div class="bg-red-50 p-1 rounded border border-red-200">
      <div class="flex items-center gap-1">
        <span class="bg-red-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">High</span>
        <span class="font-bold">#176: Nethermind blob処理</span>
      </div>
      <div class="text-gray-600">不正blob txによるバリデータ停止</div>
    </div>
    <div class="bg-red-50 p-1 rounded border border-red-200">
      <div class="flex items-center gap-1">
        <span class="bg-red-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">High</span>
        <span class="font-bold">#210: Nethermind blob検証</span>
      </div>
      <div class="text-gray-600">blob hashと実データの不整合を許容</div>
    </div>
  </div>

  <div class="font-bold text-[11px] mb-0.5 mt-1 text-gray-700">見逃したMedium脆弱性（2件）</div>
  <div class="space-y-0.5 text-[9px]">
    <div class="bg-orange-50 p-1 rounded border border-orange-200">
      <div class="flex items-center gap-1">
        <span class="bg-orange-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">Med</span>
        <span class="font-bold">#15: Nimbus DoS</span>
      </div>
      <div class="text-gray-600">大きなcustody group countによるリモートDoS</div>
    </div>
    <div class="bg-orange-50 p-1 rounded border border-orange-200">
      <div class="flex items-center gap-1">
        <span class="bg-orange-600 text-white px-1 py-0.5 rounded text-[8px] font-bold">Med</span>
        <span class="font-bold">#216: Nimbus metadata</span>
      </div>
      <div class="text-gray-600">Fuluフォーク後の古いmetadata使用</div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-1 text-gray-700">見逃し原因の分析</div>
  <div class="bg-gray-50 p-2 rounded-lg space-y-2 text-[10px]">
    <div class="bg-red-100 p-1.5 rounded">
      <strong class="text-red-700">1. 暗号ライブラリがスコープ外</strong>
      <div class="text-gray-600">#203: c-kzgは外部依存であり、仕様ベース監査の対象外</div>
    </div>
    <div class="bg-orange-100 p-1.5 rounded">
      <strong class="text-orange-700">2. 複雑な状態遷移の追跡困難</strong>
      <div class="text-gray-600">#190: キャッシュ汚染は特定の状態遷移でのみ発生</div>
    </div>
    <div class="bg-yellow-100 p-1.5 rounded">
      <strong class="text-yellow-700">3. 動的解析（Fuzzing）の不足</strong>
      <div class="text-gray-600">#176, #210: 不正入力の境界条件テストが不十分</div>
    </div>
    <div class="bg-blue-100 p-1.5 rounded">
      <strong class="text-blue-700">4. 仕様の細かいニュアンス見落とし</strong>
      <div class="text-gray-600">#40: proposer lookaheadの仕様理解不足</div>
    </div>
  </div>
  
  <div class="mt-2 p-2 bg-blue-50 rounded border border-blue-200 text-[10px]">
    <strong class="text-blue-700">教訓:</strong><br>
    • 暗号ライブラリ等も仕様書に含める<br>
    • キャッシュ系の脆弱性パターンをチェックリストに追加<br>
    • 仕様の深い理解を促すプロンプト改善
  </div>
</div>

</div>

<!--
我々が見逃したHigh/Medium脆弱性について分析しました。

コンテストで報告されたHigh 5件・Medium 2件のうち、我々が発見できたのは0件でした。

左側に見逃した脆弱性の一覧を示しています。
High 5件は、#40のProposer計算エラー、#190のPrysmキャッシュ汚染、#203のc-kzg Fiat-Shamir脆弱性、#176と#210のNethermind blob処理関連です。
Medium 2件は、#15と#216のNimbus関連の脆弱性です。

右側に見逃し原因の分析を示しています。
1つ目は暗号ライブラリがスコープ外だったこと。
2つ目は複雑な状態遷移の追跡が困難だったこと。
3つ目は動的解析（Fuzzing）が不足していたこと。
4つ目は仕様の細かいニュアンスを見落としたことです。

教訓として、暗号ライブラリ等の仕様を含める、キャッシュ系の脆弱性パターンをチェックリストに追加すること、仕様の深い理解を促すプロンプト改善が挙げられます。
-->
