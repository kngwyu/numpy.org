---
title: "ケーススタディ: DeepLabCut 三次元姿勢推定"
sidebar: false
---

{{< figure src="/images/content_images/cs/mice-hand.gif" class="fig-center" caption="**DeepLapCutを用いたマウスの手の動きの解析 **" alt="micehandanim" attr="*(Source: www.deeplabcut.org )*" attrlink="http://www.mousemotorlab.org/deeplabcut">}}

<blockquote cite="https://news.harvard.edu/gazette/story/newsplus/harvard-researchers-awarded-czi-open-source-award/">
    <p>オープンソースソフトウェアは生体臨床医学を加速させています。 DeepLabCut を使用すると、Deep Learningを使用して動物の行動を自動的にビデオ解析することができます。</p>
    <footer align="right">—Alexander Mathis、 <cite>准教授、École polytechnology fe’rale de Lausanne <a href="https://www.epfl.ch/en/">(EPFL)</a></cite></footer>
</blockquote>

## DeepLabCut について

[DeepLabCut](https://github.com/DeepLabCut/DeepLabCut) は世界中の何百もの研究機関の研究者が、ごくわずかなトレーニングデータで、人間レベルの精度で実験動物の行動を追跡可能にするオープンソースのツールボックスです。 DeepLabCutの技術により、科学者は動物の種類と時系列のデータを元に、運動制御と行動に関する科学的な理解を深めることができるようになりました。

神経科学、医学、生体力学などのいくつかの研究分野では、動物の動きを追跡したデータを使用しています。 DeepLabCut は、動画に記録された動きを解析することで、人間やその他の動物が何をしているのかを理解することができます。 タグ付けや監視などの、手間のかかる作業に自動化を利用し、深層学習ベースのデータ解析を実施します。DeepLabCut は、霊長類、マウス、魚、ハエなどの動物を観察する科学的研究に利用されており、より速く、正確な結果をもたらしました。

{{< figure src="/images/content_images/cs/race-horse.gif" class="fig-center" caption="**色のついた点は競走馬の体の位置を追跡**" alt="horserideranim" attr="*(Source: Mackenzie Mathis)*">}}

DeepLabCutによる動物の姿勢を抽出することによる、非侵襲的な行動追跡は、生体力学や、遺伝学、倫理学、神経科学などの分野における科学的な研究に必要不可欠です。 動的に変化する背景の中で、動物の姿勢をビデオデータから非侵襲的に測定することは、計算処理的に非常に困難です。 例えば、必要な計算リソースやトレーニングデータが問題になります。

DeepLabCutは、研究者が対象の姿勢をを推定することができ、Pythonベースのソフトウェアを使って効率的に対象の行動を定量化することを可能にします。  DeepLabCutを使用すると、研究者は動画から異なるフレームを識別し、数十個のフレームの特定の身体部位にデジタルなラベルを貼ることができます。また、DeepLabCutのディープラーニングベースのポーズ推定アーキテクチャが、動画の残りの部分や動物の他の類似した動画から同じ特徴を抽出する方法を学習することもできます。 ハエやマウスなどの一般的な実験動物から [チーター][cheetah-movement]のようなより珍しい動物まで、動物の種類を問わず利用する事ができます。

DeepLabCut では [transfer learning](https://arxiv.org/pdf/1909.11229)という技術を使用しています。これにより必要な学習データの量を大幅に削減し、学習の収束を加速させることができます。  必要に応じて、より高速な推論を提供するさまざまなネットワークアーキテクチャ(MobileNetV2など)を選択することができ、リアルタイムの実験データフィードバックと組み合わせることもできます。 DeepLabCutはもともと、ツールの名前の元となった [DeeperCut](https://arxiv.org/abs/1605.03170)と呼ばれる、パフォーマンスの高い人像推定アーキテクチャからの特徴検出器を使用しています。 その過程で、このパッケージには、追加のアーキテクチャや、拡張メソッド、および一通りのフロントエンドユーザエクスペリエンスが得られるように大幅に変更されました。 さらに、 大規模な生物学的実験をサポートするために DeepLabCut はアクティブな学習機能を提供しています。例えば、エッジケースをカバーしたり、特定のコンテキスト内でポーズ推定アルゴリズムを堅牢にするために、時間経過しても学習データを増やすことができます。

最近、[DeepLabCut model zoo](http://www.mousemotorlab.org/dlc-modelzoo)が発表されました。これは、霊長類の顔分析から犬の姿勢まで、様々な種や実験条件に対応した事前訓練済みモデルを提供しています。 これにより、例えば、新しいデータのラベルを付けることなくクラウドで予測を実行することができたり、ニューラルネットワーク学習を実行することができます。また、プログラミング経験は必要ありません。

### 主な目標と結果

* **科学研究のための動物姿勢解析の自動化:**

  DeepLabCut 技術の主な目的は、多様な環境で動物の姿勢を測定し追跡することです。 このデータは、例えば、脳がどのように運動を制御しているかを理解するための神経科学の研究や、動物がどのように社会的に交流しているかを明らかにするために利用することができます。 研究者はDeepLabCutで [10倍のパフォーマンス向上](https://www.biorxiv.org/content/10.1101/457242v1) が可能であると発表しています。 オフラインでは最大1200フレーム/秒(FPS) で姿勢推定することができます。

* **姿勢推定のための使いやすいPythonツールキットの作成:**

  DeepLabCutは、動物の姿勢推定技術を研究者が簡単に利用できるツールとして共有したいという考えから開発されています。 そこでらはプロジェクト管理機能 を備えた、単独で機能し、使いやすいPythonツールボックスとしてこのツールを作成しました。 これにより、姿勢推定の自動化だけでなく、 データセット収集段階から共有可能て、再利用可能な分析パイプラインを作成するDeepLabCut Toolkitを提供し、プロジェクトのエンドツーエンドの管理も可能になりました。

  この[ツールキット][DLCToolkit] はオープンソースとして利用できます。

  DeepLabCut ワークフローは以下のようになります。

  - アクティブ学習によるトレーニングセットの作成と調整を行います
  - 特定の動物やシナリオに合わせたニューラルネットワークの構築
  - 動画における大規模推論のためのコード作成
  - 統合された可視化ツールを使用して推論の描画

{{< figure src="/images/content_images/cs/deeplabcut-toolkit-steps.png" class="csfigcaption" caption="**DeepLabCutによる姿勢推定のステップ**" alt="dlcsteps" align="middle" attr="(Source: DeepLabCut)" attrlink="https://twitter.com/DeepLabCut/status/1198046918284210176/photo/1" >}}

### 課題

* **速度**

    動物行動動画の高速処理は、彼らの行動を測定し、同時に科学実験をより効率的で正確にするために重要です。 動的に変化する背景の中で、マーカーを使用せずに、実験室での実験のために動物の詳細な姿勢を抽出することは、技術的にも、必要なリソース的にも、必要なトレーニングデータの面でも、困難な場合があります。 科学者が、より現実的な状況で研究を行うために、コンピュータビジョンなどの専門知識のスキルを必要とせずに使うことができるツールを開発することは、解決すべき重要な問題です。

* **組み合わせ問題**

    組合せ問題とは、複数の四肢の動きを個々の動物行動に統合することを指します。 キーポイントとそ個々の動物の動きを関連性に基づき組み合わせ、それらを時間的に結びつけることは、複雑なプロセスであり、特に実験映像の中で複数の動物の動きを追跡する場合には、非常に膨大な数値解析が必要となります。

* **データ処理**

    最後に、配列の操作、 様々な画像処理、目標のテンソル処理、キーポイントに対応する大きな配列のスタックを処理することは、かなり難しい問題です。

{{< figure src="/images/content_images/cs/pose-estimation.png" class="csfigcaption" caption="**姿勢推定の多様性と難しさ**" alt="challengesfig" align="middle" attr="(Source: Mackenzie Mathis)" attrlink="https://www.biorxiv.org/content/10.1101/476531v1.full.pdf" >}}

## 姿勢推定の課題に対応するためのNumPyの役割

NumPy は DeepLabCutにおける、行動分析の高速化のための数値計算の核となっています。  NumPyだけでなく、 DeepLabCutは様々なNumPyをベースとしているPythonライブラリを利用しています。: [SciPy](https://www.scipy.org), [Pandas](https://pandas.pydata.org), [matplotlib](https://matplotlib.org), [Tensorpack](https://github.com/tensorpack/tensorpack), [imgaug](https://github.com/aleju/imgaug), [scikit-learn](https://scikit-learn.org/stable/), [scikit-image](https://scikit-image.org) and [Tensorflow](https://www.tensorflow.org).

NumPyの特徴である、画像処理、組み合わせ処理、そして高速計算は、DeepLabCutの姿勢推定アルゴリズムにおいて重要な役割を果たしました。

* ベクトル化
* マスクされた配列操作
* 線形代数
* ランダムサンプリング
* 大きな配列の再構成

DeepLabCutは、ツールキットが提供する ワークフローを通じてNumPyの配列機能を利用しています。 特にNumPy はヒューマンアノテーションのラベル付けや、アノテーションの書き込み、編集、処理のために、特定のフレームをサンプリングするために使用されています。  TensorFlowを使ったニューラルネットワークは、DeepLabCut技術によって何千回も訓練され、 フレームから真アノテーション情報を予測します。 この目的のために、姿勢推定問題を、画像-画像変換問題として変換するための目標密(スコアマップ) を作成します。 ニューラルネットワークのロバスト化のために、幾何学・画像的処理を施した、スコアマップの計算を行うデータオーグメンテーションを採用しています。 また学習を高速化するために、NumPyのベクトル化機能が利用されています。 推論のためには、ターゲットスコアマップから最も可能性の高い予測値を抽出し、効率的に「予測値をリンクさせて個々の動物を組み立てる」ことが必要になります。

{{< figure src="/images/content_images/cs/deeplabcut-workflow.png" class="fig-center" caption="**DeepLabCutのワークフロー**" alt="workflow" attr="*(Source: Mackenzie Mathis)*" attrlink="https://www.researchgate.net/figure/DeepLabCut-work-flow-The-diagram-delineates-the-work-flow-as-well-as-the-directory-and_fig1_329185962">}}

## まとめ

行動を観察し、効率的に表現することは、現代倫理学、神経科学、医学、工学の根幹です。 [DeepLabCut](http://orga.cvss.cc/wp-content/uploads/2019/05/NathMathis2019.pdf) により、研究者は対象の姿勢を推定し、行動を効率的に定量化できるようになりました。 DeepLabCutのPythonツールボックスでは、わずかな学習画像のセットで、ニューラルネットワークを人間レベルのラベリング精度で学習することができ、実験室での行動分析だけでなく、スポーツ、歩行分析、医学、リハビリテーション研究などへの応用が可能になります。 DeepLabCut アルゴリズムに必要な、複雑な組み合わせ処理や、データ処理の問題は、NumPy の配列操作機能を使用して対応することになります。

{{< figure src="/images/content_images/cs/numpy_dlc_benefits.png" class="fig-center" alt="numpy benefits" caption="**NumPyの主要機能**" >}}

[cheetah-movement]: https://www.technologynetworks.com/neuroscience/articles/interview-a-deeper-cut-into-behavior-with-mackenzie-mathis-327618

[DLCToolkit]: https://github.com/DeepLabCut/DeepLabCut
