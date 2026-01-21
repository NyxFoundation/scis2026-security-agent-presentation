---
layout: default
---

# 本手法の立ち位置

<div class="flex justify-center mt-4">

<!-- 4象限チャート -->
<div class="relative border-2 border-gray-300 rounded bg-gray-50" style="width: 600px; height: 320px;">
<!-- 軸ラベル -->
<div class="absolute top-2 left-1/2 -translate-x-1/2 text-sm text-gray-600 font-bold">仕様起点</div>
<div class="absolute bottom-2 left-1/2 -translate-x-1/2 text-sm text-gray-600 font-bold">コード起点</div>
<div class="absolute left-3 top-1/2 -translate-y-1/2 text-sm text-gray-600 font-bold">単一実装</div>
<div class="absolute right-3 top-1/2 -translate-y-1/2 text-sm text-gray-600 font-bold">多実装</div>
<!-- 軸線 -->
<div class="absolute left-1/2 top-8 bottom-8 w-px bg-gray-300"></div>
<div class="absolute top-1/2 left-16 right-16 h-px bg-gray-300"></div>
<!-- RFCAudit -->
<div class="absolute text-center" style="left: 18%; top: 22%;">
<div class="bg-gray-500 text-white px-2 py-1 rounded text-sm">RFCAudit</div>
<div class="text-xs text-gray-600 mt-1">単一実装のみ</div>
</div>
<!-- RepoAudit -->
<div class="absolute text-center" style="left: 18%; bottom: 22%;">
<div class="bg-gray-500 text-white px-2 py-1 rounded text-sm">RepoAudit</div>
<div class="text-xs text-gray-600 mt-1">検証器重視</div>
</div>
<!-- Fluffy/LOKI -->
<div class="absolute text-center" style="right: 18%; bottom: 22%;">
<div class="bg-gray-500 text-white px-2 py-1 rounded text-sm">Fluffy/LOKI</div>
<div class="text-xs text-gray-600 mt-1">差分依存</div>
</div>
<!-- 本手法 + 吹き出し -->
<div class="absolute" style="right: 22%; top: 15%;">
<div class="bg-blue-600 text-white px-3 py-2 rounded text-sm font-bold shadow-lg">本手法</div>
<!-- 吹き出し（右に配置） -->
<div class="absolute bg-blue-100 border-2 border-blue-400 rounded-lg p-2 text-xs" style="left: 110%; top: -10px; width: 130px;">
<div class="font-bold text-blue-800 mb-1">独自性</div>
<div>• 仕様起点 + 多実装</div>
<div>• 脅威モデル形式化</div>
<!-- 吹き出しの矢印（左向き） -->
<div class="absolute top-3 -left-2 w-0 h-0 border-t-6 border-b-6 border-r-8 border-transparent border-r-blue-400"></div>
</div>
</div>
</div>

</div>

<div class="absolute bottom-4 left-4 text-xs text-gray-400">
Zheng et al., RFCAudit, arXiv 2025, https://arxiv.org/abs/2506.00714<br>
Guo et al., RepoAudit, ICML 2025, https://openreview.net/forum?id=TXcifVbFpG<br>
Yang et al., Fluffy, OSDI 2021, https://www.usenix.org/conference/osdi21/presentation/yang<br>
Ma et al., LOKI, NDSS 2023, https://www.ndss-symposium.org/ndss-paper/loki-state-aware-fuzzing-framework-for-the-implementation-of-blockchain-consensus-protocols/
</div>

<!--
ここで、関連研究との比較を行います。

RFCAuditは仕様起点ですが単一実装を対象としています。RepoAuditはコード起点で検証器による誤検知削減を重視します。FluffyやLOKIは多実装の差分を利用しますが、仕様への言及はありません。

本手法は、仕様起点で多実装に対応し、かつ脅威モデルを明示的に形式化する点で差別化されます。

特に、今回の実験で誤検知の最大原因が脅威モデル不整合であることがわかったため、前提条件を工程として固定することを重視しています。

最後にまとめます。
-->
