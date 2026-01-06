---
layout: default
---

# まとめ

<div class="grid grid-cols-2 gap-6 mt-4">

<div>
  <div class="font-bold text-lg mb-3 text-green-700">成果 (Achievements)</div>
  <ul class="list-disc pl-4 space-y-2 text-sm">
    <li>
      <strong>類似バグ探索の有効性</strong><br>
      <span class="text-xs text-gray-600">有効報告の76.5%を占め、最も効果的な戦略</span>
    </li>
    <li>
      <strong>仕様ベース監査の成功</strong><br>
      <span class="text-xs text-gray-600">唯一のLow脆弱性 (#109) は仕様要件と実装の乖離を正確に指摘</span>
    </li>
    <li>
      <strong>監査の民主化を実証</strong><br>
      <span class="text-xs text-gray-600">非専門家 (vita) が最多のバグを発見。AIによる監査参加障壁の低下</span>
    </li>
    <li>
      <strong>報告件数No.1</strong><br>
      <span class="text-xs text-gray-600">コンテスト参加者中、最多の有効報告数を達成</span>
    </li>
  </ul>
</div>

<div>
  <div class="font-bold text-lg mb-3 text-red-700">限界 (Limitations)</div>
  <ul class="list-disc pl-4 space-y-2 text-sm">
    <li>
      <strong>High/Medium脆弱性は全件見逃し</strong><br>
      <span class="text-xs text-gray-600">致命的なバグの発見には至らず</span>
    </li>
    <li>
      <strong>仕様外のバグに対応困難</strong><br>
      <span class="text-xs text-gray-600">暗号ライブラリ、複雑な状態遷移</span>
    </li>
    <li>
      <strong>誤検知率68.5%</strong><br>
      <span class="text-xs text-gray-600">脅威モデル不一致が主因（改善可能）</span>
    </li>
  </ul>
</div>

</div>

<div class="mt-6 p-4 bg-gray-100 rounded text-center text-sm">
  <div class="font-bold text-lg mb-2">"AI監査の現在地"</div>
  <div>
    AI監査は<strong>『過去の類似バグ』</strong>と<strong>『明確な仕様違反』</strong>には極めて強いが、<br>
    <strong>未知の攻撃手法</strong>や<strong>複雑な状態遷移</strong>の発見には、まだ人間の直感と深い洞察が必要である。
  </div>
</div>

<!--
まとめです。

今回の実験で、「類似バグ探索」と「仕様ベース監査」が、既知のパターンや単純な仕様違反の発見に極めて強力であることが証明されました。
特に、専門家でなくともツールを使えばバグが見つけられる「監査の民主化」の可能性を示せたことは大きな成果です。

一方で、High/Mediumのような複雑なバグを見逃した事実も重く受け止めています。
仕様外の暗号ライブラリバグや、複雑な状態遷移に起因するバグは、現状のエージェントでは検出が困難でした。

結論として、AI監査は既知のパターンには強いものの、未知の攻撃手法や複雑なバグの発見には、まだ人間の洞察力が必要です。
今後は脅威モデルの整合と動的解析の統合を進め、より深いバグを発見できるエージェントへと進化させていきます。
-->
