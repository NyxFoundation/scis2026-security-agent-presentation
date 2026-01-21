---
layout: default
---

# 高信頼ソフトウェアでは仕様と実装の整合性確認が不可欠

<div class="text-center text-sm text-gray-600 mt-2">
航空管制 / 医療機器 / 金融システム / インターネット / ブロックチェーン など
</div>

<div class="grid grid-cols-5 gap-4 mt-4 items-center">

<div class="col-span-2 p-4 border-2 border-black rounded-lg">

<div class="text-center text-lg font-bold mb-3">自然言語仕様</div>

```
A sender MUST NOT send a
Content-Length header field in
any message that contains a
Transfer-Encoding header field.
```

<div class="mt-3 text-sm text-center">
RFC 7230 (HTTP/1.1) Section 3.3.2
</div>

</div>

<div class="col-span-1 text-center text-4xl">

→ **?** ←

<div class="text-sm mt-2">整合性</div>

</div>

<div class="col-span-2 p-4 border-2 border-black rounded-lg">

<div class="text-center text-lg font-bold mb-3">実装コード</div>

```python
if length:
    self.headers["Content-Length"] = \
        builtin_str(length)
else:
    self.headers["Transfer-Encoding"] = \
        "chunked"
```

<div class="mt-3 text-sm text-center">
requests/models.py
</div>

</div>

</div>

<div class="mt-8 text-center">

<span class="text-red-600 font-bold">現状: 整合性確認は人手に依存</span> (時間がかかり、見落としが発生...)

</div>

<div class="absolute bottom-4 left-4 text-xs text-gray-400">
RFC 7230 Section 3.3.2, https://datatracker.ietf.org/doc/html/rfc7230#section-3.3.2<br>
requests/models.py, https://github.com/psf/requests/blob/main/src/requests/models.py
</div>

<!--
航空管制、医療機器、金融システム、インターネット、そしてブロックチェーンなど、高信頼性が求められるソフトウェアでは、仕様と実装の整合性確認が極めて重要です。

ここでは実際のRFC 7230、つまりHTTP/1.1の仕様とPythonのrequestsライブラリのコードを例示しています。

これらのシステムでは、RFCや技術仕様書といった自然言語で記述された仕様があり、「MUST（必須）」「SHOULD（推奨）」といった規範語で要件が定義されています。

しかし、これらの仕様を実装に正しく反映できているかを確認する作業は、現在も多くが人手に依存しており、時間がかかり、エラーが入りやすいという問題があります。

特に、複数のチームが同じ仕様を独立に実装する環境では、さらに複雑な問題が生じます。
-->
