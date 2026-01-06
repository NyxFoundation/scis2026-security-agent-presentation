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
## 技術課題・研究動向・将来展望

gohan

---
layout: two-cols
layoutClass: gap-8
---

# 自己紹介

**gohan**

- Nyx Foundation所属
- ZK Tokyo運営
- 早稲田大学暗号学修士
- イーサリアム財団奨学生

::right::

<div class="mt-8">

**これまでやったこと**

- イーサリアムへ複数バグ報告
- Fusaka監査コンテストで15件のバグ報告
- Geth, Erigonの実装改善に貢献
- zkVMベンチマークの研究（国際学会採択）
- MPCで数理最適化を解くシステムの研究

</div>

---

# 本勉強会の目的

<div class="text-center text-xl font-bold mt-2 mb-6">
3つの地図を完全理解する！！！
</div>

<div class="grid grid-cols-3 gap-4">
<div class="border-2 border-amber-400 rounded-lg p-3 bg-amber-50 text-center">
<div class="text-2xl mb-1">🧭</div>
<div class="font-bold text-sm">ロードマップの方向性</div>
<div class="text-xs mt-1 opacity-80">シンプル・柔軟性・分散性を保ったまま速く</div>
</div>

<div class="border-2 border-orange-400 rounded-lg p-3 bg-orange-50 text-center">
<div class="text-2xl mb-1">📅</div>
<div class="font-bold text-sm">直近アップグレード</div>
<div class="text-xs mt-1 opacity-80">Fusaka / Glamsterdam</div>
</div>

<div class="border-2 border-red-400 rounded-lg p-3 bg-red-50 text-center">
<div class="text-2xl mb-1">🔗</div>
<div class="font-bold text-sm">エコシステム</div>
<div class="text-xs mt-1 opacity-80">zkHyperliquid / Bitcoin DeFi / Privacy</div>
</div>
</div>

---

# イーサリアムについておさらい

イーサリアムは信頼機関なしで動くプログラムを実行できる**「分散型アプリ基盤」**

<div class="grid grid-cols-2 gap-4 mt-2">
<div>

```mermaid {scale: 0.55}
flowchart LR
    V1((V1)) & V2((V2)) & V3((V3)) --> C[多数決]
    C --> B[確定]
```

```mermaid {scale: 0.5}
flowchart LR
    A[提案] --> B[検証]
    B -->|12s| C[正当化]
    C -->|6min| D[確定]
    style D fill:#90EE90
```

</div>
<div>

```mermaid {scale: 0.55}
flowchart LR
    U[Users] --> L2[L2]
    L2 -->|proof| L1[L1]
    style L1 fill:#FFB6C1
    style L2 fill:#87CEEB
```

**ポイント**
- 誰が正しいか多数決で決める
- いつ会計が締められるかが明確
- L2でスケール、L1で信頼を担保

</div>
</div>

---

# イーサリアムロードマップ

<span class="text-green-600 font-bold">シンプルに</span>・<span class="text-amber-600 font-bold">柔軟に</span>・<span class="text-red-600 font-bold">分散したまま速く</span>

```mermaid {scale: 0.6}
flowchart LR
    A["Peer-DAS/ePBS/BALs"] --> B[DAS] --> C[Based Rollup] --> D[Kohaku] --> E[AA]
    B -.-> F[Danksharding]
    C -.-> G[Stateless]
    D -.-> H[Native Rollup]
    E -.-> I["RISC-V/3SF"]

    style A fill:#C8E6C9
    style B fill:#C8E6C9
    style F fill:#C8E6C9
    style C fill:#FFE0B2
    style D fill:#FFE0B2
    style G fill:#FFE0B2
    style H fill:#FFE0B2
    style E fill:#FFCDD2
    style I fill:#FFCDD2
```

---

# ①シンプルに

<div class="grid grid-cols-2 gap-4 mt-2">

<div class="border rounded p-3 bg-blue-50">
<div class="font-bold mb-1">RISC-V</div>
<div class="text-sm">Solidity → Rust, Go（高速化&拡張性）</div>
</div>

<div class="border rounded p-3 bg-blue-50">
<div class="font-bold mb-1">leanConsensus (zkVM統合)</div>
<div class="text-sm">固有アルゴリズム → ZK検証</div>
</div>

<div class="border rounded p-3 bg-blue-50">
<div class="font-bold mb-1">Account Abstraction (EOA廃止)</div>
<div class="text-sm">EOA & CA → CA only</div>
</div>

<div class="border rounded p-3 bg-blue-50">
<div class="font-bold mb-1">Stateless</div>
<div class="text-sm">フルノード → 軽量ノード</div>
</div>

</div>

```mermaid {scale: 0.5}
flowchart LR
    A1[複雑] --> B1[シンプル]
    style B1 fill:#90EE90
```

---

# ウォレット耐量子移行のカギはAccount Abstraction

