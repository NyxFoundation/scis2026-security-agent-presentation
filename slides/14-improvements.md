---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# コンテスト後の改善: Program Graphベースのアーキテクチャ

<div class="text-sm text-gray-600 mb-2">
  Fusakaコンテストの課題を受け、アーキテクチャを刷新し、Geth監査デモで有効性を検証
</div>

<div class="grid grid-cols-2 gap-3">

<div>
  <div class="font-bold text-sm mb-1 text-blue-700">Program Graph: 仕様の形式化</div>
  <div class="p-2 bg-blue-50 rounded-lg border border-blue-200 text-[9px]">
    <div class="bg-white p-2 rounded">
      <!-- Program Graph の図示 -->
      <div class="flex flex-col items-center">
        <div class="flex gap-2 mb-2">
          <div class="bg-red-100 border border-red-300 px-2 py-1 rounded text-center">
            <div class="font-bold text-red-700">External User</div>
            <div class="text-[8px] text-gray-500">UNTRUSTED</div>
          </div>
          <div class="bg-yellow-100 border border-yellow-300 px-2 py-1 rounded text-center">
            <div class="font-bold text-yellow-700">P2P Peer</div>
            <div class="text-[8px] text-gray-500">SEMI_TRUSTED</div>
          </div>
        </div>
        <div class="text-gray-400 text-lg">↓ Trust Boundary ↓</div>
        <div class="flex gap-2 mt-1">
          <div class="bg-green-100 border border-green-300 px-2 py-1 rounded text-center">
            <div class="font-bold text-green-700">TX Pool</div>
            <div class="text-[8px] text-gray-500">TRUSTED</div>
          </div>
          <div class="bg-green-100 border border-green-300 px-2 py-1 rounded text-center">
            <div class="font-bold text-green-700">EVM</div>
            <div class="text-[8px] text-gray-500">TRUSTED</div>
          </div>
          <div class="bg-green-100 border border-green-300 px-2 py-1 rounded text-center">
            <div class="font-bold text-green-700">State DB</div>
            <div class="text-[8px] text-gray-500">TRUSTED</div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-1 text-gray-600 text-center">
      <strong>信頼境界を明示化</strong>し、境界を越えるエッジを重点監査
    </div>
  </div>
  
  <div class="font-bold text-sm mb-1 mt-2 text-green-700">5つの攻撃ベクトル分析の義務化</div>
  <div class="p-2 bg-green-50 rounded-lg border border-green-200 text-[10px]">
    <div class="grid grid-cols-5 gap-1 text-center">
      <div class="bg-white p-1 rounded">
        <div class="font-bold text-red-600">DoS</div>
        <div class="text-[8px]">Memory</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold text-red-600">DoS</div>
        <div class="text-[8px]">CPU</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold text-orange-600">State</div>
        <div class="text-[8px]">Corruption</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold text-purple-600">Logic</div>
        <div class="text-[8px]">Error</div>
      </div>
      <div class="bg-white p-1 rounded">
        <div class="font-bold text-blue-600">Auth</div>
        <div class="text-[8px]">Bypass</div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-1 text-purple-700">Geth監査デモ: チェックリストの網羅性</div>
  <div class="p-2 bg-purple-50 rounded-lg border border-purple-200 text-[10px]">
    <div class="mb-1 text-gray-700">
      PR #12で改善版アーキテクチャをGethに適用し、チェックリストの網羅性を検証
    </div>
    <div class="bg-white p-1.5 rounded space-y-1">
      <div class="flex justify-between">
        <span>01_SPEC.json</span>
        <span class="text-blue-600 font-bold">3,558行</span>
      </div>
      <div class="text-[9px] text-gray-500 ml-2">→ 8アクター、12データ構造、サブグラフ定義</div>
      <div class="flex justify-between">
        <span>01b_TRUSTMODEL.json</span>
        <span class="text-blue-600 font-bold">217行</span>
      </div>
      <div class="text-[9px] text-gray-500 ml-2">→ 信頼境界12エッジを明示的に定義</div>
      <div class="flex justify-between">
        <span>02a_CHECKLIST_BOUNDARIES.json</span>
        <span class="text-blue-600 font-bold">40チェック</span>
      </div>
      <div class="text-[9px] text-gray-500 ml-2">→ 信頼境界に対する監査項目を自動生成</div>
      <div class="flex justify-between">
        <span>02b_CHECKLIST_*.json (9ファイル)</span>
        <span class="text-blue-600 font-bold">195チェック</span>
      </div>
      <div class="text-[9px] text-gray-500 ml-2">→ 各プロパティに対する監査項目</div>
    </div>
  </div>
  
  <div class="font-bold text-sm mb-1 mt-2 text-orange-700">改善のポイント</div>
  <div class="p-2 bg-orange-50 rounded-lg border border-orange-200 text-[10px]">
    <div class="space-y-1">
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>網羅性:</strong> 信頼境界12エッジ全てに監査項目を生成</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>トレーサビリティ:</strong> 仕様→プロパティ→チェックの追跡可能</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>Guard Analysis:</strong> 既存防御ロジックの検出を義務化</span>
      </div>
      <div class="flex items-start gap-1">
        <span class="text-green-600">✓</span>
        <span><strong>6カテゴリ判定:</strong> CONFIRMED/LIKELY/VERIFIED_SAFE等</span>
      </div>
    </div>
  </div>
</div>

</div>

<!--
Fusakaコンテストの課題を受け、アーキテクチャを刷新しました。
これは「今後の計画」ではなく、既に実装・検証済みの改善策です。

左上に「Program Graph」の概念図を示しています。
External UserはUNTRUSTED、P2P PeerはSEMI_TRUSTED、内部コンポーネント（TX Pool、EVM、State DB）はTRUSTEDとして明示的に定義します。
信頼境界を越えるエッジを重点的に監査することで、効率的な脆弱性発見が可能になります。

右側にGeth監査デモの結果を示しています。
PR #12で改善版アーキテクチャをGethに適用しました。
01_SPEC.jsonは3,558行で、8アクター、12データ構造、サブグラフを定義しています。
01b_TRUSTMODEL.jsonは217行で、信頼境界12エッジを明示的に定義しています。
02a_CHECKLIST_BOUNDARIES.jsonは40チェック、02b_CHECKLIST_*.jsonは9ファイルで195チェックを自動生成しました。

改善のポイントとして、網羅性、トレーサビリティ、Guard Analysis、6カテゴリ判定を実装しています。
-->
