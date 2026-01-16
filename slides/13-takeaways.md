---
layout: default
---

# 仕様チェックリスト監査は「発見」より「体系化と横展開」に強みがある

<div class="mt-4 space-y-3 text-sm">

<div class="p-3 bg-green-50 rounded border-l-4 border-green-500">
  <div class="flex items-start gap-3">
    <span class="text-2xl font-bold text-green-600">1</span>
    <div>
      <div class="font-bold">横断実装チェックは1件の発見を全実装に展開できる</div>
      <div class="text-gray-600">
        有効発見の <span class="font-bold text-green-700 text-lg">76.5%</span> が横展開由来
      </div>
    </div>
  </div>
</div>

<div class="p-3 bg-blue-50 rounded border-l-4 border-blue-500">
  <div class="flex items-start gap-3">
    <span class="text-2xl font-bold text-blue-600">2</span>
    <div>
      <div class="font-bold">偽陽性の過半はLLM能力ではなく脅威モデル不整合に起因</div>
      <div class="text-gray-600">
        <span class="font-bold text-blue-700 text-lg">56.8%</span> が前提条件のズレ → <span class="text-blue-600 font-bold">工程改善で対処可能</span>
      </div>
    </div>
  </div>
</div>

<div class="p-3 bg-red-50 rounded border-l-4 border-red-500">
  <div class="flex items-start gap-3">
    <span class="text-2xl font-bold text-red-600">3</span>
    <div>
      <div class="font-bold">高/中重大度検出には根本的限界がある</div>
      <div class="text-gray-600">
        検出率 <span class="font-bold text-red-700 text-lg">0%</span> → モデル検査等との統合が必要
      </div>
    </div>
  </div>
</div>

</div>

<div class="mt-4 flex justify-center">
  <div class="px-4 py-2 bg-gray-800 rounded text-center text-sm">
    <div class="font-bold text-white">LLMエージェント ≠ 万能の発見者</div>
    <div class="text-gray-300">LLMエージェント = パターン伝播者</div>
  </div>
</div>

<!--
3つの持ち帰りメッセージです。

第一に、横断実装チェックは有効発見の76.5%を占め、仕様チェックリストの横展開が多実装監査をスケールさせます。

第二に、偽陽性の56.8%は脅威モデル不整合に起因し、これはモデル能力向上ではなく工程改善で対処可能です。

第三に、高/中重大度検出率0%は根本的限界を示し、モデル検査やシンボリック実行との統合が今後の方向性です。

LLMエージェントは「万能の発見者」ではなく「パターン伝播者」として位置づけるべきです。

ご清聴ありがとうございました。ご質問をお受けします。
-->
