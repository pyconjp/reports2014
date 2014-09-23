# PyCon JP 2014参加レポート

## はじめに

9月12日（金）～ 16日（月）の4日間にわたり、下記の会場においてPyCon JP 2014が開催されました。

* 市ケ谷健保会館・会議室（チュートリアル）
* 東京国際交流館プラザ平成（カンファレンス）
* 日本マイクロソフト株式会社　品川オフィス（スプリント）

![オープニング](https://farm4.staticflickr.com/3865/15292487901_e6c44930a3_z.jpg)
オープニング (c) PyCon JP

開催期間中は、チュートリアル、キーノート、セッション、LT、パーティ、スプリントなど本当にたくさんのイベントが行われました。本記事では4回にわたって、PyCon JP 2014の模様をお伝えします。第1回目の今回は、PyConJPの紹介とキーノートの模様をお伝えします。

## PyCon JP 2014とは

PyConとは、日本を含む世界各国で開催されており、Pythonユーザーが集まり、Pythonに関する知識を共有したり、交流を深めるためのイベントです。PyCon JP は日本で開催されるカンファレンスで、毎年規模が大きくなっており、今年は500人以上の参加者がありました。今年は「Python で再発見 - Rediscover with Python」をテーマとして開催されました。

## 1日目基調講演 Kenneth Reitz氏 Python 2.7 and Python 3: A Sacred Love Story

初日の基調講演はKenneth Reitz氏でした。Kenneth Reitz氏は、HerokuのPythonプロダクトオーナーであり、Python Software Foundationのフェローです。

![Kenneth Reitz氏（１）](https://farm4.staticflickr.com/3869/15254824341_f80de5374b_z.jpg)
Kenneth Reitz氏（１） (c) PyCon JP

### Language

Kenneth氏はまず言語に関する4つの軸、言葉の伝え方の変化について述べました。人間は言葉を通じて、アイデアを人に伝えており、時間とともに伝え方に変化があること、また人間のハードウェアは変わらないがソフトウェアは常にアップデートされていると述べました。

#### 軸

* Self
* Other
* Time
* Spach

#### 言語

* 初期の人類 自分で考える
* 言語を話す（他の人に説明する）
* 言語を書く（アイデアは時間を超えて存続する）

次にコミュニケーションの方法の変革について、具体的な事例を交えて説明しました。現代は人類の歴史において多対多で発信できる初めての機会だと述べました。

#### コミュニケーション

**One to One**

* 一人もしくは少数の人数とコミュニケーションするのに使われた

**One to Many**

* 印刷機が発明され、大多数の人とコミュニケーション出来るようになった。
* 新聞、本、テレビ、ラジオなど

**Many to Many**

* インターネット
* インターネットにアクセスすれば、たくさんの情報とアイデアにアクセス出来る。
* 誰でも、どんなことでも、大多数の人に対して、発信できるようになった。

### Python



![Kenneth Reitz氏（２）](https://farm4.staticflickr.com/3908/15071365558_b62e1cabdb_z.jpg)
Kenneth Reitz氏（２） (c) PyCon JP


スライド

* https://speakerdeck.com/kennethreitz/python-2-dot-7-and-python-3-a-sacred-love-story

動画

* https://www.youtube.com/playlist?list=PLMkWB0UjwFGm4Ao5w2CKv24tl_Op_kxs5/


## 2日目基調講演 西尾泰和氏 ─Rediscover with Python

西尾氏はサイボウズ・ラボのエンジニアであり、未来のグループウェアの研究開発をしています。昨年出版した「 コーディングを支える技術 」はベストセラー、重版を経て、先日韓国語版、中国語版が出版されました。

![西尾泰和氏（１）](https://farm6.staticflickr.com/5569/15071276549_bb33abf9dc_z.jpg)
西尾泰和氏（１）(c) PyCon JP


### evil pythonista

西尾氏はまず2006年のLL Ring「じゃんけん2.0」で書いたPythonでのじゃんけんプログラムの例をあげ、自らをevil pythonista（邪悪なpythonista）と自己紹介を行いました。プログラムはワンライナーで記述され、if、while、try..exceptなどの構文が使えない中、いかに工夫してプログラムを書いたかの紹介と、実際のプログラムを提示して、会場は大きな笑いに包まれて講演はスタートしました。

### サイボウズにおけるPython利用シーン

西尾氏はサイボウズ・ラボで、次世代グループウェアの基盤となる技術を中長期視点で研究開発しており、サイボウズではPythonを次のシーンで利用しているとの述べていました。

* 自動化（VM、ストレージ･各種設定の管理、テスト、Jenkinsのスクリプト）
* インフラ（Remote Backup、P2P automatic failure recovery system)
* 解析（データの収集、クレンジング、フィルタリング、統計処理）

インフラのセクションではデータセンターのストレージバックアップの事例や、P2Pの自動障害回復システムの事例を上げ、高速化が必要な部分JavaやC++で記述し、Pythonでそれらのコンポーネントをつなぎ合わせていると述べていました。

* https://enterprise.cybozu.com/topics131111/
* http://developer.cybozu.co.jp/tech/?p=5799

解析のセクションでは、実際にサイボウズのプロダクトである「kintone」に搭載されているおすすめグラフの（Chart recommendation）の紹介がありました。西尾氏がFlask、NumPyを使用してプロトタイプを作成したとの解説がありました。

* http://developer.cybozu.co.jp/tech/?p=3874

### Rediscover with Python

次に今回のカンファレンスのテーマである[Rediscover with Python]についてのお話となりました。
まず再発見するにはどうしたら良いかという問いかけを行い、どんな視点で物事をみても、かならず見えてない部分があり、見えてない部分を知るために視点を変える必要があると述べました。

* 明らかに知っている領域
* 明らかに知らない領域
* 知らないことを知らない領域がある。

さらに見えてないのにそれに気づいていない盲点（blind spot）を見つけるためにはどうすれば良いか、次の5つの項目を掲げ、具体例を交えて解説していました。

* Comparison
* History
* Experience
* Abstraction
* Communication


![西尾泰和氏（２）](https://farm4.staticflickr.com/3901/15273959086_f71d9fec25_z.jpg)
西尾泰和氏（２） (c) PyCon JP

スライド
* http://www.slideshare.net/nishio/pyconjp-keynote-speach-japanese-version

動画
* https://www.youtube.com/watch?v=3AVt6A7qaOg&list=UUxNoKygeZIE1AwZ_NdUCkhQ







