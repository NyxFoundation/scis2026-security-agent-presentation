---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# Appendix: 補足データ

<div class="grid grid-cols-2 gap-4 mt-2">

<div>
  <div class="font-bold text-sm mb-2 text-blue-700">発見した脆弱性の全リスト</div>
  <div class="bg-gray-50 p-2 rounded text-xs">
    <div class="space-y-1">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-12">ID</span>
        <span class="w-10">Sev</span>
        <span class="w-16">Client</span>
        <span>概要</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#109</span>
        <span class="w-10 text-blue-600">Low</span>
        <span class="w-16">Nimbus</span>
        <span>custody DoS</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#45</span>
        <span class="w-10">Info</span>
        <span class="w-16">Erigon</span>
        <span>高ガスTx残存</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#31-33</span>
        <span class="w-10">Info</span>
        <span class="w-16">Grandine</span>
        <span>backfill系</span>
      </div>
      <div class="flex gap-2 p-1">
        <span class="w-12">#27</span>
        <span class="w-10">Info</span>
        <span class="w-16">Prysm</span>
        <span>status偽装</span>
      </div>
      <div class="text-gray-500 p-1">...他13件</div>
    </div>
  </div>

  <div class="font-bold text-sm mb-2 mt-3 text-green-700">コンテキストエンジニアリング</div>
  <div class="bg-gray-50 p-2 rounded text-xs">
    <ul class="list-disc pl-4 space-y-1">
      <li>仕様サマリと脅威モデルの一本化</li>
      <li>仕様IDに基づくスコープ縮小</li>
      <li>数十行スニペット単位での粒度制御</li>
      <li>JSON永続化による状態管理</li>
    </ul>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-purple-700">参加者別の成績詳細</div>
  <div class="bg-gray-50 p-2 rounded text-xs">
    <div class="space-y-1">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-16">Auditor</span>
        <span class="w-10 text-center">検出</span>
        <span class="w-16">戦略</span>
        <span>備考</span>
      </div>
      <div class="flex gap-2 p-1 border-b bg-yellow-50 font-bold">
        <span class="w-16">vita</span>
        <span class="w-10 text-center">8</span>
        <span class="w-16">類似探索</span>
        <span>非専門家</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-16">gohan</span>
        <span class="w-10 text-center">7</span>
        <span class="w-16">全戦略</span>
        <span>著者</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-16">adachi</span>
        <span class="w-10 text-center">1</span>
        <span class="w-16">コード解析</span>
        <span>-</span>
      </div>
      <div class="flex gap-2 p-1">
        <span class="w-16">tei</span>
        <span class="w-10 text-center">1</span>
        <span class="w-16">コード解析</span>
        <span>-</span>
      </div>
    </div>
  </div>

  <div class="font-bold text-sm mb-2 mt-3 text-red-700">見逃したHigh/Medium全リスト</div>
  <div class="bg-gray-50 p-2 rounded text-xs">
    <div class="space-y-1">
      <div class="flex gap-2 bg-gray-100 p-1 rounded font-bold">
        <span class="w-12">ID</span>
        <span class="w-10">Sev</span>
        <span>概要</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#203</span>
        <span class="w-10 text-red-600">High</span>
        <span>c-kzg Fiat-Shamir</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#190</span>
        <span class="w-10 text-red-600">High</span>
        <span>Prysm キャッシュ</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#176</span>
        <span class="w-10 text-red-600">High</span>
        <span>Nethermind blob</span>
      </div>
      <div class="flex gap-2 p-1 border-b">
        <span class="w-12">#15</span>
        <span class="w-10 text-orange-600">Med</span>
        <span>Nimbus metadata</span>
      </div>
    </div>
  </div>
</div>

</div>

<!--
Appendixとして補足データをまとめています。
発見した脆弱性の全リスト、参加者別の成績詳細、見逃したHigh/Mediumの全リストを掲載しています。
質疑応答でご質問があればこちらを参照いただけます。
-->
