---
layout: default
---

# 多実装環境では「全員が同じ誤解をする」問題が発生する

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

```mermaid {scale: 0.6}
graph TD
    SPEC[仕様文書] --> A[チームA]
    SPEC --> B[チームB]
    SPEC --> C[チームC]
    A --> ERR[同じ誤解]
    B --> ERR
    C --> ERR
```

</div>

<div class="flex flex-col justify-center">

<div class="p-4 bg-gray-100">

> 「独立実装でも共通障害は偶然より有意に多く発生する」

<div class="text-right text-sm">— Knight & Leveson (1986)</div>

</div>

<div class="mt-4">

Nバージョンプログラミングの仮定<br/>
「独立開発なら障害も独立」は**成立しない**

</div>

</div>

</div>

<div class="absolute bottom-4 left-4 text-xs text-gray-400">
[4] Knight & Leveson, IEEE TSE, 1986
</div>

<!--
多実装環境、つまり同じ仕様を複数のチームが独立に実装する環境では、興味深い問題が生じます。

1986年のKnightとLevesonの有名な研究で示されたように、独立に開発された実装であっても、仕様の曖昧な部分について同じ誤解をする「共通モード障害」が偶然より高い頻度で発生します。

これは、仕様文書の曖昧さや、暗黙の前提が原因です。Nバージョンプログラミングでは「独立開発なら障害も独立」と仮定しますが、実際にはそうならないことが実証されています。
-->
