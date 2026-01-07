---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# Appendix: 補足データ

<div class="grid grid-cols-2 gap-3 mt-2">

<div>
  <div class="font-bold text-sm mb-1 text-blue-700">発見した脆弱性 (Valid 17件)</div>
  <div class="bg-gray-50 p-1.5 rounded text-[10px]">
    <div class="space-y-0.5">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-8">Sev</span>
        <span class="w-14">Client</span>
        <span>件数</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-8 text-yellow-600">Low</span>
        <span class="w-14">Nimbus</span>
        <span>1件 (#109: custody rotation DoS)</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-8 text-blue-600">Info</span>
        <span class="w-14">Nimbus</span>
        <span>5件</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-8 text-blue-600">Info</span>
        <span class="w-14">Grandine</span>
        <span>3件</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-8 text-blue-600">Info</span>
        <span class="w-14">Erigon</span>
        <span>2件</span>
      </div>
      <div class="flex gap-2 p-0.5">
        <span class="w-8 text-blue-600">Info</span>
        <span class="w-14">その他</span>
        <span>6件 (Besu, Lodestar, Nethermind, Teku, Prysm, Reth)</span>
      </div>
    </div>
  </div>

  <div class="font-bold text-sm mb-1 mt-2 text-green-700">類似バグリストの例</div>
  <div class="bg-gray-50 p-1.5 rounded text-[9px] font-mono">
    <div class="text-gray-500">// bugs_ethereum.json</div>
    <div class="text-blue-700">CVE-2023-42319: GraphQL DoS</div>
    <div class="text-blue-700">CL-2023-01: BlocksByRange溢れ</div>
    <div class="text-blue-700">CVE-2024-32649: Prysm panic</div>
    <div class="text-gray-500">...他50+件</div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-1 text-purple-700">参加者別の成績詳細</div>
  <div class="bg-gray-50 p-1.5 rounded text-[10px]">
    <div class="space-y-0.5">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-14">Auditor</span>
        <span class="w-8 text-center">Valid</span>
        <span class="w-14">戦略</span>
        <span>備考</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b bg-yellow-50 font-bold">
        <span class="w-14">vita</span>
        <span class="w-8 text-center">8</span>
        <span class="w-14">類似探索</span>
        <span>非専門家・最多</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-14">gohan</span>
        <span class="w-8 text-center">7</span>
        <span class="w-14">全戦略</span>
        <span>著者</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-14">adachi</span>
        <span class="w-8 text-center">1</span>
        <span class="w-14">コード解析</span>
        <span>-</span>
      </div>
      <div class="flex gap-2 p-0.5">
        <span class="w-14">tei</span>
        <span class="w-8 text-center">1</span>
        <span class="w-14">Fuzz</span>
        <span>-</span>
      </div>
    </div>
  </div>

  <div class="font-bold text-sm mb-1 mt-2 text-red-700">見逃したHigh/Medium (7件)</div>
  <div class="bg-gray-50 p-1.5 rounded text-[10px]">
    <div class="space-y-0.5">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-10">ID</span>
        <span class="w-8">Sev</span>
        <span class="w-20">Client</span>
        <span>概要</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#40</span>
        <span class="w-8 text-red-600">High</span>
        <span class="w-20">Specs</span>
        <span>Proposer計算</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#190</span>
        <span class="w-8 text-red-600">High</span>
        <span class="w-20">Prysm</span>
        <span>キャッシュ汚染</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#203</span>
        <span class="w-8 text-red-600">High</span>
        <span class="w-20">c-kzg</span>
        <span>Fiat-Shamir</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#176</span>
        <span class="w-8 text-red-600">High</span>
        <span class="w-20">Nethermind</span>
        <span>blob tx DoS</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#210</span>
        <span class="w-8 text-red-600">High</span>
        <span class="w-20">Nethermind</span>
        <span>blob検証</span>
      </div>
      <div class="flex gap-2 p-0.5 border-b">
        <span class="w-10">#15</span>
        <span class="w-8 text-orange-600">Med</span>
        <span class="w-20">Nimbus</span>
        <span>custody DoS</span>
      </div>
      <div class="flex gap-2 p-0.5">
        <span class="w-10">#216</span>
        <span class="w-8 text-orange-600">Med</span>
        <span class="w-20">Nimbus</span>
        <span>metadata</span>
      </div>
    </div>
  </div>
  
  <div class="font-bold text-sm mb-1 mt-2 text-orange-700">Geth監査デモ統計 (PR #12)</div>
  <div class="bg-orange-50 p-1.5 rounded text-[10px]">
    <div class="grid grid-cols-2 gap-1">
      <div>出力ファイル: <strong>28件</strong></div>
      <div>仕様 (01_SPEC): <strong>3,558行</strong></div>
      <div>境界チェック: <strong>40件</strong></div>
      <div>プロパティチェック: <strong>195件</strong></div>
    </div>
  </div>
</div>

</div>

<!--
Appendixとして補足データをまとめています。
発見した脆弱性のValid 17件のリスト、参加者別の成績詳細、見逃したHigh 5件・Medium 2件の全リストを掲載しています。
また、類似バグリストの例とGeth監査デモの統計も追加しています。
質疑応答でご質問があればこちらを参照いただけます。
-->
