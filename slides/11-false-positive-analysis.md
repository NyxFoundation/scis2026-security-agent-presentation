---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜ誤検知が多かったのか？

<div class="text-sm text-gray-600 mb-2">
  誤検知は「AIの能力不足」ではなく「前提条件のズレ」が原因
</div>

<div class="grid grid-cols-2 gap-3">

<div>
  <div class="font-bold text-sm mb-1 text-center">誤検知の主要因 (Invalid: 37件)</div>
  
  <div class="space-y-2">
    <div class="bg-red-50 p-2 rounded-lg border border-red-200">
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-red-600 text-white text-[9px] px-1.5 py-0.5 rounded">主因</span>
        <span class="text-sm font-bold text-red-800">脅威モデル不整合</span>
      </div>
      <div class="text-[10px] text-gray-700">
        <div class="bg-white p-1.5 rounded mt-1">
          <div class="font-bold">具体例: Besu #52, #53, Lighthouse #8</div>
          <div class="text-gray-600">Agent: "ELは信頼できない"</div>
          <div class="text-gray-600">Contest: "ELは信頼済み"</div>
          <div class="text-red-600">→ EL入力を疑う指摘が全てInvalid</div>
        </div>
      </div>
    </div>    
    <div class="bg-orange-50 p-2 rounded-lg border border-orange-200">
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-orange-500 text-white text-[9px] px-1.5 py-0.5 rounded">要因</span>
        <span class="text-sm font-bold text-orange-800">既存ガード見落とし</span>
      </div>
      <div class="text-[10px] text-gray-700">
        <div class="bg-white p-1.5 rounded mt-1">
          <div class="font-bold">具体例: Besu #16, #18</div>
          <div class="text-gray-600">実装済みの防御ロジックを検出できず</div>
          <div class="text-orange-600">→ 仕様通りの挙動をバグと誤認</div>
        </div>
      </div>
    </div>
    <div class="bg-yellow-50 p-2 rounded-lg border border-yellow-200">
      <div class="flex items-center gap-2 mb-1">
        <span class="bg-yellow-500 text-white text-[9px] px-1.5 py-0.5 rounded">要因</span>
        <span class="text-sm font-bold text-yellow-800">到達不可能コード</span>
      </div>
      <div class="text-[10px] text-gray-700">
        <div class="bg-white p-1.5 rounded mt-1">
          <div class="font-bold">具体例: Nimbus #4, #5</div>
          <div class="text-gray-600">未使用コードパスを報告</div>
          <div class="text-yellow-600">→ ビルド対象外のコードを解析</div>
        </div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-1 text-blue-800">教訓と対策</div>

  <div class="p-2 bg-blue-50 rounded-lg border border-blue-200 mb-2">
    <div class="font-bold text-blue-800 mb-1 text-sm">AI精度の鍵は「前提条件」</div>
    <div class="text-[10px] text-gray-700">
      AIの推論能力ではなく、<strong>前提条件(Preconditions)の設定</strong>が精度を決定する。<br>
      <span class="text-gray-500 mt-1 block">
         (人間がスコープと信頼境界を正しく定義しない限り、AIは空振りする)
      </span>
    </div>
  </div>

  <div class="p-2 bg-green-50 rounded-lg border border-green-200">
    <div class="font-bold text-green-800 mb-1 text-sm">改善後の対策（実装済み）</div>
    <div class="text-[10px] space-y-1">
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>Trust Model明示化:</strong> TRUSTED/SEMI_TRUSTED/UNTRUSTED</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>6カテゴリ判定:</strong> CONFIRMED/LIKELY/VERIFIED_SAFE等</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>到達性検証:</strong> ビルド対象外コードの除外</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>Guard Analysis:</strong> 既存防御ロジックの検出を義務化</span>
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

最大の要因は「脅威モデルの不一致」でした。
具体例として、Besu #52, #53、Lighthouse #8があります。
我々はセキュリティの原則通り「実行層（EL）は信頼できない」として監査を行いましたが、コンテストのルールでは「ELは信頼済み」とされていました。
この「前提条件のズレ」により、正しい推論でもルール上は誤検知となってしまいました。

次に大きかったのが「既存ガードの見落とし」です。
Besu #16, #18のように、実装済みの防御ロジックを検出できず、仕様通りの挙動をバグと誤認しました。

3つ目は「到達不可能コード」です。
Nimbus #4, #5のように、ビルド対象外の未使用コードパスを報告してしまいました。

右側に教訓と対策を示しています。
改善後のアーキテクチャでは、Trust Modelの明示化、6カテゴリ判定システム、到達性検証、Guard Analysisを実装しました。
-->
