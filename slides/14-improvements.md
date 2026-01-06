---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 今後の展望と改善アクション

<div class="grid grid-cols-2 gap-4 mt-2">

<div>
  <div class="font-bold text-sm mb-2 text-blue-700">短期改善（次回コンテストまで）</div>

  <div class="space-y-2">
    <div class="p-2 bg-red-50 rounded border-l-4 border-red-500">
      <div class="flex items-center gap-2">
        <span class="bg-red-600 text-white px-2 py-1 rounded text-xs">最優先</span>
        <span class="font-bold text-sm">脅威モデル整合</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        コンテストルールを事前精査し、プロンプトに正確反映
      </div>
    </div>
    <div class="p-2 bg-orange-50 rounded border-l-4 border-orange-400">
      <div class="flex items-center gap-2">
        <span class="bg-orange-500 text-white px-2 py-1 rounded text-xs">高</span>
        <span class="font-bold text-sm">動的解析の統合</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        Fuzzing・プロパティテストの自動生成を強化
      </div>
    </div>
    <div class="p-2 bg-orange-50 rounded border-l-4 border-orange-400">
      <div class="flex items-center gap-2">
        <span class="bg-orange-500 text-white px-2 py-1 rounded text-xs">高</span>
        <span class="font-bold text-sm">プロンプト拡張</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        キャッシュ汚染・暗号実装不備等の脆弱性クラス追加
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-green-700">中長期研究（今後の方向性）</div>

  <div class="space-y-2">
    <div class="p-2 bg-yellow-50 rounded border-l-4 border-yellow-500">
      <div class="flex items-center gap-2">
        <span class="bg-yellow-500 text-white px-2 py-1 rounded text-xs">中</span>
        <span class="font-bold text-sm">サプライチェーン統合</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        cargo audit等の依存ライブラリスキャン
      </div>
    </div>
    <div class="p-2 bg-blue-50 rounded border-l-4 border-blue-400">
      <div class="flex items-center gap-2">
        <span class="bg-blue-500 text-white px-2 py-1 rounded text-xs">研究</span>
        <span class="font-bold text-sm">マルチエージェント協調</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        複数の専門エージェントによる協調的脆弱性探索
      </div>
    </div>
    <div class="p-2 bg-purple-50 rounded border-l-4 border-purple-400">
      <div class="flex items-center gap-2">
        <span class="bg-purple-500 text-white px-2 py-1 rounded text-xs">研究</span>
        <span class="font-bold text-sm">形式検証との融合</span>
      </div>
      <div class="text-xs text-gray-600 mt-1">
        LLMが生成した仮説を形式手法で検証
      </div>
    </div>
  </div>
</div>

</div>

<div class="mt-3 p-2 bg-blue-100 rounded-lg text-center border border-blue-300">
  <div class="font-bold text-sm">
    <span class="text-red-600">High/Medium脆弱性の発見率向上</span>
    <span class="mx-2">&</span>
    <span class="text-blue-600">誤検知率の大幅削減</span>
  </div>
</div>

<!--
今回の経験を踏まえた改善アクションをまとめました。

短期的には、まず「脅威モデルの整合」が最優先です。
コンテストルールを事前に精査し、プロンプトに正確に反映させます。

次に「動的解析の統合」と「プロンプト拡張」です。
Fuzzingを強化し、キャッシュ汚染や暗号実装不備など、仕様ベース以外の攻撃面もカバーするプロンプトを追加します。

中長期的には、サプライチェーンスキャンの統合、マルチエージェント協調、形式検証との融合といった研究を進めていきます。

目標は、High/Medium脆弱性の発見率向上と、誤検知率の大幅削減です。
-->
