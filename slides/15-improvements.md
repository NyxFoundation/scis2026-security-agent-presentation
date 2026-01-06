---
layout: default
---

# 改善アクション

<div class="mt-2">

<table class="w-full text-sm">
  <thead class="bg-gray-100">
    <tr>
      <th class="p-2 text-left w-24">優先度</th>
      <th class="p-2 text-left">アクション</th>
      <th class="p-2 text-left">詳細</th>
    </tr>
  </thead>
  <tbody>
    <tr class="bg-red-50">
      <td class="p-2 border-b"><span class="bg-red-600 text-white px-2 py-0.5 rounded text-xs">最優先</span></td>
      <td class="p-2 border-b font-bold">脅威モデル整合</td>
      <td class="p-2 border-b text-xs">コンテスト開始前にEL/CL信頼境界をプロンプトに正確反映。事前にルールを精査し、脅威モデルの齟齬を排除。</td>
    </tr>
    <tr class="bg-orange-50">
      <td class="p-2 border-b"><span class="bg-orange-500 text-white px-2 py-0.5 rounded text-xs">高</span></td>
      <td class="p-2 border-b font-bold">分析手法の多様化</td>
      <td class="p-2 border-b text-xs">静的解析に加え、Fuzzing・プロパティテストを自動生成。「思い込み」による見逃しを排除。</td>
    </tr>
    <tr class="bg-orange-50">
      <td class="p-2 border-b"><span class="bg-orange-500 text-white px-2 py-0.5 rounded text-xs">高</span></td>
      <td class="p-2 border-b font-bold">プロンプト拡張</td>
      <td class="p-2 border-b text-xs">キャッシュ汚染、暗号実装不備など脆弱性クラス別の探索プロンプトを追加。仕様ベース以外の攻撃面もカバー。</td>
    </tr>
    <tr>
      <td class="p-2 border-b"><span class="bg-yellow-500 text-white px-2 py-0.5 rounded text-xs">中</span></td>
      <td class="p-2 border-b font-bold">サプライチェーン統合</td>
      <td class="p-2 border-b text-xs"><code>cargo audit</code>等の依存ライブラリスキャンをパイプラインに組込。外部ライブラリの脆弱性も自動検出。</td>
    </tr>
    <tr>
      <td class="p-2 border-b"><span class="bg-yellow-500 text-white px-2 py-0.5 rounded text-xs">中</span></td>
      <td class="p-2 border-b font-bold">到達可能性検証</td>
      <td class="p-2 border-b text-xs">報告前に静的解析ツールでコード到達性を確認。ビルド対象外・モックコードへの誤報告を防止。</td>
    </tr>
    <tr>
      <td class="p-2"><span class="bg-gray-500 text-white px-2 py-0.5 rounded text-xs">低</span></td>
      <td class="p-2 font-bold">情報収集範囲拡大</td>
      <td class="p-2 text-xs">テストコード・設計文書も除外せずコンテキストに含める。既存防御策の見落としを防止。</td>
    </tr>
  </tbody>
</table>

</div>

<div class="mt-4 p-3 bg-blue-50 rounded text-sm text-center">
  <strong>目標:</strong> High/Medium脆弱性の発見率向上 & 誤検知率の大幅削減
</div>

<!--
最後に、今回の経験を踏まえた改善アクションをまとめました。

最優先は「脅威モデルの整合」です。
コンテスト開始前にルールを精査し、EL/CLの信頼境界をプロンプトに正確に反映させることで、脅威モデルの齟齬による誤検知を大幅に削減できます。

次に優先度が高いのは「分析手法の多様化」と「プロンプト拡張」です。
静的解析だけでなく、Fuzzingやプロパティテストを自動生成することで、複雑な状態遷移のバグを検出できるようにします。
また、キャッシュ汚染や暗号実装不備など、仕様ベース以外の攻撃面をカバーするプロンプトを追加します。

中程度の優先度として「サプライチェーン統合」と「到達可能性検証」があります。
cargo audit等のツールをパイプラインに組み込み、外部ライブラリの脆弱性も自動検出できるようにします。
-->
