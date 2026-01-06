---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 驚くべき成果：報告件数No.1と「監査の民主化」

<div class="flex justify-center items-center gap-8 mt-2 mb-4">
  <div class="text-center p-4 bg-blue-50 rounded-lg">
    <div class="text-5xl font-bold text-blue-600 mb-1">17件</div>
    <div class="text-sm text-gray-600">有効脆弱性</div>
    <div class="text-xs text-red-600 font-bold mt-1">報告件数 No.1</div>
  </div>
  <div class="text-center p-4 bg-green-50 rounded-lg">
    <div class="text-5xl font-bold text-green-600 mb-1">31.5%</div>
    <div class="text-sm text-gray-600">Valid率</div>
    <div class="text-xs text-gray-500 mt-1">（全体平均: 27.6%）</div>
  </div>
</div>

<div class="grid grid-cols-2 gap-6">

<div>
  <div class="font-bold text-sm mb-2 text-center">戦略別 発見件数（グラフ）</div>
  <div class="bg-gray-50 p-3 rounded-lg">
    <div class="flex items-end gap-2 justify-center h-32">
      <div class="flex flex-col items-center">
        <div class="bg-green-500 w-16 rounded-t" style="height: 100px"></div>
        <div class="text-xs mt-1">類似探索</div>
        <div class="text-sm font-bold text-green-600">13件</div>
      </div>
      <div class="flex flex-col items-center">
        <div class="bg-blue-500 w-16 rounded-t" style="height: 23px"></div>
        <div class="text-xs mt-1">コード解析</div>
        <div class="text-sm font-bold text-blue-600">3件</div>
      </div>
      <div class="flex flex-col items-center">
        <div class="bg-purple-500 w-16 rounded-t" style="height: 8px"></div>
        <div class="text-xs mt-1">Fuzzing</div>
        <div class="text-sm font-bold text-purple-600">1件</div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="font-bold text-sm mb-2 text-yellow-700 text-center">「監査の民主化」の実証</div>
  <div class="p-3 bg-yellow-50 rounded-lg border-2 border-yellow-400">
    <div class="text-sm mb-2">
      <strong>非専門家が最多のバグを発見！</strong>
    </div>
    <div class="space-y-1 text-xs">
      <div class="flex justify-between bg-yellow-100 p-2 rounded font-bold">
        <span>vita (非専門家)</span>
        <span class="text-red-600 text-lg">8件 (Top)</span>
      </div>
      <div class="flex justify-between border-t pt-1">
        <span>gohan (著者)</span>
        <span>7件</span>
      </div>
      <div class="flex justify-between border-t pt-1">
        <span>他2名</span>
        <span>2件</span>
      </div>
    </div>
    <div class="mt-2 text-xs text-gray-600">
      適切なコンテキストがあれば、専門知識がなくても脆弱性発見が可能
    </div>
  </div>
</div>

</div>

<!--
結果の詳細です。

有効報告数は17件で、コンテスト参加者中、最多の報告件数となりました。
Valid率も31.5%と、全体平均の27.6%を上回っています。

左のグラフをご覧ください。
戦略別の有効性では「類似バグ探索」が圧倒的で、有効なバグの76.5%を占めています。

右側に注目していただきたいのですが、深いエンジニアリング経験を持たないvita氏が、チーム内で最多の8件のバグを発見しました。
これは「監査の民主化」、つまり専門家でなくとも適切なツールがあれば監査に参加できることを実証した重要な結果です。
-->
