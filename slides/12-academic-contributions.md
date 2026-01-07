---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 学術的貢献と得られた知見

<div class="text-sm text-gray-600 mb-4">
  本研究がセキュリティ・AI研究コミュニティにもたらす新たな知見
</div>

<div class="grid grid-cols-2 gap-4">

<div class="space-y-3">
  <div class="font-bold text-blue-700 mb-2">Contribution 1: 手法の有効性実証</div>

  <div class="p-3 bg-blue-50 rounded-lg border-l-4 border-blue-500">
    <div class="font-bold text-sm mb-1">類似バグ探索の高い有効性</div>
    <div class="text-xs text-gray-600">
      発見された脆弱性の<strong>76.5%</strong>が類似バグ探索によるもの。
      既知パターンの横展開がLLMの強みを最大限活かす戦略であることを実証。
    </div>
  </div>

  <div class="p-3 bg-green-50 rounded-lg border-l-4 border-green-500">
    <div class="font-bold text-sm mb-1">仕様ベース監査の精度</div>
    <div class="text-xs text-gray-600">
      明確な仕様違反（#109のDoS脆弱性）を高精度で検出可能。
      仕様の形式化がLLM監査の前提条件となることを示唆。
    </div>
  </div>
</div>

<div class="space-y-3">
  <div class="font-bold text-green-700 mb-2">Contribution 2: 設計指針の提示</div>

  <div class="p-3 bg-purple-50 rounded-lg border-l-4 border-purple-500">
    <div class="font-bold text-sm mb-1">チェックリスト駆動型ワークフロー</div>
    <div class="text-xs text-gray-600">
      高自由度エージェントより、タスク分割・段階的実行が効果的。
      説明可能性（Explainability）の向上にも寄与。
    </div>
  </div>

  <div class="p-3 bg-orange-50 rounded-lg border-l-4 border-orange-500">
    <div class="font-bold text-sm mb-1">脅威モデル整合の重要性</div>
    <div class="text-xs text-gray-600">
      誤検知の27%は脅威モデル不一致が原因。
      事前のルール整合がAI監査の精度を決定する重要因子。
    </div>
  </div>
</div>

</div>

<div class="mt-4 p-3 bg-gray-100 rounded-lg">
  <div class="font-bold text-sm mb-2">Contribution 3: 限界の明確化</div>
  <div class="grid grid-cols-2 gap-4 text-xs">
    <div>
      <strong class="text-red-600">得意領域:</strong>
      <ul class="list-disc pl-4 mt-1 text-gray-600">
        <li>既知パターンの横展開</li>
        <li>明確な仕様違反の検出</li>
        <li>繰り返しタスクの自動化</li>
      </ul>
    </div>
    <div>
      <strong class="text-red-600">苦手領域:</strong>
      <ul class="list-disc pl-4 mt-1 text-gray-600">
        <li>未知の攻撃手法の発見</li>
        <li>複雑な状態遷移の追跡</li>
        <li>仕様外（暗号ライブラリ等）のバグ</li>
      </ul>
    </div>
  </div>
</div>

<!--
最後に、本研究が得た学術的知見を3点にまとめます。

第1に、LLMエージェントによる脆弱性検知の有効性を実証しました。
特に「類似バグ探索」戦略が極めて有効であり、既知のパターンを横展開することで、高効率に脆弱性を発見できることが定量的に示されました。

第2に、AI監査における設計指針を提示しました。
自由度の高いエージェントよりも、チェックリストに基づく構造化されたワークフローが優れていること、そして「脅威モデルの事前整合」がシステムの精度を決定づける最重要因子であることを明らかにしました。

第3に、現状の限界を明確化しました。
仕様違反の検出には強い一方で、未知の攻撃手法や複雑な状態遷移バグの発見には依然として人間の洞察が必要であるという境界線を引くことができました。
-->
