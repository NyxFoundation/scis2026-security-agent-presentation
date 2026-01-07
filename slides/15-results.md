---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# コンテスト後の改善(2): Geth監査デモ結果

<div class="text-xs text-gray-600 mb-2">
  新アーキテクチャをGethコードベースに適用し、課題解決とセキュリティ検証を実施
</div>

<div class="grid grid-cols-2 gap-4 h-[80%]">
  <div class="flex flex-col h-full">
    <div class="font-bold text-sm mb-2 text-purple-700">Fusakaの課題への対応状況</div>
    <div class="flex-grow p-4 bg-purple-50 rounded border border-purple-200 text-xs flex flex-col justify-center space-y-4">
      <div>
        <div class="mb-1 text-gray-700 font-bold">✅ 課題1: 脅威モデルの不整合 → <span class="text-green-600">解決</span></div>
        <div class="bg-white p-2 rounded text-[10px] shadow-sm">
          <code class="text-blue-600">01b_TRUSTMODEL.json</code>で<strong>ELをTRUSTED</strong>と明示定義。<br>
          攻撃者による操作不可能な領域を正確に特定。
        </div>
      </div>
      <div>
        <div class="mb-1 text-gray-700 font-bold">✅ 課題2: チェックリストの網羅性 → <span class="text-green-600">解決</span></div>
        <div class="bg-white p-2 rounded text-[10px] shadow-sm">
          <div class="flex justify-between mb-1">
            <span>境界チェック: <span class="text-blue-600 font-bold">40項目</span></span>
            <span>プロパティ: <span class="text-blue-600 font-bold">180項目</span></span>
          </div>
          <div class="text-gray-500 border-t pt-1">
            → 合計<strong>220チェック</strong>を仕様から自動生成
          </div>
        </div>
      </div>
      <div>
        <div class="mb-1 text-gray-700 font-bold">✅ 課題3: 暗号検証の不足 → <span class="text-green-600">解決</span></div>
        <div class="bg-white p-2 rounded text-[10px] shadow-sm">
          <div class="italic text-gray-600">
            "Verify KZG commitment computation in crypto/kzg4844/"
          </div>
          <div class="mt-1">
             暗号ライブラリの呼び出し検証を必須チェックとして追加。
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="flex flex-col h-full">
    <div class="font-bold text-sm mb-2 text-orange-700">AUDITMAPでの監査結果</div>
    <div class="flex-grow p-4 bg-orange-50 rounded border border-orange-200 text-xs flex flex-col justify-center">      
      <div class="bg-white p-4 rounded shadow-sm mb-4">
        <div class="text-center mb-2 font-bold text-gray-700">監査対象: 重要コードパス 100件</div>
        <div class="flex justify-center items-end space-x-4">
          <div class="text-center">
            <div class="text-3xl font-bold text-green-600">80<span class="text-lg text-gray-500">件</span></div>
            <div class="text-[10px] font-bold text-green-700">Verified Secure</div>
          </div>
          <div class="text-center pb-1">
            <div class="text-xl font-bold text-gray-400">20<span class="text-sm">件</span></div>
            <div class="text-[9px] text-gray-500">Manual Review Required</div>
          </div>
        </div>
        <div class="text-center mt-2 text-green-600 font-bold text-lg">
          Coverage: 80%
        </div>
      </div>
      <div class="bg-white p-3 rounded shadow-sm">
        <div class="font-bold text-gray-700 mb-2 border-b pb-1">実施した分析手法</div>
        <ul class="list-disc list-inside space-y-1 text-[10px] text-gray-600">
          <li>5つの主要攻撃ベクトル分析 (Reentrancy, etc.)</li>
          <li>Guard Analysis (アクセス制御の検証)</li>
          <li>Data Flow Tracking (汚染解析)</li>
        </ul>
      </div>
    </div>
  </div>

</div>

<!--
続いて、この新アーキテクチャを用いたGeth監査デモの結果です。
Fusakaコンテストでの反省点が確実に対策されていることを確認しました。

左側をご覧ください。
課題1の「脅威モデル不整合」は、ELをTRUSTEDと定義することで解決しました。
課題2の「チェックリスト網羅性」は、グラフから220項目を自動生成することで解決しました。
課題3の「暗号検証不足」は、KZG commitment検証などを明示的にチェックリストに含めることで解決しました。

右側はAUDITMAPでの定量的な監査結果です。
100件の重要箇所を監査し、そのうち80%にあたる80件がverified-secureと判定されました。
全件に対して5つの攻撃ベクトル分析とGuard Analysisを適用し、高い精度で検証を行っています。
-->
