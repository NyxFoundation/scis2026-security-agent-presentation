---
layout: two-cols
layoutClass: gap-6
---

# 教訓: プロンプト設計の知見

<div class="mt-4">

<div class="p-3 bg-red-50 rounded-lg border-l-4 border-red-400 mb-4">
  <div class="font-bold text-red-800 mb-1">初期アプローチの失敗</div>
  <ul class="text-xs list-disc pl-4 space-y-1">
    <li>DifyやLangChain等で「高自由度なエージェント」を構築</li>
    <li>適切なツール選択が行われず、検証プロセスが省略されたままレポート生成</li>
    <li>APIレート制限・レイテンシで試行回数を稼げず</li>
  </ul>
</div>

<div class="p-3 bg-green-50 rounded-lg border-l-4 border-green-400">
  <div class="font-bold text-green-800 mb-1">転換: チェックリスト駆動型へ</div>
  <ul class="text-xs list-disc pl-4 space-y-1">
    <li>タスクを細分化: 「仕様抽出」「コードマッピング」「攻撃経路分析」「レポート生成」</li>
    <li>各ステップの出力精度向上</li>
    <li>説明可能性 (Explainability) の向上</li>
  </ul>
</div>

</div>

::right::

<div class="mt-12">

<div class="p-4 bg-blue-50 rounded-lg border-2 border-blue-300">
  <div class="font-bold text-blue-800 mb-2">有効だった手法</div>

  <div class="text-sm mb-3">
    禁止事項の列挙よりも、<strong>Chain-of-Thought (CoT) で熟練監査員の思考プロセスを提示</strong>する方が効果的
  </div>

  <div class="bg-white p-2 rounded text-xs">
    <div class="font-bold mb-1">推論ステップの明示:</div>
    <ol class="list-decimal pl-4 space-y-0.5">
      <li>仕様と信頼境界を整理</li>
      <li>入力検証を評価</li>
      <li>境界チェックを評価</li>
      <li>スループット影響を評価</li>
    </ol>
  </div>

  <div class="bg-white p-2 rounded text-xs mt-2">
    <div class="font-bold mb-1">事後検証チェック:</div>
    <ul class="list-disc pl-4">
      <li>仕様定義データとの矛盾確認</li>
      <li>既知バグカタログとの重複確認</li>
    </ul>
  </div>
</div>

</div>

<!--
プロンプト設計から得られた教訓です。

開発初期段階では、DifyやLangChain等のフレームワークを使って「高自由度なエージェント」を構築しました。
しかし、エージェントが適切なツールを選択せず、必要な検証を省略したままレポートを生成してしまう問題が多発しました。

そこで方針を転換し、「チェックリスト駆動型」のワークフローを採用しました。
タスクを「仕様抽出」「コードマッピング」「攻撃経路分析」「レポート生成」に細分化することで、各ステップの出力精度が向上し、問題発生時の追跡も容易になりました。

また、禁止事項を大量に列挙するよりも、Chain-of-Thoughtを用いて「熟練監査員の思考プロセスそのもの」を提示する方が効果的であることがわかりました。
-->
