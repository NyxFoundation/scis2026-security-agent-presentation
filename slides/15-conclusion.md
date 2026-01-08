---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# まとめ

<div class="mt-2 space-y-2">

<div class="p-2 bg-blue-50 rounded-lg border-l-4 border-blue-500">
  <div class="flex items-center gap-3">
    <div class="text-2xl font-bold text-blue-600">1</div>
    <div>
      <div class="font-bold text-blue-800 text-sm">AIによる監査自動化は有効である</div>
      <div class="text-xs text-gray-600">
        54件報告し<strong>17件</strong>が有効。特に<strong>類似バグ探索</strong>が効果的（<strong>76.5%</strong>）
      </div>
    </div>
  </div>
</div>

<div class="p-2 bg-green-50 rounded-lg border-l-4 border-green-500">
  <div class="flex items-center gap-3">
    <div class="text-2xl font-bold text-green-600">2</div>
    <div>
      <div class="font-bold text-green-800 text-sm">「監査の民主化」を実証</div>
      <div class="text-xs text-gray-600">
        非専門家(D氏)が専門家(B氏)を上回る<strong>8件</strong>を発見。<strong>適切なコンテキスト</strong>があれば専門知識不要
      </div>
    </div>
  </div>
</div>

<div class="p-2 bg-orange-50 rounded-lg border-l-4 border-orange-500">
  <div class="flex items-center gap-3">
    <div class="text-2xl font-bold text-orange-600">3</div>
    <div>
      <div class="font-bold text-orange-800 text-sm">課題を特定し、改善策を実装・検証</div>
      <div class="text-xs text-gray-600">
        High/Medium 0件発見の課題 → <strong>Program Graph</strong>と<strong>Trust Model</strong>で網羅性を改善
      </div>
    </div>
  </div>
</div>

</div>

<div class="mt-2 p-2 text-black border-black border rounded-lg text-center">
  <div class="font-bold mb-1">"AI監査の現在地"</div>
  <div class="text-xs">
    AI監査は<strong>『過去の類似バグ』</strong>と<strong>『明確な仕様違反』</strong>には極めて強いが、<br>
    <strong>未知の攻撃手法</strong>の発見には、まだ人間の直感と深い洞察が必要である
  </div>
</div>

<div class="mt-2 grid grid-cols-3 gap-2 text-[10px]">
  <div class="bg-blue-100 p-2 rounded text-center">
    <div class="font-bold text-blue-700">Fusakaコンテスト</div>
    <div>17件発見 / 有効率31.5%</div>
  </div>
  <div class="bg-green-100 p-2 rounded text-center">
    <div class="font-bold text-green-700">改善版 (Gethデモ)</div>
    <div>235チェック自動生成</div>
  </div>
  <div class="bg-purple-100 p-2 rounded text-center">
    <div class="font-bold text-purple-700">研究サイクル</div>
    <div>課題→改善→検証を完遂</div>
  </div>
</div>

<!--
まとめです。

第一に、AIによる監査自動化は有効です。
54件報告し17件が有効となりました。特に類似バグ探索が効果的で、発見された脆弱性の76.5%を占めました。

第二に、「監査の民主化」を実証しました。
非専門家のD氏が専門家のB氏を上回る8件を発見し、適切なコンテキストがあれば専門知識がなくても脆弱性発見が可能であることを示しました。

第三に、課題を特定し、改善策を実装・検証しました。
High/Medium脆弱性0件発見という課題を受け、Program GraphベースのアーキテクチャとTrust Modelを実装し、Geth監査デモで235チェックを自動生成しました。

結論として、AI監査は既知のパターンには強いものの、未知の攻撃手法の発見には、まだ人間の洞察力が必要です。
本研究は、課題発見から改善、検証のサイクルを1回転させた継続的な研究です。
-->
