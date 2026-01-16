---
layout: default
---

# 予備1: 関連研究における本研究の位置づけ

<div class="mt-4 text-xs">

| 手法 | 対象 | 主要アプローチ | 本研究との差異 |
|------|------|--------------|--------------|
| Fluffy / LOKI / FORKY | 多実装 | 差分ファジング | 意味的盲点を検出不可 |
| RFCAudit | 単一実装 | 仕様→実装監査 | 横展開戦略なし |
| RepoAudit | 単一リポジトリ | 検証器中心の偽陽性削減 | 仕様起点ではない |
| **SpecAudit** | **多実装** | **仕様チェックリスト＋横展開** | **脅威モデル形式化で偽陽性対策** |

<div class="mt-4 flex justify-center">
  <div class="relative w-72 h-44 border rounded p-2 text-xs">
    <div class="absolute top-1 left-1/2 transform -translate-x-1/2 text-gray-500">多実装</div>
    <div class="absolute bottom-1 left-1/2 transform -translate-x-1/2 text-gray-500">単一実装</div>
    <div class="absolute left-1 top-1/2 transform -translate-y-1/2 text-gray-500">コード起点</div>
    <div class="absolute right-1 top-1/2 transform -translate-y-1/2 text-gray-500">仕様起点</div>

    <div class="absolute top-6 left-6 px-1 py-0.5 bg-slate-300 rounded text-xs border border-slate-400">Fluffy/LOKI</div>
    <div class="absolute bottom-10 left-8 px-1 py-0.5 bg-slate-300 rounded text-xs border border-slate-400">RepoAudit</div>
    <div class="absolute bottom-8 right-6 px-1 py-0.5 bg-slate-300 rounded text-xs border border-slate-400">RFCAudit</div>
    <div class="absolute top-8 right-8 px-2 py-1 bg-blue-500 text-white rounded font-bold">SpecAudit</div>
  </div>
</div>

</div>

<!--
関連研究との位置づけです。

差分ファジング系（Fluffy, LOKI, FORKY）は多実装を対象としますが、意味的盲点を検出できません。

RFCAuditは仕様起点ですが単一実装対象です。

本研究は仕様起点かつ多実装対象で、横断実装チェックという横展開戦略と、脅威モデル形式化による偽陽性対策を特徴とします。
-->
