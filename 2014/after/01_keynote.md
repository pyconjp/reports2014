# PyCon JP 2014参加レポート

## はじめに

9月12日（金）～ 15日（月）の4日間にわたり、東京国際交流館プラザ平成において[PyCon JP 2014](https://pycon.jp/2014/)が開催されました。

![オープニング](https://farm4.staticflickr.com/3865/15292487901_e6c44930a3_z.jpg)
オープニング (c) PyCon JP

開催期間中は、チュートリアル、キーノート、セッション、LT、パーティ、スプリントなど本当にたくさんのイベントが行われました。本レポートでは4回にわたって、PyCon JP 2014の模様をお伝えします。第1回目の今回は、PyCon JP 2014の紹介とキーノートの模様をお伝えします。

## PyCon JP 2014とは

PyConとは、日本を含む世界各国で開催されており、Pythonユーザーが集まり、Pythonに関する知識を共有したり、交流を深めるためのイベントです。PyCon JP は日本で開催されるカンファレンスで、毎年規模が大きくなっており、日本を含む世界各国から参加者が集まります。今年は **「Python で再発見 - Rediscover with Python」** をテーマとして開催され、545名の方が参加しました。

## キーノート & セッション

PyCon JP 2014ではYouTube Liveによってほとんどのセッションが生放送されました。またセッションの録画をYouTubeで見ることができるようになっています。

### PyCon Japan 2014の動画

* http://www.youtube.com/playlist?list=PLMkWB0UjwFGm4Ao5w2CKv24tl_Op_kxs5
	

## 1日目基調講演 Kenneth Reitz氏 Python 2.7 and Python 3: A Sacred Love Story

1日日の基調講演はKenneth Reitz氏でした。Kenneth氏は、HerokuのPythonプロダクトオーナーであり、Python Software Foundationのフェローです。
まずは自己紹介として、Kenneth氏が関わっているプロジェクトやライブラリの紹介をしていました。またKenneth氏が興味をもっている写真や音楽、さらにスピーカーとしての活動について話しました。

![Kenneth Reitz氏（１）](https://farm4.staticflickr.com/3869/15254824341_f80de5374b_z.jpg)
Kenneth Reitz氏（１） (c) PyCon JP

### Language
    
次に言語に関する4つの軸および、言葉の伝え方の変化について述べました。人間は言葉を通じて、アイデアを人に伝えており、時間とともに伝え方が変化していること、また人間のハードウェア（体）は変化しないが、ソフトウェア（伝えるスキル）は常にアップデートされている事を述べました。

#### 軸

* Self
* Other
* Time
* Space

#### 伝え方

* 初期の人類（自分で考える）
* 言葉を話す（他の人に説明する）
* 言葉を書く（アイデアは時間を超えて存続する）

次にコミュニケーションの変革について、具体的な事例を交えて説明しました。現代は人類の歴史において多対多で発信できる初めての機会になったと紹介していました。

#### コミュニケーション

**One to One**

* 一人もしくは少数の人数とコミュニケーションするのに使われた

**One to Many**

* 印刷機が発明され、大多数の人とコミュニケーション出来るようになった
* 新聞、本、テレビ、ラジオなど

**Many to Many**

* インターネット
* インターネットにアクセスすれば、たくさんの情報とアイデアにアクセス出来る
* 誰でも、どんなことでも、大多数の人に対して、発信できるようになった
* とても素晴らしいこと（世界中の開発者と時間や距離を超えてコミュニケーションできる）

### Python

#### The Zen of Python

次にPythonの話題に移りました。まずはimport thisで有名な[The Zen of Python](http://legacy.python.org/dev/peps/pep-0020/)からいくつかの項目を紹介し、Kenneth氏がPythonを特別だと思っていて、Pythonが好きだという事を紹介しました。

* Beautiful is better than ugly.
* Explicit is better than implicit
* Simple is better than complex.
* Complex is better than complicated.

そして現状のPythonには、Python2、Python3が存在していること、またその部分で分断があるので、それを解決するためにPython3をみんなで使って、フィードバックしていこうという問題提起のプレゼンテーションでした。Kenneth氏のスライドにある[You are the solution.] いう言葉がとても印象的で、Pythonを利用する私たちが、もっと問題意識をもって、積極的にPython3を利用していこうと考えさせられる内容でした。質疑応答でもPython3に関連する話題がとても多く、非常にエキサイティングなセッションとなりました。

![Kenneth Reitz氏（２）](https://farm4.staticflickr.com/3908/15071365558_b62e1cabdb_z.jpg)
Kenneth Reitz氏（２） (c) PyCon JP

スライド

* https://speakerdeck.com/kennethreitz/python-2-dot-7-and-python-3-a-sacred-love-story

動画

* http://youtu.be/9oJXzlmGJKc?list=PLMkWB0UjwFGm4Ao5w2CKv24tl_Op_kxs5


## 2日目基調講演 西尾泰和氏 ─Rediscover with Python

2日日の基調講演はサイボウズ・ラボのエンジニアである西尾氏が登壇しました。西尾氏はサイボウズ・ラボで、未来のグループウェアの研究開発をしています。昨年出版した[「 コーディングを支える技術 」](http://gihyo.jp/magazine/wdpress/plus/978-4-7741-5654-5)はベストセラー、重版を経て、先日韓国語版、中国語版が出版されました。現在英語版も翻訳作業を行っているようです。

### evil pythonista

西尾氏はまず2006年のLL Ring「じゃんけん2.0」で書いたPythonでのじゃんけんプログラムの例をあげ、自らをevil pythonista（邪悪なpythonista）と称して自己紹介を行いました。作成したプログラムはワンライナーで記述され、if、while、try..exceptなどの構文が使えない中、いかに工夫してプログラムを書いたか説明していました。実際に使用したプログラムをスクリーンに表示した時は、会場は大きな笑いに包まれました。

![西尾泰和氏（１）](https://farm6.staticflickr.com/5569/15071276549_bb33abf9dc_z.jpg)
西尾泰和氏（１）(c) PyCon JP

### サイボウズにおけるPython利用シーン

西尾氏はサイボウズ・ラボで、次世代グループウェアの基盤となる技術を中長期視点で研究開発しており、サイボウズではPythonを次のシーンで利用していると説明を行いました。

* 自動化（VM、ストレージ･各種設定の管理、テスト、Jenkinsのスクリプト）
* インフラ（Remote Backup、P2P automatic failure recovery system)
* 解析（データの収集、クレンジング、フィルタリング、統計処理）

インフラのセクションではデータセンターのストレージバックアップの事例や、P2Pの自動障害回復システムの事例を上げ、高速化が必要な部分をC++やJavaで記述し、Pythonでそれらのコンポーネントをつなぎ合わせていると述べていました。
サイボウズのような大規模な事例でのPythonの使用例を知ることが出来て、とても参考になりました。

* https://enterprise.cybozu.com/topics131111/
* http://developer.cybozu.co.jp/tech/?p=5799

西尾氏は上記に挙げた項目のうち、一番コントリビュートしているのは解析の部分だと説明し、実際にサイボウズのプロダクトである「kintone」に搭載されているおすすめグラフ（Chart recommendation）について説明を行いました。色々なデータの統計情報を元に、情報のありそうなグラフを選択して、表示してくれる仕組みのようです。西尾氏がFlask、NumPyを使用してプロトタイプを作成し、最終的には製品版のアプリケーションではJavaScriptに移植して作成されたようです。

* http://developer.cybozu.co.jp/tech/?p=3874

### グループウェア

次にグループウェアについてのお話となりました。グループウェアとはGroup + Softwareであり、ソフトウェアによって集団の能力を増強するソフトウェアであると述べていました。人間は既にコンピューターによって増強されており、どうすればもっと増強できるかを考えていると話していました。具体例としてGoogleがある状態とない状態を比較して、知識が強化されているのは前者のほうであると説明していました。またモニタリングの研究や、次のエンゲルバードによる人間増強の四要素について解説しました。

#### 人間増強の四要素

* 1: 人工物(Artifacts): コンピュータ、ソフトウェア、etc. 
* 2: 言語(Language): 概念を表す専門用語、デザパタ、etc. 
* 3: 方法論(Methodology): 問題解決のための手順、戦略、etc. 
* 4: 教育(Training): 1～3を使うスキルを身につける

*エンゲルバート"Augmenting Human Intellect: A Conceptual Framework" (1962)* 

### Rediscover with Python

次に今回のカンファレンスのテーマである**Rediscover with Python**についてのお話となりました。
まず問題を再発見するにはどうしたら良いかという問いかけがあり、どんな視点で物事をみても、かならず見えてない部分があり、その見えてない部分を知るために視点を変える必要があると述べました。

* 明らかに知っている領域
* 明らかに知らない領域
* 知らないことを知らない領域がある。

さらに見えてないのにそれに気づいていない盲点（blind spot）を見つけるためにはどうすれば良いか、次の5つの項目を掲げ、具体例を交えて解説していました。西尾氏の幅広い知識と深い洞察をもとにした発表内容はとても素晴らしく、今後のエンジニア人生にとって、とても参考になる内容でした。

* Comparison（比較）
* History（歴史）
* Experience（経験）
* Abstraction（抽象）
* Communication（コミュニケーション）

![西尾泰和氏（２）](https://farm4.staticflickr.com/3901/15273959086_f71d9fec25_z.jpg)
西尾泰和氏（２） (c) PyCon JP

スライド

* http://www.slideshare.net/nishio/pyconjp-keynote-speach-japanese-version

動画

* http://youtu.be/3AVt6A7qaOg?list=PLMkWB0UjwFGm4Ao5w2CKv24tl_Op_kxs5


## 次回予告

第2回ではPyCon JP 2014のカンファレンスのセッション（1日目）の内容をお届けします。
