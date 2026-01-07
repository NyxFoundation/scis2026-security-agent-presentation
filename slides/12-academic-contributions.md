---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 学術的貢献と得られた知見

<div class="text-sm text-gray-600 mb-3">
  本研究がセキュリティ・AI研究コミュニティにもたらす新たな知見
</div>

<div class="grid grid-cols-2 gap-3">

<div class="space-y-2">
  <div class="font-bold text-blue-700 mb-1">Contribution 1: 手法の有効性実証</div>

  <div class="p-2 bg-blue-50 rounded-lg border-l-4 border-blue-500">
    <div class="font-bold text-sm mb-1">類似バグ探索の高い有効性</div>
    <div class="text-[10px] text-gray-600">
      発見された脆弱性の<strong class="text-blue-700">76.5% (13/17件)</strong>が類似バグ探索によるもの。<br>
      既知パターンの横展開が最も効果的な戦略であることを実証。
    </div>
    <div class="mt-1 bg-white p-1.5 rounded text-[9px]">
      <strong>根拠:</strong> bugs_ethereum.jsonに登録した50+の既知パターンを横展開
    </div>
  </div>

  <div class="p-2 bg-green-50 rounded-lg border-l-4 border-green-500">
    <div class="font-bold text-sm mb-1">監査の民主化</div>
    <div class="text-[10px] text-gray-600">
      非専門家(vita)が専門家(gohan)を上回る<strong class="text-green-700">8件</strong>の有効バグを発見。<br>
      適切なコンテキストがあれば、専門知識の差をAIが埋められることを実証。
    </div>
    <div class="mt-1 bg-white p-1.5 rounded text-[9px]">
      <strong>vita氏の全8件が「類似バグ探索」戦略</strong>
    </div>
  </div>
</div>

<div class="space-y-2">
  <div class="font-bold text-green-700 mb-1">Contribution 2: 設計指針の提示</div>

  <div class="p-2 bg-purple-50 rounded-lg border-l-4 border-purple-500">
    <div class="font-bold text-sm mb-1">チェックリスト駆動型ワークフロー</div>
    <div class="text-[10px] text-gray-600">
      高自由度エージェントより、タスク分割・段階的実行が効果的。<br>
      説明可能性（Explainability）の向上にも寄与。
    </div>
  </div>

  <div class="p-2 bg-orange-50 rounded-lg border-l-4 border-orange-500">
    <div class="font-bold text-sm mb-1">脅威モデル整合の重要性</div>
    <div class="text-[10px] text-gray-600">
      誤検知の主因は脅威モデル不一致。<br>
      事前のルール整合がAI監査の精度を決定する重要因子。
    </div>
  </div>
  
  <div class="p-2 bg-yellow-50 rounded-lg border-l-4 border-yellow-500">
    <div class="font-bold text-sm mb-1">研究サイクルの完遂</div>
    <div class="text-[10px] text-gray-600">
      課題発見 → 改善策実装 → 検証のサイクルを1回転。<br>
      Geth監査デモで改善版アーキテクチャの有効性を検証。
    </div>
  </div>
</div>

</div>

<div class="mt-2 p-2 bg-gray-100 rounded-lg">
  <div class="font-bold text-sm mb-1">Contribution 3: 限界の明確化</div>
  <div class="grid grid-cols-2 gap-3 text-[10px]">
    <div>
      <strong class="text-green-600">得意領域:</strong>
      <ul class="list-disc pl-4 mt-0.5 text-gray-600">
        <li>既知パターンの横展開 (76.5%)</li>
        <li>明確な仕様違反の検出</li>
        <li>繰り返しタスクの自動化</li>
      </ul>
    </div>
    <div>
      <strong class="text-red-600">苦手領域:</strong>
      <ul class="list-disc pl-4 mt-0.5 text-gray-600">
        <li>未知の攻撃手法 (High/Medium 0件発見)</li>
        <li>複雑な状態遷移の追跡</li>
        <li>仕様外（暗号ライブラリ等）のバグ</li>
      </ul>
    </div>
  </div>
</div>

<!--
最後に、本研究が得た学術的知見を3点にまとめます。

第1に、LLMエージェントによる脆弱性検知の有効性を実証しました。
特に「類似バグ探索」戦略が極めて有効であり、発見された脆弱性の76.5%、17件中13件がこの戦略によるものです。
また、非専門家のvita氏が専門家のgohan氏を上回る8件の有効バグを発見し、「監査の民主化」を実証しました。

第2に、AI監査における設計指針を提示しました。
自由度の高いエージェントよりも、チェックリストに基づく構造化されたワークフローが優れていること、そして「脅威モデルの事前整合」がシステムの精度を決定づける最重要因子であることを明らかにしました。
さらに、課題発見から改善策実装、検証のサイクルを1回転させ、Geth監査デモで改善版アーキテクチャの有効性を検証しました。

第3に、現状の限界を明確化しました。
既知パターンの横展開には強い一方で、High/Medium脆弱性は0件発見であり、未知の攻撃手法の発見には依然として人間の洞察が必要です。
-->
