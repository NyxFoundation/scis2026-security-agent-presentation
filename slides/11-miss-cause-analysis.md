---
layout: default
---

# 見逃しの原因分析

<div class="grid grid-cols-2 gap-6 mt-6 items-center">

<div>

```mermaid
%%{init: {"themeVariables": {"xyChart": {"plotColorPalette": "#6366f1, #8b5cf6, #a78bfa, #c4b5fd"}}}}%%
xychart-beta vertical
    title "見逃し原因（計7件）"
    x-axis ["複雑な状態遷移", "動的境界条件", "外部依存", "仕様ニュアンス"]
    y-axis "件数" 0 --> 4
    bar [3, 2, 1, 1]
```

</div>

<div>

<div class="p-3 bg-red-100 border-l-4 border-red-500">
<span class="text-red-700 font-bold">高重大度 0/5、中重大度 0/2</span>
<div class="text-sm text-gray-600 mt-1">→ 重大な脆弱性は全て見逃し</div>
</div>

<div class="mt-4 text-sm">

| 見逃し原因 | 例 |
|------------|-----|
| 複雑な状態遷移 | フォーク境界での長い状態変化 |
| 動的境界条件 | 実行時に決まるガード条件 |

</div>

</div>

</div>

<div class="mt-4 text-center">

チェックリスト充実で改善可能

</div>

<!--
V1では、高重大度5件、中重大度2件、計7件の重大な脆弱性をすべて見逃しました。

見逃しの原因を分析すると、最も多いのが「複雑な状態遷移」で3件、次いで「動的境界条件」が2件、「外部依存」と「仕様ニュアンス」が各1件でした。

複雑な状態遷移とは、例えばフォーク境界での長い状態変化のように、複数のステップにまたがる状態変化のことです。動的境界条件とは、実行時に決まるガード条件のことです。

重要なのは、これらは本手法の根本的な限界ではなく、チェックリストを充実させることで改善可能な課題であるという点です。
-->
