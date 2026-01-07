---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# コンテスト後の改善: Program Graphベースのアーキテクチャ

<div class="text-xs text-gray-600 mb-1">
  Fusakaコンテストの課題を受け、アーキテクチャを刷新し、Geth監査デモで有効性を検証
</div>

<div class="grid grid-cols-2 gap-2">

<div>
  <div class="font-bold text-xs mb-1 text-blue-700">Program Graph: 仕様の形式化</div>
  <div class="p-1.5 bg-blue-50 rounded border border-blue-200">
    <img src="/images/program_graph_main.png" class="w-full max-h-32 object-contain rounded" />
    <div class="text-[8px] text-gray-600 text-center">
      <strong>CL/ELをTRUSTED</strong>として明示定義、<strong>信頼境界</strong>を越えるエッジを重点監査
    </div>
  </div>

  <div class="font-bold text-xs mb-1 mt-1.5 text-green-700">EIP別サブグラフ（例: EIP-4844 BLOBHASH）</div>
  <div class="p-1 bg-green-50 rounded border border-green-200">
    <img src="/images/program_graph_eip4844.png" class="w-full max-h-28 object-contain rounded" />
    <div class="text-[7px] text-gray-600 text-center">
      KZG commitment検証を含む20のEIP別サブグラフを定義
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-xs mb-1 text-purple-700">Geth監査デモ: Fusakaの課題への対応</div>
  <div class="p-1.5 bg-purple-50 rounded border border-purple-200 text-[9px]">
    <div class="mb-0.5 text-gray-700 font-bold text-[9px]">✅ 課題1: 脅威モデルの不整合 → 解決</div>
    <div class="bg-white p-1 rounded mb-1.5 text-[8px]">
      <code class="text-blue-600">01b_TRUSTMODEL.json</code>で<strong>ELをTRUSTED</strong>と明示定義
    </div>
    <div class="mb-0.5 text-gray-700 font-bold text-[9px]">✅ 課題2: チェックリストの網羅性 → 解決</div>
    <div class="bg-white p-1 rounded mb-1.5 text-[8px]">
      <div class="flex justify-between">
        <span>境界チェック <span class="text-blue-600 font-bold">40項目</span></span>
        <span>プロパティ <span class="text-blue-600 font-bold">180項目</span></span>
      </div>
      <div class="text-gray-500">→ 合計<strong>220チェック</strong>を自動生成</div>
    </div>
    <div class="mb-0.5 text-gray-700 font-bold text-[9px]">✅ 課題3: 暗号検証の不足 → 解決</div>
    <div class="bg-white p-1 rounded text-[8px]">
      <div class="text-[7px] text-gray-500 italic">
        "Verify KZG commitment computation in crypto/kzg4844/"
      </div>
    </div>
  </div>

  <div class="font-bold text-xs mb-1 mt-1.5 text-orange-700">AUDITMAPでの監査結果</div>
  <div class="p-1.5 bg-orange-50 rounded border border-orange-200 text-[9px]">
    <div class="bg-white p-1 rounded">
      <div class="flex justify-between text-[9px]">
        <span>監査済み <span class="text-blue-600 font-bold">100件</span></span>
        <span>verified-secure <span class="text-green-600 font-bold">80件 (80%)</span></span>
      </div>
      <div class="text-[8px] text-gray-500 mt-0.5">
        → 5つの攻撃ベクトル分析 + Guard Analysis適用
      </div>
    </div>
  </div>
</div>

</div>

<!--
Fusakaコンテストの課題を受け、アーキテクチャを刷新しました。
これは「今後の計画」ではなく、既に実装・検証済みの改善策です。

左側にProgram Graphの実際の出力を示しています。
Consensus Layer (CL) と Execution Layer (EL) の両方がTRUSTEDとして明示的に定義されています。
これにより、Fusakaで問題となった「ELを信頼しない」という誤った脅威モデルを根本的に解決しています。

EIP-4844 BLOBHASHのサブグラフも示しています。
このようにEIP別に20のサブグラフを定義し、KZG commitment検証などの暗号処理も監査対象としています。

右側にGeth監査デモの結果を示しています。
課題1の脅威モデル不整合は、01b_TRUSTMODEL.jsonでELをTRUSTEDと明示定義することで解決しました。
課題2のチェックリスト網羅性は、合計220チェックを自動生成することで解決しました。
課題3の暗号検証不足は、KZG commitment検証をチェックリストに含めることで解決しました。

AUDITMAPでは100件を監査し、80件がverified-secureと判定されました。
5つの攻撃ベクトル分析とGuard Analysisを全件に適用しています。
-->
