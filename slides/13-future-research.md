---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 今後の研究方向

<div class="text-sm text-gray-600 mb-3">
  改善版でもなお残る課題と、中長期的な研究の方向性
</div>

<div class="grid grid-cols-2 gap-4">

<div>
  <div class="font-bold text-sm mb-2 text-red-700">残された課題</div>

  <div class="space-y-2">
    <div class="p-2 bg-red-50 rounded-lg border border-red-200">
      <div class="font-bold text-sm text-red-800">High/Medium脆弱性の見逃し</div>
      <div class="text-[10px] text-gray-600 mt-1">
        High 5件・Medium 2件を全て見逃し。<br>
        未知の攻撃手法、複雑な状態遷移バグの検出が困難。
      </div>
    </div>
    <div class="p-2 bg-orange-50 rounded-lg border border-orange-200">
      <div class="font-bold text-sm text-orange-800">暗号ライブラリの監査</div>
      <div class="text-[10px] text-gray-600 mt-1">
        c-kzgのFiat-Shamir脆弱性(#203)は専門知識が必要。<br>
        現状のLLMでは暗号実装の正当性検証は困難。
      </div>
    </div>
    <div class="p-2 bg-yellow-50 rounded-lg border border-yellow-200">
      <div class="font-bold text-sm text-yellow-800">EL側のカバレッジ</div>
      <div class="text-[10px] text-gray-600 mt-1">
        CL中心の監査となり、EL（Geth, Nethermind等）の<br>
        カバレッジが不十分。
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-blue-700">中長期研究の方向性</div>

  <div class="space-y-2">
    <div class="p-2 bg-blue-50 rounded-lg border border-blue-200">
      <div class="flex items-center gap-2">
        <span class="bg-blue-500 text-white px-2 py-0.5 rounded text-[10px]">研究</span>
        <span class="font-bold text-sm">マルチエージェント協調</span>
      </div>
      <div class="text-[10px] text-gray-600 mt-1">
        専門エージェント（暗号、P2P、状態管理）の協調による<br>
        カバレッジ向上と専門性の補完。
      </div>
    </div>
    <div class="p-2 bg-purple-50 rounded-lg border border-purple-200">
      <div class="flex items-center gap-2">
        <span class="bg-purple-500 text-white px-2 py-0.5 rounded text-[10px]">研究</span>
        <span class="font-bold text-sm">形式検証との融合</span>
      </div>
      <div class="text-[10px] text-gray-600 mt-1">
        LLMが生成した仮説をモデル検査器で検証。<br>
        状態遷移バグの検出精度向上。
      </div>
    </div>
    <div class="p-2 bg-green-50 rounded-lg border border-green-200">
      <div class="flex items-center gap-2">
        <span class="bg-green-500 text-white px-2 py-0.5 rounded text-[10px]">応用</span>
        <span class="font-bold text-sm">サプライチェーン統合</span>
      </div>
      <div class="text-[10px] text-gray-600 mt-1">
        cargo audit等の依存ライブラリスキャンとの統合。<br>
        外部ライブラリの脆弱性も検出範囲に。
      </div>
    </div>
  </div>
</div>

</div>

<div class="mt-3 p-2 bg-gray-100 rounded-lg text-center">
  <div class="text-sm">
    <strong>目標:</strong> 
    <span class="text-red-600">High/Medium発見 0件</span> → 
    <span class="text-green-600">少なくとも1件以上</span> を次の研究サイクルで達成
  </div>
</div>

<!--
改善版でもなお残る課題と、中長期的な研究の方向性について説明します。

左側に残された課題を示しています。
まず、High 5件・Medium 2件を全て見逃しており、未知の攻撃手法や複雑な状態遷移バグの検出が困難です。
次に、c-kzgのFiat-Shamir脆弱性のような暗号ライブラリの監査は、専門知識が必要であり、現状のLLMでは困難です。
また、CL中心の監査となり、EL側のカバレッジが不十分という課題もあります。

右側に中長期研究の方向性を示しています。
マルチエージェント協調では、暗号、P2P、状態管理などの専門エージェントが協調することで、カバレッジ向上と専門性の補完を目指します。
形式検証との融合では、LLMが生成した仮説をモデル検査器で検証し、状態遷移バグの検出精度向上を図ります。
サプライチェーン統合では、cargo audit等の依存ライブラリスキャンと統合し、外部ライブラリの脆弱性も検出範囲に含めます。

目標は、High/Medium発見を0件から少なくとも1件以上に改善することです。
-->
