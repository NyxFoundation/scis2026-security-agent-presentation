---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# イーサリアムの心臓部を守る「クライアント」とは？

<div class="p-2 bg-primary-bg rounded-lg text-sm mb-3">
  <strong>クライアント</strong> = イーサリアムネットワークに参加するための<strong>ソフトウェア</strong>
</div>

<!-- クライアント一覧 -->
<div class="grid grid-cols-2 gap-4 mb-3">
  <div class="p-2 bg-primary-bg rounded-lg">
    <div class="text-xs font-bold text-primary-dark mb-2 text-center">実行層 (EL) クライアント</div>
    <div class="flex justify-center items-center gap-3">
      <div class="flex flex-col items-center">
        <img src="/images/eth_geth.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Geth</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_reth.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Reth</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_besu.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Besu</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_erigon.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Erigon</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_nethermind.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Nethermind</span>
      </div>
    </div>
  </div>

  <div class="p-2 bg-secondary-bg rounded-lg">
    <div class="text-xs font-bold text-secondary-dark mb-2 text-center">合意層 (CL) クライアント</div>
    <div class="flex justify-center items-center gap-2">
      <div class="flex flex-col items-center">
        <img src="/images/eth_lighthouse.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Lighthouse</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_prysm.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Prysm</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_teku.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Teku</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_nimbus.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Nimbus</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_lodestar.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Lodestar</span>
      </div>
      <div class="flex flex-col items-center">
        <img src="/images/eth_grandine.png" class="h-7 w-7 object-contain" />
        <span class="text-[9px] text-gray-600">Grandine</span>
      </div>
    </div>
  </div>
</div>

<div class="text-center text-xs text-gray-500 mb-3">
  ノード運用者は EL × CL の組み合わせを自由に選択可能 → 計11種類のクライアントが稼働
</div>

<!-- 強みと課題 -->
<div class="grid grid-cols-2 gap-4 mb-3">
  <div class="flex items-center gap-2 p-2 bg-success-bg rounded-lg border border-success-light">
    <div class="text-xl text-success">✓</div>
    <div>
      <div class="font-bold text-success-dark text-xs">耐障害性（強み）</div>
      <div class="text-[10px] text-gray-600">1つにバグがあっても他は影響を受けない</div>
    </div>
  </div>
  <div class="flex items-center gap-2 p-2 bg-tertiary-bg rounded-lg border border-tertiary-light">
    <div class="text-xl text-tertiary">✗</div>
    <div>
      <div class="font-bold text-tertiary-dark text-xs">検証コスト（課題）</div>
      <div class="text-[10px] text-gray-600"><strong>全実装</strong>を検証しないと安全性を保証できない</div>
    </div>
  </div>
</div>

<!-- 結論 -->
<div class="p-2 bg-gray-100 rounded-lg text-center">
  <div class="text-sm font-bold text-gray-700">
    11種類もの異なるクライアントを、どのように効率的に検証するか？
  </div>
</div>

<div class="absolute bottom-2 left-2 text-[8px] text-gray-400 max-w-[90%] leading-relaxed text-left">
  <div><strong class="text-gray-500">[クライアント多様性]</strong> https://ethereum.org/ja/developers/docs/nodes-and-clients/client-diversity/</div>
</div>

<!--
イーサリアムには「クライアント多様性」という特徴があります。

クライアントとは、イーサリアムネットワークに参加するためのソフトウェアです。
PCで言えばOSのようなもの、インターネットで言えばWebブラウザのような役割です。

ノード運用者は、実行層と合意層のソフトウェアを自由に組み合わせて選ぶことができます。
例えば、実行層はGeth、合意層はLighthouseという組み合わせも可能です。

これには耐障害性というメリットがあります。
1つのソフトウェアにバグがあっても、他のソフトを使っているノードは影響を受けません。

一方で、全ての実装を検証しなければならないという課題もあります。
11種類もの異なるクライアントを、どのように効率的に検証するかが本研究の動機です。
-->
