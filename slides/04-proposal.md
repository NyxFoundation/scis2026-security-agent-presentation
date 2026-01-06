---
layout: default
---

# 提案手法: AI監査エージェント

### Phase 1: 準備

```mermaid {scale: 0.8}
flowchart LR
    A[仕様書/EIPs] --> B[仕様抽出] --> C[実装マッピング]
    C --> D[チェックリスト]
    C --> E[類似バグリスト]
    style D fill:#dbeafe
    style E fill:#dbeafe
```

<br>

### Phase 2: 監査

```mermaid {scale: 0.8}
flowchart LR
    D[チェックリスト] --> F[コード監査] --> I[検証/PoC]
    E[類似バグリスト] --> G[類似バグ探索] --> I
    H[動的テスト] --> J[レポート]
    I --> J
    style D fill:#dbeafe
    style E fill:#dbeafe
    style J fill:#fef9c3,stroke:#eab308
```

<!--
提案するAI監査エージェントの概要です。

Phase 1の準備フェーズでは、仕様書から要件を抽出し、実装マッピングを行って、チェックリストと類似バグリストを作成します。

Phase 2の監査フェーズでは、3つの戦略を並行実行します。
コード監査と類似バグ探索は検証・PoC作成を経て、動的テストは直接、最終レポートに統合されます。
-->
