---
theme: seriph
title: イーサリアム開発の最前線
info: |
  ## イーサリアム開発の最前線
  技術課題・研究動向・将来展望

  Nyx Foundation登壇資料
  gohan
layout: cover
transition: slide-left
mdc: true
---

# イーサリアム開発の最前線
### gohan

---
layout: two-cols
layoutClass: gap-16
---

# 自己紹介

::left::

<div class="flex flex-col items-center">
  <div class="w-64 h-64 bg-gray-200 rounded-lg flex items-center justify-center mb-4">
    <span class="text-gray-400">Profile Image</span>
  </div>
  <h3 class="text-xl font-bold">gohan</h3>
  <p class="text-sm mt-2">Nyx Foundation所属</p>
  <p class="text-sm">ZK Tokyo運営</p>
  <p class="text-sm">早稲田大学暗号学修士</p>
  <p class="text-sm">イーサリアム財団奨学生</p>
</div>

::right::

<div class="mt-4">
  <h4 class="text-lg font-bold mb-4">これまでやったこと</h4>
  
  <ul class="text-sm space-y-2 mb-6">
    <li>✓ イーサリアムへ複数バグ報告</li>
    <li>✓ イーサリアムFusaka監査コンテストで15件のバグ報告</li>
    <li>✓ イーサリアムクライアントGeth, Enigonの実装改善に貢献</li>
    <li>✓ zkVMベンチマークの研究（国際学会採択）</li>
    <li>✓ MPCで数理最適化を解くシステムの研究（EFと共同）</li>
  </ul>

  <div class="flex gap-4 justify-center mt-8">
    <div class="w-24 h-16 bg-orange-100 rounded flex items-center justify-center">
      <span class="text-xs text-center">AWS</span>
    </div>
    <div class="w-24 h-16 bg-purple-100 rounded flex items-center justify-center">
      <span class="text-xs text-center">Ethereum</span>
    </div>
  </div>
</div>

---

# 本勉強会の目的

## 3つの地図を完全理解する！！！

<div class="mt-12 grid grid-cols-3 gap-6">
  <div class="bg-orange-100 rounded-lg p-6 border-2 border-orange-300 flex flex-col items-center justify-center h-48">
    <div class="text-4xl mb-4">🧭</div>
    <h3 class="font-bold text-center">ロードマップの方向性</h3>
    <p class="text-xs mt-2 text-center">シンプル・柔軟性・分散性を保ったまま速く</p>
  </div>
  
  <div class="bg-orange-200 rounded-lg p-6 border-2 border-orange-400 flex flex-col items-center justify-center h-48">
    <div class="text-4xl mb-4">📅</div>
    <h3 class="font-bold text-center">直近アップグレード</h3>
    <p class="text-xs mt-2 text-center">Fusaka/Glamsterdam</p>
  </div>
  
  <div class="bg-orange-300 rounded-lg p-6 border-2 border-orange-500 flex flex-col items-center justify-center h-48">
    <div class="text-4xl mb-4">🔗</div>
    <h3 class="font-bold text-center">エコシステム</h3>
    <p class="text-xs mt-2 text-center">zkHyperliquid Bitcoin DeFi Privacy etc.</p>
  </div>
</div>

---

# イーサリアムについておさらい

イーサリアムは信頼機関なしで動くプログラムを実行できる「分散型アプリ基盤」

