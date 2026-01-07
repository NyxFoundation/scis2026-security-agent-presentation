---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜ誤検知が多かったのか？

<div class="text-sm text-gray-600 mb-3">
  68.5%の誤検知は「AIの能力不足」ではなく「設定のズレ」が原因
</div>

<div class="grid grid-cols-2 gap-4">

<div>
  <div class="font-bold text-sm mb-2 text-center">誤検知の主要因 (Invalid: 68.5%)</div>
  
  <div class="space-y-3">
    <div class="bg-red-50 p-3 rounded-lg border border-red-200">
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-red-600 text-white text-[10px] px-1.5 py-0.5 rounded">Primary (27%)</span>
        <span class="text-sm font-bold text-red-800">Threat Model Misalignment</span>
      </div>
      <div class="text-xs text-gray-700 ml-1">
        <strong>Trust Boundaryの不一致</strong>
        <ul class="list-disc list-inside mt-1 text-gray-600">
          <li>Agent: "EL is Untrusted" (Zero Trust)</li>
          <li>Contest: "EL is Trusted Component"</li>
        </ul>
        → EL入力を疑う指摘が全てInvalid判定。
      </div>
    </div>
    <div class="bg-blue-50 p-3 rounded-lg border border-blue-200">
      <div class="font-bold text-blue-800 mb-1 text-sm">教訓: AI精度の鍵は「前提条件」</div>
      <div class="text-xs text-gray-700">
        AIの推論能力ではなく、<strong>前提条件(Preconditions)の設定</strong>が精度を決定する。<br>
        <span class="text-gray-500 text-[10px] mt-1 block">
           (人間がスコープと信頼境界を正しく定義しない限り、AIは空振りする)
        </span>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-orange-800">その他の要因 (Analysis & Tool Issues)</div>

  <div class="p-3 bg-orange-50 rounded-lg border border-orange-200 space-y-3">
    <div>
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-orange-500 text-white text-[10px] px-1.5 py-0.5 rounded">Factor 1</span>
        <span class="text-xs font-bold text-gray-800">Insufficient Reachability</span>
      </div>
      <div class="text-xs text-gray-600 ml-1">
        ビルド対象外やMockコードへの過度な静的解析。<br>
        → 「動かないコード」のバグを報告してしまう。
      </div>
    </div>
    <div>
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-orange-500 text-white text-[10px] px-1.5 py-0.5 rounded">Factor 2</span>
        <span class="text-xs font-bold text-gray-800">Overlooking Defenses</span>
      </div>
      <div class="text-xs text-gray-600 ml-1">
        テストコードや設計書を除外したため、既存の防御ロジックを見落とす。<br>
        → 仕様通りの正当な挙動をバグと誤認。
      </div>
    </div>
    <div>
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-orange-500 text-white text-[10px] px-1.5 py-0.5 rounded">Factor 3</span>
        <span class="text-xs font-bold text-gray-800">Insufficient Cross-referencing</span>
      </div>
      <div class="text-xs text-gray-600 ml-1">
        既知のIssueや最新コードベースとの照合不足。<br>
        → 既に知られている問題の再報告（Duplicate）。
      </div>
    </div>

  </div>
</div>

</div>

<div class="absolute bottom-2 left-2 text-[8px] text-gray-400 max-w-[90%] leading-relaxed">
  <div><strong class="text-gray-500">[コンテストルール・脅威モデル]</strong> https://audits.sherlock.xyz/contests/1140</div>
</div>

<!--
誤検知（Invalid）の要因分析について詳しく説明します。

最大の要因は「脅威モデルの不一致」で、全体の27%を占めました。
我々はセキュリティの原則通り「実行層（EL）は信頼できない」として監査を行いましたが、コンテストのルールでは「ELは信頼済み」とされていました。
この「前提条件のズレ」により、正しい推論でもルール上は誤検知となってしまいました。

次に大きかったのが「解析手法」に起因する要因です。
1つ目はReachabilityの確認不足です。実際には動作しないMockコード等を解析してしまいました。
2つ目は既存の防御ロジックの見落としです。テストコードを除外したため、既にテストでカバーされている防御を見落としました。
3つ目は既知情報との照合不足です。既に報告済みのIssueを再発見し、Duplicateとなりました。

これらの結果は、AIの能力以前に、人間による「スコープ定義」と「情報供給」が重要であることを示しています。
-->