```mermaid {scale: 0.65}
flowchart TB
    User((User))
    EOA[EOA]
    CA[CA]

    User --> EOA
    EOA -->|"①資産を移動"| CA
    User -.->|"②アクセス禁止 ❌"| EOA
    User -->|"③復元 ✅"| CA

    style EOA fill:#FFCDD2
    style CA fill:#C8E6C9
```

<div class="p-3 bg-pink-50 rounded border-l-4 border-pink-400 text-sm">
<div class="font-bold">イーサリアムがビットコインを救う？？？</div>
<div class="mt-1">zkVMを用いたビットコインの耐量子移行実現に取り組むエンジニアも</div>
</div>

---

# ②柔軟に

| レイヤー | 技術 | 効果 |
|---|---|---|
| **L1** | ePBS | ビルダーとの通信が柔軟に |
| **L1** | leanConsensus | コンセンサスが柔軟に |
| **L2** | Based Rollup | ロールアップが柔軟に |
| **L2** | Native Rollup | シーケンサーロジックの強制化 |
| **User** | Kohaku Wallet | ウォレットが柔軟に |

---

# ③分散性を保ったまま速く

<div class="grid grid-cols-2 gap-8 mt-4">

<div class="text-center">
<div class="text-sm text-gray-500">Block Latency</div>
<div class="text-4xl font-bold">
<span class="text-gray-400">12s</span> → <span class="text-orange-500">4s</span>
</div>
<div class="mt-4 text-left text-sm">

- **Block-level Access Lists**: 並列処理
- **Data Availability Sampling**: Blob数増加

</div>
</div>

<div class="text-center">
<div class="text-sm text-gray-500">Finality</div>
<div class="text-4xl font-bold">
<span class="text-gray-400">6min</span> → <span class="text-orange-500">12s</span>
</div>
<div class="mt-4 text-left text-sm">

- **3 Slot Finality (3SF)**

$T_{finality} = 3 \times 4s = 12s$

</div>
</div>

</div>

---

# 直近のアップグレード

| | 主要技術 | ユーザー影響 | ノード運用者影響 |
|---|---|---|---|
| **Fusaka** | PeerDAS | <span class="text-green-600">L2 TPS↑</span> | <span class="text-red-500">負荷↑</span> |
| **Glamsterdam** | ePBS/BALs/FOCIL | <span class="text-green-600">L1 TPS↑</span> <span class="text-green-600">検閲耐性↑</span> | <span class="text-red-500">帯域要求↑</span> <span class="text-green-600">収益安定↑</span> |

<div class="mt-4 text-xs opacity-70">

参考: https://eips.ethereum.org/EIPS/eip-7607, https://eips.ethereum.org/EIPS/eip-7773

</div>

---

# 安全性を支える仕組み① 形式検証

<div class="grid grid-cols-2 gap-6">

<div class="bg-pink-50 p-3 rounded">
<div class="font-bold mb-2">形式検証とは？</div>
<div class="text-sm">プログラムの安全性を**数学的に証明**する技術</div>

$\forall x: P(x) \Rightarrow Q(f(x))$

<div class="text-xs mt-2">テストよりも網羅的に安全性を保障できる</div>
</div>

<div class="bg-amber-50 p-3 rounded">
<div class="font-bold mb-2">Nyx Foundationの貢献</div>
<div class="text-sm">
耐量子署名の一部を形式検証してケンブリッジ大学で開かれたEF合宿で発表
</div>
<div class="text-xs mt-2">AIエージェントでLean形式検証を自動化</div>
</div>

</div>

---

# 安全性を支える仕組み② 実装セキュリティ対策

<div class="grid grid-cols-2 gap-6">

<div>

```mermaid {scale: 0.6}
flowchart TB
    A[監査コンテスト] --> B[バグバウンティ]
    B --> C[監査]
    C --> D[メインネット]
    style D fill:#90EE90
```

</div>

<div>

**実装ガード**: 後方互換性、フェイルセーフ機構

**クライアント多様性**: 複数言語実装、単一障害点排除

<div class="p-2 bg-blue-50 rounded text-center mt-2">
<span class="text-xl font-bold text-blue-600">10年間</span> ゼロダウンタイム
</div>

<div class="p-2 bg-green-50 rounded mt-2 text-sm">
バグバウンティ: 2件 / 監査コンテスト: 15件
</div>

</div>
</div>

---

# よくある疑問: なぜL2ではなくL1？

<div class="text-center text-sm opacity-70 mb-2">
Tempo / Hyperliquid / Arc などがL1を選択
</div>

```mermaid {scale: 0.6}
flowchart LR
    P1["ロールアップが遅い"] --> S1["ZKの実用化"]
    P2["L1の確定が遅い"] --> S2["確定の高速化(3SF)"]

    style P1 fill:#FFCDD2
    style P2 fill:#FFCDD2
    style S1 fill:#C8E6C9
    style S2 fill:#C8E6C9
```