<div class="grid grid-cols-2 gap-8 mt-6">
  <div>
    <div class="mb-6">
      <h4 class="font-bold mb-3 text-sm">誰が正しいか多数決で決める</h4>
      <div class="bg-gray-100 p-4 rounded-lg flex items-center justify-center gap-3">
        <div class="w-6 h-6 bg-blue-500 rounded-full"></div>
        <div class="w-6 h-6 bg-blue-500 rounded-full"></div>
        <div class="w-6 h-6 bg-blue-500 rounded-full"></div>
        <span class="text-lg">→</span>
        <div class="w-12 h-8 bg-blue-300 rounded flex items-center justify-center text-xs font-bold">多数決</div>
      </div>
    </div>

    <div class="mb-6">
      <h4 class="font-bold mb-3 text-sm">いつ会計が締められるかが明確</h4>
      <div class="bg-gray-100 p-4 rounded-lg text-xs space-y-2">
        <div class="flex justify-between font-bold">
          <span>ブロック提案</span>
          <span>検証</span>
          <span>正当化</span>
          <span>確定</span>
        </div>
        <div class="flex justify-between text-gray-600">
          <span></span>
          <span>12s</span>
          <span></span>
          <span>6min</span>
        </div>
      </div>
    </div>

    <div>
      <h4 class="font-bold mb-3 text-sm">L2でスケール、L1で信頼を担保</h4>
      <div class="bg-gray-100 p-4 rounded-lg text-xs flex items-center justify-center gap-2">
        <span class="bg-pink-200 px-2 py-1 rounded">複数ノード</span>
        <span>→</span>
        <span class="bg-blue-200 px-2 py-1 rounded">L2</span>
        <span>→</span>
        <span class="bg-orange-200 px-2 py-1 rounded">L1</span>
      </div>
    </div>
  </div>

  <div>
    <h4 class="font-bold mb-3 text-sm">ブロックチェーン構造</h4>
    <div class="bg-gray-100 p-6 rounded-lg">
      <div class="flex items-center justify-center gap-2 mb-4">
        <div class="w-10 h-10 bg-blue-400 rounded flex items-center justify-center text-white text-xs font-bold">N</div>
        <span class="text-lg">→</span>
        <div class="w-10 h-10 bg-blue-400 rounded flex items-center justify-center text-white text-xs font-bold">N</div>
        <span class="text-lg">→</span>
        <div class="w-10 h-10 bg-blue-400 rounded flex items-center justify-center text-white text-xs font-bold">N</div>
      </div>
      <div class="flex items-center justify-center gap-2">
        <div class="w-10 h-10 bg-blue-400 rounded flex items-center justify-center text-white text-xs font-bold">N</div>
        <span class="text-lg">→</span>
        <div class="w-10 h-10 bg-blue-400 rounded flex items-center justify-center text-white text-xs font-bold">N</div>
      </div>
    </div>
  </div>
</div>

---

# イーサリアムロードマップ

シンプルに・柔軟に・分散したまま速く

```mermaid
graph LR
    A["Peer-DAS<br/>ePBS<br/>BALs"] --> B["DAS"]
    B --> C["Based<br/>Rollup"]
    C --> D["Kohaku<br/>Wallet"]
    D --> E["Account<br/>Abstraction"]
    
    B --> F["Danksharding"]
    C --> G["Stateless"]
    D --> H["Native<br/>Rollup"]
    E --> I["RISC-V"]
    E --> J["3SF APS"]
    
    style A fill:#C8E6C9
    style B fill:#C8E6C9
    style F fill:#C8E6C9
    
    style C fill:#FFE0B2
    style G fill:#FFE0B2
    style H fill:#FFE0B2
    
    style D fill:#FFE0B2
    
    style E fill:#F8BBD0
    style I fill:#F8BBD0
    style J fill:#F8BBD0
```

---

# まとめ

<div class="grid grid-cols-3 gap-6 mt-12">
  <div class="bg-blue-50 p-6 rounded-lg border-l-4 border-blue-400">
    <h3 class="font-bold mb-2">🧭 ロードマップ</h3>
    <p class="text-sm">シンプル・柔軟性・分散性を保ったまま速く</p>
  </div>
  
  <div class="bg-blue-50 p-6 rounded-lg border-l-4 border-blue-400">
    <h3 class="font-bold mb-2">📅 アップグレード</h3>
    <p class="text-sm">直近のFusaka/Glamsterdamに注目</p>
  </div>
  
  <div class="bg-blue-50 p-6 rounded-lg border-l-4 border-blue-400">
    <h3 class="font-bold mb-2">🔗 エコシステム</h3>
    <p class="text-sm">多様なアプリケーションの発展</p>
  </div>
</div>

<div class="mt-16 text-center">
  <h2 class="text-3xl font-bold">ご質問ありがとうございました</h2>
</div>

---
layout: cover
---

# Thank you!