---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 課題：なぜ誤検知が多かったのか？

<div class="text-sm text-gray-600 mb-3">
  68.5%の誤検知は「AIの能力不足」ではなく「設定のズレ」が原因
</div>

<div class="grid grid-cols-2 gap-4">

<div>
  <div class="bg-gray-100 rounded-lg p-3 mb-3 text-center">
    <div class="flex justify-center items-center gap-4">
      <div>
        <div class="text-sm text-gray-600">Valid率</div>
        <div class="text-2xl font-bold text-blue-600">31.5%</div>
      </div>
      <div class="text-2xl text-gray-300">|</div>
      <div>
        <div class="text-sm text-gray-600">Invalid率</div>
        <div class="text-2xl font-bold text-red-500">68.5%</div>
      </div>
    </div>
  </div>

  <div class="font-bold text-sm mb-2">誤検知の内訳（図解）</div>
  <div class="bg-gray-50 p-3 rounded-lg">
    <div class="flex items-end gap-1 h-24">
      <div class="flex flex-col items-center flex-1">
        <div class="bg-red-500 w-full rounded-t" style="height: 65px"></div>
        <div class="text-[10px] mt-1 text-center">脅威モデル<br>不一致</div>
        <div class="text-xs font-bold text-red-600">27%</div>
      </div>
      <div class="flex flex-col items-center flex-1">
        <div class="bg-orange-400 w-full rounded-t" style="height: 52px"></div>
        <div class="text-[10px] mt-1 text-center">判断基準<br>ズレ</div>
        <div class="text-xs font-bold text-orange-600">22%</div>
      </div>
      <div class="flex flex-col items-center flex-1">
        <div class="bg-yellow-400 w-full rounded-t" style="height: 32px"></div>
        <div class="text-[10px] mt-1 text-center">既知防御<br>見落とし</div>
        <div class="text-xs font-bold text-yellow-600">12%</div>
      </div>
      <div class="flex flex-col items-center flex-1">
        <div class="bg-gray-400 w-full rounded-t" style="height: 19px"></div>
        <div class="text-[10px] mt-1 text-center">その他</div>
        <div class="text-xs font-bold text-gray-600">8%</div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="p-3 bg-red-50 rounded-lg border-2 border-red-400 mb-3">
    <div class="font-bold text-red-800 mb-2">最大要因：脅威モデルの不一致</div>
    <div class="grid grid-cols-2 gap-2 text-xs mb-2">
      <div class="bg-white p-2 rounded">
        <div class="font-bold text-gray-600">Our Prompt</div>
        <div class="text-red-600">「ELは信頼しない」</div>
      </div>
      <div class="bg-white p-2 rounded">
        <div class="font-bold text-gray-600">Contest Rule</div>
        <div class="text-green-600">「ELは信頼できる」</div>
      </div>
    </div>
    <div class="text-xs text-gray-600">
      → EL入力を疑う指摘が全て「ルール上問題なし」として却下
    </div>
  </div>

  <div class="p-3 bg-blue-50 rounded-lg border border-blue-300">
    <div class="font-bold text-blue-800 mb-2">重要な示唆</div>
    <div class="text-xs space-y-1">
      <div class="flex items-start gap-2">
        <span class="text-green-500">✓</span>
        <span>誤検知の多くは<strong>事前設定</strong>で防げる</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="text-green-500">✓</span>
        <span>AIの推論能力自体は問題ではない</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="text-green-500">✓</span>
        <span>脅威モデルの事前調整で大幅改善可能</span>
      </div>
    </div>
  </div>
</div>

</div>

<div class="absolute bottom-2 left-2 text-[8px] text-gray-400 max-w-[90%] leading-relaxed">
  <div><strong class="text-gray-500">[コンテストルール・脅威モデル]</strong> https://audits.sherlock.xyz/contests/1140</div>
</div>

<!--
誤検知の分析です。
6割以上がInvalid判定を受けましたが、これには明確な理由がありました。

グラフをご覧ください。
最大の要因は「脅威モデルの不一致」で、全体の27%を占めています。

我々のプロンプトでは「実行層クライアントは信頼できない」という厳格なゼロトラスト設定をしていました。
しかしコンテストのルールでは「実行層は信頼できるものとする」と定義されていました。

このため、ELからの入力を疑う指摘が全て「ルール上問題なし」として却下されました。

重要なのは、これはAIの能力不足ではなく、設定のズレが原因だということです。
脅威モデルを事前に正しく設定していれば、大幅に改善できたはずです。
-->