<div class="text-xs opacity-70">
参考: Ethproofs, 3SF論文
</div>

---

# イーサリアムユースケース

```mermaid {scale: 0.6}
mindmap
  root((Ethereum))
    zk-Hyperliquid
      HIBACHI
      Lighter
    Bitcoin DeFi
      Citrea
      BitVM
    Privacy
      ZKP2P
      RAILGUN
    AI
      MINA
      EZKL
    Bridge
      ACROSS
    予測市場
      Polymarket
```

---
layout: two-cols
layoutClass: gap-8
---

# Nyx Foundationの実践経験

- マイナンバーカードを使ったDID
- zkVM
- 無担保DeFiローン
- MPCを使った決済ネッティング
- DeFiソルバーアルゴリズム
- クロスチェーンブリッジ
- NFT / ステーブルコイン
- ノード運用
- +複数件のセキュリティ監査

::right::

<div class="mt-12">

<div class="p-4 bg-gray-100 rounded-xl text-center">
<div class="font-bold mb-2">お気軽にご相談ください</div>
<div class="text-blue-600 font-mono text-sm">contact@nyx.foundation</div>
</div>

</div>

---

# イーサリアム財団の動向

<div class="grid grid-cols-2 gap-4">

<div>

- **dAI Team**: AI関連の研究開発
- **ESP Grants**: 助成金プログラム刷新
- **Institutional Liquidity Layer**: 機関投資家向け
- **Ethereum Treasuries**: 企業のETH保有増加

</div>

<div class="flex items-center justify-center">

<div class="p-6 bg-amber-100 rounded-lg text-center">
<div class="text-2xl font-bold text-amber-700">チャンス！</div>
</div>

</div>
</div>

---

# イーサリアム上での資産運用

<div class="grid grid-cols-2 gap-6">

<div class="bg-purple-50 p-3 rounded">
<div class="font-bold mb-2">プロ参入で戦略も高度化</div>
<div class="text-sm">

- **DEX**: JIT流動性の活用
- **Lending**: キュレーター型ポートフォリオ管理

</div>
</div>

<div class="bg-blue-50 p-3 rounded">
<div class="font-bold mb-2">収益機会の変化</div>
<div class="text-sm">

- **BuilderNet**: ブロック構築の分散化
- **Prover Network**: ZK証明生成への参加

</div>
</div>

</div>

---

# イーサリアム・クライアント実装の違い（EL）

| | 言語 | ディスク | 特徴 |
|---|---|---|---|
| **Geth** | Go | 1.2TB | ロードマップ実装最速、API充実 |
| **Erigon** | Go | 1TB | 軽量、高速同期、CL不要 |
| **Nethermind** | .NET | 1.1TB | MEV/Flashbots標準搭載 |
| **Besu** | Java | 1.4TB | エンタープライズ特化 |
| **Reth** | Rust | 1.6TB | ExEx拡張、高速DB |

---

# イーサリアム・クライアント実装の違い（CL）

| | 言語 | メモリ | 特徴 |
|---|---|---|---|
| **Prysm** | Go | ～5GiB | MEV機能充実 |
| **Lighthouse** | Rust | ～5GiB | 保守性、多段防御 |
| **Nimbus** | Nim | ～3GiB | 低メモリ |
| **Lodestar** | JS | ～8GiB | 拡張性 |
| **Teku** | Java | ～10GiB | Besu相性良 |

---

# どのクライアントを選択すればいいの？

| ユースケース | EL | CL |
|---|---|---|
| RPCノード運用 | Geth | Nimbus |
| バリデータ運用 | Nethermind | Lighthouse / Prysm |
| 独自実装・拡張 | Reth / Erigon | Lodestar |
| 独自チェーン | Besu | Teku |

<div class="mt-4 text-xs opacity-70">

※十分なインターネット速度下であればパフォーマンス・APYに特に差はない
※RPCノード運用時はWAF設定等でセキュリティを徹底すること

</div>

---

# 今日のまとめ

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-amber-400 rounded-lg p-4 bg-amber-50 text-center">
<div class="text-2xl mb-1">🧭</div>
<div class="font-bold">ロードマップの方向性</div>
<div class="text-xs mt-2">シンプル・柔軟性・分散性を保ったまま速く</div>
</div>

<div class="border-2 border-orange-400 rounded-lg p-4 bg-orange-50 text-center">
<div class="text-2xl mb-1">📅</div>
<div class="font-bold">直近アップグレード</div>
<div class="text-xs mt-2">Fusaka / Glamsterdam</div>
</div>

<div class="border-2 border-red-400 rounded-lg p-4 bg-red-50 text-center">
<div class="text-2xl mb-1">🔗</div>
<div class="font-bold">エコシステム</div>
<div class="text-xs mt-2">zkHyperLiquid / Bitcoin DeFi / Privacy</div>
</div>

</div>

---
layout: cover
---

# Thank you!
