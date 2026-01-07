---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜHigh/Mediumの脆弱性を見逃したのか？

<!-- 上段: メッセージ -->
<div>
  <div class="bg-red-50 p-3 rounded-lg border-2 border-red-400 mb-4 text-center">
    <div class="text-sm text-gray-700">
      我々はコンテスト中に7件の<strong>High/Medium脆弱性を見逃しました</strong>。<br>
      これらは全て、他チームによって発見・報告されました。
    </div>
  </div>

  <div class="font-bold text-sm mb-2 text-gray-700">見逃した主な脆弱性と要因</div>
  
  <div class="overflow-x-auto">
    <table class="w-full text-xs border-collapse">
      <thead>
        <tr class="bg-gray-100 text-gray-700">
          <th class="p-2 border text-left w-12">ID</th>
          <th class="p-2 border text-left w-12">Sev</th>
          <th class="p-2 border text-left w-20">Client</th>
          <th class="p-2 border text-left">Summary</th>
          <th class="p-2 border text-left w-32">Why Missed?</th>
        </tr>
      </thead>
      <tbody>
        <!-- High: Crypto, Scope -->
        <tr class="border-b">
          <td class="p-2 border font-bold">#203</td>
          <td class="p-2 border font-bold text-red-600">High</td>
          <td class="p-2 border text-gray-600">c-kzg</td>
          <td class="p-2 border">
            <div>Weak Fiat-Shamir in proof verification</div>
            <div class="text-[10px] text-gray-500">外部暗号ライブラリの脆弱性</div>
          </td>
          <td class="p-2 border bg-red-50 text-red-800 font-bold">Scope Out</td>
        </tr>
        <!-- High: Complex State -->
        <tr class="border-b">
          <td class="p-2 border font-bold">#190</td>
          <td class="p-2 border font-bold text-red-600">High</td>
          <td class="p-2 border text-gray-600">Prysm</td>
          <td class="p-2 border">
            <div>Incorrect Caching of inclusion proof</div>
            <div class="text-[10px] text-gray-500">データ包含証明のキャッシュ不整合</div>
          </td>
          <td class="p-2 border bg-orange-50 text-orange-800 font-bold">Complex State</td>
        </tr>
        <!-- High: Dynamic Gap -->
        <tr class="border-b">
          <td class="p-2 border font-bold">#176</td>
          <td class="p-2 border font-bold text-red-600">High</td>
          <td class="p-2 border text-gray-600">Nethermind</td>
          <td class="p-2 border">
            <div>Malformed blob tx causes validator stop</div>
            <div class="text-[10px] text-gray-500">不正Blobによるバリデータ停止</div>
          </td>
          <td class="p-2 border bg-yellow-50 text-yellow-800 font-bold">Fuzzing Gap</td>
        </tr>
        <!-- High: Spec Nuance -->
        <tr class="border-b">
          <td class="p-2 border font-bold">#40</td>
          <td class="p-2 border font-bold text-red-600">High</td>
          <td class="p-2 border text-gray-600">Specs</td>
          <td class="p-2 border">
            <div>Proposer lookahead not considered</div>
            <div class="text-[10px] text-gray-500">Proposer計算ロジックの不備</div>
          </td>
          <td class="p-2 border bg-blue-50 text-blue-800 font-bold">Logic Bug</td>
        </tr>
        <!-- Med: Validation Miss -->
        <tr>
          <td class="p-2 border font-bold">#15</td>
          <td class="p-2 border font-bold text-orange-600">Med</td>
          <td class="p-2 border text-gray-600">Nimbus</td>
          <td class="p-2 border">
            <div>Remote DoS via large metadata update</div>
            <div class="text-[10px] text-gray-500">メタデータ更新時の検証不備</div>
          </td>
          <td class="p-2 border bg-gray-50 text-gray-800 font-bold">Simple Miss</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<!--
我々が見逃した5つのHigh/Medium脆弱性について、なぜ検知できなかったのか、その要因を分析しました。

表の上から順に説明します。
まず#203は、外部暗号ライブラリ(c-kzg)の脆弱性であり、仕様ベース監査のスコープ外でした。
#190のPrysmキャッシュ不整合は、特定の状態遷移でのみ発生するバグで、静的解析では状態の追跡が困難でした。
#176は不正なBlobデータによるDoSですが、これはFuzzingによる動的解析が不足していたことに起因します。

#40はプロポーザル計算ロジックの不備ですが、仕様の細かいニュアンスをコードに落とし込めず見逃しました。
#15は単純なバリデーション漏れですが、チェックリストによる網羅的な確認が不足していました。

これら見逃しの要因を分類すると、「スコープ定義（Scope）」「状態追跡（Complex State）」「動的解析（Fuzzing Gap）」の3つに集約されます。
-->
