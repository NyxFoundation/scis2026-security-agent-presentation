---
layout: default
---

# 3つの戦略

<div class="mt-6">

| 戦略 | 説明 | 特徴 |
|------|------|------|
| **A: 静的監査** | 単一実装を仕様と直接照合 | 基本チェック |
| **B: 横展開** | 発見を他実装に展開 | **スケール効果大** |
| **C: 動的テスト** | テストケース生成・実行 | 実行時検証 |

</div>

<div class="flex items-center justify-center gap-3 mt-4 text-sm">

<div class="px-3 py-2 bg-red-100 border-2 border-red-400 rounded text-center">
<div class="font-bold">クライアントAで発見</div>
<div>範囲チェック欠落</div>
</div>

<span class="text-xl">→</span>

<div class="px-3 py-2 bg-yellow-100 border-2 border-yellow-400 rounded font-bold">パターン抽象化</div>

<span class="text-xl">→</span>

<div class="flex flex-col gap-1">
<div class="flex items-center gap-2">
<span class="px-2 py-1 bg-gray-100 border rounded">クライアントB</span>
<span class="text-green-600">✓ 同様の欠落発見</span>
</div>
<div class="flex items-center gap-2">
<span class="px-2 py-1 bg-gray-100 border rounded">クライアントC</span>
<span class="text-green-600">✓ 同様の欠落発見</span>
</div>
<div class="flex items-center gap-2">
<span class="px-2 py-1 bg-gray-100 border rounded">クライアントD</span>
<span class="text-gray-400">検証中...</span>
</div>
</div>

</div>

<div class="mt-3 text-center text-lg">

仕様の曖昧な部分で**複数チームが同じ誤解**をしている → 横展開が有効

</div>

<!--
3つの戦略のうち、特に重要なのが戦略B、横展開チェックです。

これは、ある実装で発見したバグパターンを抽象化し、同じチェックリスト項目を他のすべての実装に対して検証する戦略です。

例えば、クライアントAで「範囲チェックの欠落」を発見した場合、同じチェック項目をクライアントB、C、Dにも適用します。

多実装環境では、仕様の曖昧な部分で複数チームが同じ誤解をしている可能性が高いため、この横展開が非常に効果的です。

戦略Aは単一実装を仕様に照らして直接チェックし、戦略Cは動的テストを生成します。
-->
