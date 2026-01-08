---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# コンテスト後の改善: 形式的なチェックリスト生成

<div class="text-xs text-gray-600 mb-3">
  Fusakaコンテストの課題を受け、4フェーズの構造化ワークフローに刷新
</div>

<div class="grid grid-cols-4 gap-2 h-[75%]">

  <!-- Phase 1: SPEC -->
  <div class="bg-blue-50 border border-blue-300 rounded p-2 flex flex-col">
    <div class="text-center mb-1">
      <div class="font-bold text-blue-700 text-xs">Phase 1: SPEC</div>
      <div class="text-[9px] text-gray-600">仕様の形式化</div>
    </div>
    <div class="flex-grow flex flex-col justify-center">
      <img src="/images/program_graph_main.png" class="w-full max-h-60 object-contain rounded mb-1" />
      <div class="text-[7px] text-gray-600 text-center">
        <code class="bg-white px-0.5 rounded">01_SPEC.json</code>
      </div>
      <div class="text-[7px] text-center mt-1 space-y-0.5">
        <div><strong>29</strong> ノード</div>
        <div><strong>32</strong> エッジ</div>
        <div><strong>20</strong> サブグラフ</div>
      </div>
    </div>
  </div>

  <!-- Phase 2: TRUSTMODEL -->
  <div class="bg-green-50 border border-green-300 rounded p-2 flex flex-col">
    <div class="text-center mb-1">
      <div class="font-bold text-green-700 text-xs">Phase 2: TRUSTMODEL</div>
      <div class="text-[9px] text-gray-600">信頼境界定義</div>
    </div>
    <div class="flex-grow flex flex-col justify-center">
      <div class="text-[7px] text-gray-600 text-center mb-1">
        <code class="bg-white px-0.5 rounded">01b_TRUSTMODEL.json</code>
      </div>
      <div class="bg-white p-1.5 rounded text-[7px] font-mono space-y-1">
        <div class="flex justify-between">
          <span>CL</span>
          <span class="text-green-600 font-bold">TRUSTED</span>
        </div>
        <div class="flex justify-between">
          <span>EL</span>
          <span class="text-green-600 font-bold">TRUSTED</span>
        </div>
        <div class="flex justify-between">
          <span>User</span>
          <span class="text-red-600 font-bold">UNTRUSTED</span>
        </div>
        <div class="flex justify-between">
          <span>P2P</span>
          <span class="text-yellow-600 font-bold">SEMI_TRUSTED</span>
        </div>
      </div>
      <div class="text-[7px] text-center mt-2 text-green-700 font-bold">
        8アクター定義
      </div>
      <div class="text-[7px] text-center mt-1 text-gray-600">
        → ELをTRUSTEDと明示
      </div>
    </div>
  </div>

  <!-- Phase 3: CHECKLIST -->
  <div class="bg-purple-50 border border-purple-300 rounded p-2 flex flex-col">
    <div class="text-center mb-1">
      <div class="font-bold text-purple-700 text-xs">Phase 3: CHECKLIST</div>
      <div class="text-[9px] text-gray-600">監査項目生成</div>
    </div>
    <div class="flex-grow flex flex-col justify-center">
      <div class="text-[7px] text-gray-600 text-center mb-1">
        <code class="bg-white px-0.5 rounded">02a/02b_*.json</code>
      </div>
      <div class="bg-white p-1.5 rounded text-[6px] font-mono">
        <div class="text-gray-500">// 境界チェック例</div>
        <div class="truncate">"Verify Trust Boundary for EDGE-USER-SUBMIT-TX"</div>
        <div class="text-gray-500 mt-1">// KZG検証</div>
        <div class="truncate">"Verify KZG commitment in crypto/kzg4844/"</div>
      </div>
      <div class="mt-2 space-y-1 text-[8px] text-center">
        <div>境界: <strong>40</strong>項目</div>
        <div>プロパティ: <strong>180</strong>項目</div>
        <div class="text-purple-700 font-bold">計: 220項目</div>
      </div>
    </div>
  </div>

  <!-- Phase 4: AUDITMAP -->
  <div class="bg-orange-50 border border-orange-300 rounded p-2 flex flex-col">
    <div class="text-center mb-1">
      <div class="font-bold text-orange-700 text-xs">Phase 4: AUDITMAP</div>
      <div class="text-[9px] text-gray-600">5攻撃ベクトル分析</div>
    </div>
    <div class="flex-grow flex flex-col justify-center">
      <div class="text-[7px] text-gray-600 text-center mb-1">
        <code class="bg-white px-0.5 rounded">03_AUDITMAP_*.json</code>
      </div>
      <div class="bg-white p-1.5 rounded text-[6px] font-mono">
        <div>"attack_vector_analysis":</div>
        <div class="ml-1">• input_validation_bypass</div>
        <div class="ml-1">• state_transition_violation</div>
        <div class="ml-1">• resource_exhaustion</div>
        <div class="ml-1">• faulty_error_handling</div>
        <div class="ml-1">• race_conditions</div>
      </div>
      <div class="bg-white p-1 rounded mt-1 text-[7px] text-center">
        <span class="text-gray-500">classification:</span>
        <span class="text-green-600 font-bold">verified-secure</span>
      </div>
    </div>
  </div>

</div>

<!--
Fusakaコンテストの課題を受け、アーキテクチャを4フェーズの構造化ワークフローに刷新し、より形式的にチェックリスト生成をできるようにしました。

Phase 1のSPECでは、仕様をProgram Graphとして形式化します。
29ノード、32エッジ、20のEIP別サブグラフを定義しています。

Phase 2のTRUSTMODELでは、8アクターの信頼レベルを明示的に定義します。
CLとELをTRUSTED、UserをUNTRUSTED、P2PをSEMI_TRUSTEDと定義しています。
これにより、Fusakaで問題となった脅威モデル不整合を解決しました。

Phase 3のCHECKLISTでは、Program Graphから監査項目を自動生成します。
境界チェック40項目、プロパティチェック180項目、合計220項目です。
KZG commitment検証なども含まれています。

Phase 4のAUDITMAPでは、各チェック項目に対して5つの攻撃ベクトルを体系的に分析します。
分析結果はverified-secureなどの分類で出力されます。
-->
