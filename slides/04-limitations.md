---
layout: default
---

<div class="absolute top-4 right-4">
  <img src="/images/nyx_icon.svg" class="h-8 opacity-60" />
</div>

# 迫り来る脅威：人手では追いつかない検証の限界

<div class="grid grid-cols-2 gap-4">

<div class="p-4 border-2 border-gray-300 rounded-lg">
  <div class="font-bold mb-2 flex items-center gap-2">
    <span class="bg-blue-600 text-white px-2 py-0.5 rounded text-xs">背景</span>
    クライアント多様性とコンセンサス障害
  </div>
  <div class="text-sm space-y-3">
    <div>
      <div class="font-bold text-gray-700">Client Diversity (NxM)</div>
      <div class="text-xs text-gray-600">
        実行層(EL)と合意形成層(CL)の異質な組合せにより耐障害性を確保する戦略。
      </div>
    </div>
    <div>
      <div class="font-bold text-red-600">Consensus Failure Bugs (CFBs)</div>
      <div class="text-xs text-gray-600">
        実装間の微細な不一致が致命的な<strong>Chain Split</strong>を招く。
        <div class="mt-1 text-[10px] bg-red-50 p-1 rounded">
          例: SSZデシリアライズの解釈違い (Ghost Regions)
        </div>
      </div>
    </div>
  </div>
</div>

<div class="p-4 border-2 border-gray-300 rounded-lg">
  <div class="font-bold mb-2 flex items-center gap-2">
    <span class="bg-gray-600 text-white px-2 py-0.5 rounded text-xs">既存手法とその限界</span>
  </div>
  <div class="space-y-2">
    <div class="bg-gray-50 p-2 rounded text-xs">
      <div class="font-bold text-gray-700 mb-1">Specific Methods</div>
      <ul class="list-disc list-inside space-y-0.5 text-gray-600">
        <li><strong>Fluffy (OSDI'21):</strong> Multi-tx Differential Fuzzing</li>
        <li><strong>LOKI (NDSS'23):</strong> State-aware Fuzzing</li>
        <li><strong>Forky (ICSE'25):</strong> Intentional Chain Split Testing</li>
      </ul>
    </div>
    <div class="text-sm space-y-1">
      <div class="flex items-start gap-2">
        <span class="text-red-500 font-bold">✗</span>
        <div>
          <strong class="text-gray-800">意味論的盲点 (Semantic Blindness)</strong>
          <div class="text-xs text-gray-500">
            全実装が共通して仕様を誤解している場合、差分が出ず検知不可。
          </div>
        </div>
      </div>
      <div class="flex items-start gap-2">
        <span class="text-red-500 font-bold">✗</span>
        <div>
          <strong class="text-gray-800">Deep Stateへの到達困難性</strong>
          <div class="text-xs text-gray-500">
            特定のDeFi状態やバリデータ退出処理など、複雑な前提状態に到達できない。
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

</div>

<div class="mt-6 p-4 bg-blue-50 rounded-lg border-2 border-blue-400">
  <div class="text-center">
    <div class="text-lg font-bold text-blue-700 mb-2">
      Research Question
    </div>
    <div class="text-sm">
      LLMのエージェント性を用い、仕様理解に基づく
      <strong>「熟練監査員の検証プロセス」</strong>を自動化できないか？
    </div>
  </div>
</div>

<div class="absolute bottom-2 left-2 text-[8px] text-gray-400 max-w-[90%] leading-relaxed">
  <div><strong class="text-gray-500">[Client Diversity]</strong> https://ethereum.org/en/developers/docs/nodes-and-clients/client-diversity/</div>
  <div><strong class="text-gray-500">[CFBs]</strong> Tyr(S&P'23): https://doi.org/10.1109/SP46215.2023.10179386</div>
</div>

<!--
既存手法における課題と、本研究の動機について説明します。

まず背景として「Client Diversity」があります。
イーサリアムはN種類のELとM種類のCLを組み合わせることで耐障害性を確保していますが、これは同時にリスクも孕んでいます。
それが「Consensus Failure Bugs (CFBs)」です。
実装間のわずかな解釈の違いが、チェーンの分岐（Chain Split）という致命的な障害を引き起こす可能性があります。

これに対し、これまでは「差分ファジング」が有効とされてきました。
代表的な手法として、Fluffyは複数トランザクションを用いた差分ファジング、LOKIはP2Pの状態遷移モデルを考慮したファジング、Forkyは意図的にチェーンを分岐させて検証する手法などがあります。

しかし、これらの手法には「意味論的盲点 (Semantic Blindness)」という限界があります。
もし全クライアントが仕様を同じように誤解していた場合、差分が発生せず、バグを検知できません。
また、複雑なDeFiコントラクトの状態や、バリデータの退出処理といった「Deep State」には、ランダムな入力生成では到達困難です。

そこで我々は、LLMのエージェント性を活用し、仕様書を理解した上で「熟練監査員のような検証プロセス」を自動化することで、これらの限界を突破できないかと考えました。
-->
