---
layout: default
---

# 高信頼ソフトウェアでは仕様と実装の整合性確認が不可欠

<div class="grid grid-cols-5 gap-4 mt-8 items-center">

<div class="col-span-2 p-4 border-2 border-black rounded-lg">

<div class="text-center text-lg font-bold mb-3">自然言語仕様</div>

```
The validator MUST verify
that the blob count does not
exceed MAX_BLOBS_PER_BLOCK.
```

<div class="mt-3 text-sm text-center">
RFC / EIP / 技術設計書
</div>

</div>

<div class="col-span-1 text-center text-4xl">

→ **?** ←

<div class="text-sm mt-2">整合性</div>

</div>

<div class="col-span-2 p-4 border-2 border-black rounded-lg">

<div class="text-center text-lg font-bold mb-3">実装コード</div>

```go
if len(blobs) > MAX_BLOBS {
    return error
}
```

<div class="mt-3 text-sm text-center">
Go / Rust / Java / ...
</div>

</div>

</div>

<div class="mt-8 text-center">

<span class="text-red-600 font-bold">現状: 整合性確認は人手に依存</span> (時間がかかり、見落としが発生...)

</div>

<div class="absolute bottom-4 left-4 text-xs text-gray-400">
[6] Liu et al., AUTOSPEC, arXiv:2511.17977, 2025 / RFC 2119
</div>

<!--
航空管制、医療機器、金融システム、そしてブロックチェーンなど、高信頼性が求められるソフトウェアでは、仕様と実装の整合性確認が極めて重要です。

これらのシステムでは、RFCや技術仕様書といった自然言語で記述された仕様があり、「MUST（必須）」「SHOULD（推奨）」といった規範語で要件が定義されています。

しかし、これらの仕様を実装に正しく反映できているかを確認する作業は、現在も多くが人手に依存しており、時間がかかり、エラーが入りやすいという問題があります。

特に、複数のチームが同じ仕様を独立に実装する環境では、さらに複雑な問題が生じます。
-->
