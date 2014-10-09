# PyCon JP 2014参加レポート（第3回）

PyCon JP 2014参加レポート第3回は、カンファレンス2日目のセッションを中心にお届けします。

## OpenCVのpythonインターフェース入門

はじめにMasaki Hayashi氏によるOpenCVのpythonインターフェース入門のセッションをご紹介します。
Hayashi氏は現在大学院にて機械学習の画像認識の研究をしていており、ブログやWebなどでもコンピュータービジョンについて記事を執筆しているとの事でした。（[コンピュータビジョンのセカイ - 今そこにあるミライ](http://news.mynavi.jp/series/computer_vision/menu.html)）

まずは導入部分で、Computer Visionについての説明を行いました。Computer Visionは次のようなものであることを説明し、また実際のサンプルなどの動画を紹介し、わかりやすく説明していました。

### Computer Visionとは？

* カメラで撮影した画像、動画、デプス（Kinect）などから実世界の様子を計算機で（できれば自動的に）把握する技術分野
* 画像認識、画像処理、3D復元などををひっくるめてComputer Visionと呼ぶ

次にOpenCVの概要ついて次の項目をあげて説明を行いました。OpenCVのPythonから使用する場合の、主要モジュールや、応用モジュールについて解説を行いました。

### OpenCVの概要

* C++言語向けのComputer Vision大規模ライブラリ
* Python、Javaなどのラッパーも標準提供されている。
* 画像処理、動画像入出力、顔検出などComputer Visionの基本的な道具がそろっている。
* 最新バージョンはOpenCV2.4.9

またC++ではなくPythonを利用するメリットとして、下記の特徴を挙げて解説を行いました。インタラクティブに実行して、すぐ結果をみて試せるというのは非常に大きな利点があると感じました。

### PythonでOpenCVを使うメリット

* numpyやscipyとの連携
* C++と違ってインタラクティブに、実験的に実行できる（IPythonも使用できる）
* IPython Notebookによる全ての結果のノート保存、共有 
* Scikit-learn, pandasなど機会学習、データサイエンスとの相性も良い

次にOpenCVによる画像データに関する説明になり、OpenCVで読み込んだ画像データはnumpyの配列になると説明しました。numpy配列になると色々なライブラリとの連携も簡単にできるので、メリットが大きいと感じました。
実際のデモでは、基本的な画像処理であるガウシアンブラー、エッジ検出などの使用例と、画像認識の背景差分、人検出の使用例について説明していました。OpenCVにはあらかじめ色々な関数が用意されているので、デモで見たような処理は比較的簡単にできる事がわかりました。


![Masaki Hayashi氏](https://farm4.staticflickr.com/3858/15110598479_2e41c306bb_z.jpg)
Masaki Hayashi氏 (c) PyCon JP

## PyNES: Python programming for Nintendo 8 bits.

次にGuto Maia氏によるPyNES: Python programming for Nintendo 8 bitsのセッションを紹介します。Maia氏はブラジルから来日したようで、まず冒頭でブラジルのPythonのコミュニティイベントである、[PythonBrazil](http://2014.pythonbrasil.org.br)について紹介を行いました。今年のPythonBrazilはビーチの近くで開催されるとの事でした。

最初にDjangoアプリを高速化するためのポイントとして、次の項目をあげ１つづつ解説を行いました。

* SQLを減らす
* インデックス
* キャッシュ
* アプリケーション外

### SQLを減らす

まずはアプリケーションが動作しているときに、色々な情報を可視可するためのツールとしてdjango-debug-toolbarを紹介しました。django-debug-toolbarを使用するとブラウザ上からSQLを含め様々な情報を閲覧する事ができます。実際にアプリケーションを動かしながらSQLを確認する事によって、無駄なSQLを取り除く事が可能になります。次にSQLを減らすための仕組みとして、Djangoのモデルのselect_relatedやprefetch_related、bulk_createdなどのメソッドの紹介をしました。ORMが実行するSQLを知り、それに１つづつ対処していく事が重要であると再認識しました。

* [django-debug-toolbar](https://github.com/django-debug-toolbar/django-debug-toolbar)
* select_related、prefetch_related

### インデックス

次にインデックスについての説明になりました。RDBを相手にしているので、SQLを確認しながら、適切なインデックスを使用する事が重要だと説明しました。またJet Profilerなどのツールの紹介も行いました。

* [Jet Profiler for MySQL](http://www.jetprofiler.com/)
* extra クエリの一部分を生SQLで書く
* raw クエリを生SQLで書く
* テーブル設計が重要

### キャッシュ

アプリケーションのキャッシュには次の4種類があり、上のものほど効果的だと紹介しました。またRedisでのキャッシュについて例をあげ解説を行いました。キャッシュはアプリケーションの複雑度が増すので、設計を適切に行う事が重要だと説明しました。

* レスポンスキャッシュ
* ビューキャッシュ
* テンプレートキャッシュ
* オブジェクトキャッシュ

### アプリケーション外

次にアプリケーション外でのパフォーマンスを向上させるための施策についての話題となりました。セッションのバックエンドの修正や、静的ファイルの圧縮、DBのマスター、スレーブ構成のためのライブラリの紹介や設定方法について解説しました。実際の事例を元にしたライブラリの紹介だったのでとても参考になりました。

* セッションバックエンド（[django-redis-sessions](https://github.com/martinrusev/django-redis-sessions))
* 静的ファイル圧縮（[django-compressor](https://github.com/django-compressor/django-compressor), [django-asset](https://github.com/miracle2k/django-assets)）
* DBのPrimary/Replica構成（[django-replicated](https://github.com/yandex/django_replicated)）

### FunkLoadパフォーマンス測定

最後に負荷試験ツールFunkLoadの紹介を行いました。Pythonでシナリオを記述でき、実際にGETやPOSTを行ってパフォーマンスが測定できると説明しました。レポート機能もあり、今後使用してみたいと思いました。

* [FunkLoad](http://funkload.nuxeo.org/)
* 負荷試験ツール（Pythonで記述）
* セッション付きのシナリオ
* 静的ファイルの自動取得

![Guto Maia氏](https://farm4.staticflickr.com/3853/15257611232_4de5d669cc_z.jpg)
Guto Maia氏（１） (c) PyCon JP


## Improving code quality through static analysis for Python

次にShinji Iwaki氏によるセッションについて紹介します。Iwaki氏は主に業務で分析や最適化を行っていて、ITを利用して問題を解決する場合の、フローについて例を交えて説明しました。
最適化を行うまでには、下記のようにいくつかのステップがあり、Iwaki氏は以前はC#で問題を解決していましが、Pythonを使用する事でより簡単に学んだり、実行する事ができるようになったと説明しました。

### Flow of problem - solving with IT

* Collect
* Parse
* Analyze
* Optimize
* Visualize

次に各ステップで使用するライブラリや、ツールについて具体的に紹介し、IPythonにてデモを交えながら説明していました。デモは[TV番組の情報](http://kakaku.com/tv/)をスクレイピングして、解析、ビジュアライズするという内容でした。著名人のTVへの出現頻度などがわかりやすくビジュアライズされており、とてもわかりやすく、大変楽しめるセッションでした。

### Collect & Parse

* [urllib](http://docs.python.jp/3.4/library/urllib.html#module-urllib)
* [Requests](http://jp.python-requests.org/en/latest/)
* [Scrapy](http://scrapy.org)
* [BeautifulSoup4](http://www.crummy.com/software/BeautifulSoup/)
* [tweepy](http://www.tweepy.org)

### Analyzing data

* [pandas](http://pandas.pydata.org)
* [scikit-learn](http://scikit-learn.org/stable/)
* [SciPy](http://www.scipy.org)
* [NumPy](http://www.numpy.org)

### Visualization

* [mathplotlib](http://matplotlib.org)

### Optimization

* [pulp](https://pypi.python.org/pypi/PuLP)

![Shinji Iwaki氏（１）](https://farm6.staticflickr.com/5593/15294751621_e523c353db_z.jpg)
Shinji Iwaki氏（１） (c) PyCon JP


## データ分析の世界へようこそ！ ～マーケティングに活かせるPythonライブラリ～

Hirotaka Kawata氏によるMicro Pythonに関するセッションをご紹介します。[Micro Python](http://micropython.org/)はマイコン上で動作する新しいPythonのオープンソースの実装で、PyBoardというボードと共に、KICKSTARTERで投資を集めて開発されていると説明しました。
またMicro Pythonには後述する特徴があり、Raspberry Piやmrubyとの違いなどわかりやすく解説していました。特にmrubyとの思想の違いはとても参考になりました。Micro Pythonは主にマイコンやホビー向けの製品であり、REPLでインタラクティブに操作できるのが大きな特徴のようです。

![Ransui Iso氏（１）](https://farm4.staticflickr.com/3868/15297539462_f76efc3586_z.jpg)
Hirotaka Kawata氏 (c) PyCon JP

### Micro Pythonの特徴

* マイコン上でPythonが動く
* Python3互換のPython処理系（マイコン向けに再実装）
* REPLが使える（インタラクティブにマイコンを操作できる）

PyBoardに関しては、KICKSTARTERの購入分は既に発送済みらしく、すぐには入手不可能とのことでしたが、代わりに[STM32F4DISCOVERY](http://akizukidenshi.com/catalog/g/gM-05313/)という秋月電子通称で購入できるボードをカスタマイズする事でMicro Pythonを動作させる事が出来るとの事でした。実際のデモでは、カスタマイズしたボードを利用して、REPLにてLEDを点滅させたり、LCDに文字列を表示させたりしていました。インタラクティブにボードを動かす事ができるのは、とても面白かったです。私もマイコンなどには興味があったので、今後機会があれば挑戦してみたいと思いました。

## Pythonではじめる野球プログラミング

最後にRansui Iso氏によるPythonのXML-RPCモジュールのセッションをご紹介します。Iso氏は1998年頃からPythonを使っていて、様々な開発を行ってきたそうです。現在はネットの広告配信の仕組みを研究開発しており、最近はCommon Lispで開発をしながら、Pythonもヘビーに使用しているとのことでした。まずは冒頭でRPCに関しての歴史的な紹介と、そもそもRPCとは何かということをわかりやすく説明していました。
そしてPythonでのXML-RPCの特徴について解説を行い、サーバー側、クライアント側の実装について解説を行いました。また設計、実装上のヒントやTipsの紹介を行いました。


![Ransui Iso氏（１）](https://farm4.staticflickr.com/3844/15071310480_db21658b09_z.jpg)
Ransui Iso氏（１） (c) PyCon JP

### PythonでのXML-RPC

* 標準ライブラリ
* xmlrpc.server（サーバー側）
* xmlrpc.client（クライアント側）
* PurePythonによる実装
* CPythonがあればどこでも使用可能

#### サーバー側

* SimpleXMLRPCServer（サーバー）
* SimpleXMLRPCRequestHandle（公開する機能）
* 上記両方を組み合わせる

#### クライアント側 

* ServerProxy

#### Tips

* MetaClassの利用
* スレッド化（Socketserver.ThreadingMixIn）
* オブジェクトのバイナリデータの送受信

最後に事例として、実際に開発したディレクトリ型のポータルサイトについて解説を行いました。およそ30万件ほどのデータが格納されており、データベースと検索にPythonのXML-RPCのライブラリを使用しているそうです。
Pythonでは標準ライブラリが非常に充実しており、XML-RPCを行う処理もほんの少しのコードで実現する事が可能だとわかりました。今後色々なライブラリを調査して今後の開発に活用していきたいと思いました。

## 次回予告

1日日は全部で21個のセッションが行われ、そのうち7つのセッションが英語での発表となりました。発表者、参加者ともに、様々な国の方が参加しており、とても国際色が豊かなセッションでした。
発表内容もフレームワーク、ツール、ライブラリ、言語仕様、言語実装、データ分析、解析、組み込みなど多岐にわたり、今年のPyCon JPのテーマである**Python で再発見 - Rediscover with Python**にふさわしい内容でした。
ここではいくつかの発表を紹介させて頂きましたが、他のセッションに関しても次のリンクより資料、動画を閲覧する事ができますので、ぜひご覧頂ければと思います。

* [PYCON JP 2014 発表資料一覧](https://pycon.jp/2014/reports/slides/)

第3回ではPyCon JP 2014のカンファレンスのセッション（2日目）の内容をお届けします。