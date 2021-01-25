---
title: "ケーススタディ: クリケット分析、ゲームチェンジャー!"
sidebar: false
---

{{< figure src="/images/content_images/cs/ipl-stadium.png" caption="** IPLT20、インド最大のクリケットフェスティバル**" alt="Indian Premier League Cricket cup and stadium" attr="*(Image credits: IPLT20 (cup and logo) & Akash Yadav (stadium))*" attrlink="https://unsplash.com/@aksh1802" >}}

<blockquote cite="https://www.scoopwhoop.com/sports/ms-dhoni/">
    <p>観客のために競技をするのではなく、国のために競技するのです。</p>
    <footer align="right">—M S Dhoni、 <cite>インディアンチームの元キャプテン、インターナショナル・クリケットプレイヤー、チェンナイ・スーパー・キングスのためにIPLでプレイ</cite></footer>
</blockquote>

## クリケットについて

インド人はクリケットが大好きだと言っても過言ではないでしょう。 この競技は、他のスポーツと異なり、インドの農村部や都市部を問わず、あらゆる場所でプレイされており、若者から年配の方まで広く人気があり、インドでは何十億人もの人々を結びつける役割を担っています。 クリケットは多くのメディアの注目を集めています。 非常に [多額のお金](https://www.statista.com/topics/4543/indian-premier-league-ipl/)と名声がかかっています。 過去数年間、テクノロジーは文字通りクリケットの試合を変えてきました。 視聴者は、ストリーミングメディアや、トーナメント、モバイルベースの手頃なアクセスによるライブクリケット視聴や、その他の方法に甘やかされています。

インドプレミアリーグ (IPL) は、2008年に設立された20チームから成るプロクリケットリーグです。 これは、2019年に [67億ドル](https://en.wikipedia.org/wiki/Indian_Premier_League) の市場規模と評価される世界で最も参加者が多いクリケットイベントの1つです。

クリケットは数のゲームです - バッツマンによってスコアされたランの数、ボウラーによって取られたウィケットの数、クリケットチームによって獲得した試合の数、バッツマンがボウリング攻撃に特定の方法で応答する回数など。 クリケットの数字を掘り下げてパフォーマンスを向上させるとともに、NumPyなどの数値計算ソフトウェアを利用した強力な分析ツールを介して、クリケットのビジネスチャンス、市場全体、経済性を研究することは、大きな意味を持ちます。 クリケット分析は、試合に関する興味深い洞察と、ゲームの結果に関する予測AIを提供します。

現在では、クリケットゲームの記録と 利用可能な統計データは豊富で、ほぼ無限の宝の山だと言えます。: [ESPN cricinfo や](https://stats.espncricinfo.com/ci/engine/stats/index.html) [cricsheet](https://cricsheet.org). これらのクリケットデータベースは、最新の機械学習と予測モデリングアルゴリズムを使用して、 [クリケット 分析](https://www.researchgate.net/publication/336886516_Data_visualization_and_toss_related_analysis_of_IPL_teams_and_batsmen_performances) に使用されています。 メディアやプロスポーツ団体のエンターテインメントプラットフォームは、技術や分析を利用し、試合勝率を向上させるための主要なメトリックを下記のような要素だと考え始めています:

* バッティングの記録の移動平均
* スコア予測
* gaining insights into fitness and performance of a player against different opposition,
* player contribution to wins and losses for making strategic decisions on team composition

{{< figure src="/images/content_images/cs/cricket-pitch.png" class="csfigcaption" caption="**Cricket Pitch, the focal point in the field**" alt="A cricket pitch with bowler and batsmen" align="middle" attr="*(Image credit: Debarghya Das)*" attrlink="http://debarghyadas.com/files/IPLpaper.pdf" >}}

### Key Data Analytics Objectives

* Sports data analytics are used not only in cricket but many [other sports](https://adtmag.com/blogs/dev-watch/2017/07/sports-analytics.aspx) for improving the overall team performance and maximizing winning chances.
* Real-time data analytics can help in gaining insights even during the game for changing tactics by the team and by associated businesses for economic benefits and growth.
* Besides historical analysis, predictive models are harnessed to determine the possible match outcomes that require significant number crunching and data science know-how, visualization tools and capability to include newer observations in the analysis.

{{< figure src="/images/content_images/cs/player-pose-estimator.png" class="fig-center" alt="pose estimator" caption="**Cricket Pose Estimator**" attr="*(Image credit: connect.vin)*" attrlink="https://connect.vin/2019/05/ai-for-cricket-batsman-pose-analysis/" >}}

### The Challenges

* **Data Cleaning and preprocessing**

  IPL has expanded cricket beyond the classic test match format to a much larger scale. The number of matches played every season across various formats has increased and so has the data, the algorithms, newer sports data analysis technologies and simulation models. Cricket data analysis requires field mapping, player tracking, ball tracking, player shot analysis, and several other aspects involved in how the ball is delivered, its angle, spin, velocity, and trajectory. All these factors together have increased the complexity of data cleaning and preprocessing.

* **Dynamic Modeling**

  In cricket, just like any other sport, there can be a large number of variables related to tracking various numbers of players on the field, their attributes, the ball, and several possibilities of potential actions. The complexity of data analytics and modeling is directly proportional to the kind of predictive questions that are put forth during analysis and are highly dependent on data representation and the model. Things get even more challenging in terms of computation, data comparisons when dynamic cricket play predictions are sought such as what would have happened if the batsman had hit the ball at a different angle or velocity.

* **Predictive Analytics Complexity**

  Much of the decision making in cricket is based on questions such as "how often does a batsman play a certain kind of shot if the ball delivery is of a particular type", or "how does a bowler change his line and length if the batsman responds to his delivery in a certain way". This kind of predictive analytics query requires highly granular dataset availability and the capability to synthesize data and create generative models that are highly accurate.

## NumPy’s Role in Cricket Analytics

Sports Analytics is a thriving field. Many researchers and companies [use NumPy](https://adtmag.com/blogs/dev-watch/2017/07/sports-analytics.aspx) and other PyData packages like Scikit-learn, SciPy, Matplotlib, and Jupyter, besides using the latest machine learning and AI techniques.  NumPy has been used for various kinds of cricket related sporting analytics such as:

* **Statistical Analysis:** NumPy's numerical capabilities help estimate the statistical significance of observational data or match events in the context of various player and game tactics, estimating the game outcome by comparison with a generative or static model. [Causal analysis](https://amplitude.com/blog/2017/01/19/causation-correlation) and [big data approaches](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4996805/) are used for tactical analysis.

* **Data Visualization:** Data graphing and [visualization](https://towardsdatascience.com/advanced-sports-visualization-with-pandas-matplotlib-and-seaborn-9c16df80a81b) provides useful insights into relationship between various datasets.

## Summary

Sports Analytics is a game changer when it comes to how professional games are played, especially how strategic decision making happens, which until recently was primarily done based on “gut feeling" or adherence to past traditions. NumPy forms a solid foundation for a large set of Python packages which provide higher level functions related to data analytics, machine learning, and AI algorithms. These packages are widely deployed to gain real-time insights that help in decision making for game-changing outcomes, both on field as well as to draw inferences and drive business around the game of cricket. Finding out the hidden parameters, patterns, and attributes that lead to the outcome of a cricket match helps the stakeholders to take notice of game insights that are otherwise hidden in numbers and statistics.

{{< figure src="/images/content_images/cs/numpy_ca_benefits.png" class="fig-center" alt="Diagram showing benefits of using NumPy for cricket analytics" caption="**Key NumPy Capabilities utilized**" >}}