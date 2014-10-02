# PyCon JP 2014参加レポート（第２回）

![PyCon JP 2014](https://farm6.staticflickr.com/5591/15257526262_df89aa943a_z.jpg)

PyCon JP 2014参加レポート第2回は、カンファレンス１日日のセッションを中心にお届けします。

## Djangoによるスマホアプリバックエンドの実装

はじめにYuichi Nakazawa氏とKazuhiko Kakita氏によるスマホアプリのバックエンド実装に関するセッションを紹介します。
現在、両氏とも長野県で働いており、また[GEEKLAB.NAGANO](http://geeklab-nagano.com/)というオープンスペースの管理人をしているとのことでした。長野県に行ったときには、ぜひ立ち寄りたいと思います。

まずは導入部分で、スマホアプリのバックエンドとしてのDjangoのメリットを紹介していました。Djangoの管理サイトは簡単に構築できて、かつ機能も十分なので、APIを中心とするサービスの管理サイトには非常に適していると思いました。

### Djangoのメリット

* 学習コストが低い
* フルスタック
* 管理サイトが秀逸

### アプリケーションの形態

* 管理サイト + API（最低限ここまで）
* 管理サイト + CMS + API（ここまであれば完璧）

次にCMS構築の例を元に、DjangoのORMの紹介および実例を説明しました。実際にDjangoのリレーションで出来る事の紹介、またモデルの継承などについてわかりやすく説明していました。特に一般化リレーションについては、ドキュメントから探すのが難しい内容を解説しており、新しい発見がありました。Django1.7から搭載されるマイグレーション機能にも触れており、今後使用する場合の参考になりそうでした。

![Yuichi Nakazawa氏とKazuhiko Kakita氏](https://farm4.staticflickr.com/3914/15234086931_1b30acf29b_z.jpg)
Yuichi Nakazawa氏とKazuhiko Kakita氏 (c) PyCon JP

### リレーション

* 多対一のリレーション 
* 多対多のリレーション
* エクストラフィールドで多対多のリレーション 
* 一対一のリレーション

### モデルの継承

* 抽象ベースクラス（親は実体を持たない）
* マルチテーブル継承（親も子も実体をもつ）
* プロキシモデル（子は実体を持たない、子は項目追加できない、親のメソッドの拡張に）

### 一般化リレーション

* 色々なモデル親モデルにタグを付けたい場合などに使用する

### マイグレーション
 
* Django1.7から標準に
* syncdbではなく、migrate,createsuperuserを使用する。


次にAPI開発の実装のお話になりました。実際の開発ではサードパーティ製のRESTfulなライブラリではなく、自前でJSONを返す処理を実装したそうです。APIを実装する場合に必要な機能である、POST処理、プッシュ通知、ログイン連携などの方法にふれ、また公開するときの事例を紹介しており非常に参考になるセッションでした。今後私もアプリのバックエンドを実装する機会があるので、是非参考にしたいと思います。

### 実例およびライブラリ

* OrderedDictを使用（JSONのレスポンスに順序を付けるため）
* スマホ側でデータをPOSTして、Djangoのformでバリデーション
* プッシュ通知（[pyapns](https://github.com/samuraisam/pyapns/tree/master), [python-gcm](https://github.com/geeknam/python-gcm))
* 認証（[Python Social Auth](http://psa.matiasaguirre.net))
* 画像ファイル（[botl](https://github.com/boto/boto))
* 公開（Nginx + [uWSGI](http://uwsgi-docs.readthedocs.org/en/latest/index.html)）


## Djangoアプリケーション、パフォーマンスチューニング

次にHiroki KIYOHARA氏によるDjangoアプリケーションのパフォーマンスチューニングのセッションを紹介します。KIYOHARA氏は、業務においても100万ユーザーを超えるサイトの構築、運用経験があり、またDjango本体へも貢献しているそうです。Djangoの勉強会なども開催しており、昨年のPyCon APAC 2013でのトークセッションでも発表を行いました。
このセッションでは主に、Djangoアプリケーションの高速化とパフォーマンス測定ツールについてお話していました。

![Hiroki KIYOHARA氏（１）](https://farm4.staticflickr.com/3844/15050629847_5363e61aa2_z.jpg)
Hiroki KIYOHARA氏（１） (c) PyCon JP

最初にDjangoアプリを高速化するためのポイントとして、次の項目をあげ１つづつ解説を行いました。

* SQLを減らす
* インデックス
* キャッシュ
* アプリケーション外

### SQL

まずはアプリケーションが動作しているときに、色々な情報を可視可するためのツールとしてdjango-debug-toolbarを紹介しました。django-debug-toolbarを使用するとブラウザ上からSQLを含め様々な情報を閲覧する事ができます。実際にアプリケーションを動かしながらSQLを確認する事によって、無駄なSQLを取り除く事が可能になります。次にSQLを減らすための仕組みとして、Djangoのモデルのselect_relatedやprefetch_related、bulk_createdなどのメソッドの紹介をしました。ORMが実行するSQLを知り、それに１つづつ対処していく事が重要であると再認識しました。

* [django-debug-toolbar](https://github.com/django-debug-toolbar/django-debug-toolbar)
* select_related、prefetch_related

次にインデックスについての説明になりました。RDBを相手にしているので、SQLを確認しながら、適切なインデックスを使用する事が重要だと説明しました。またJet Profilerなどのツールの紹介も行いました。

### インデックス

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

次にアプリケーション外でのパフォーマンスを向上させるための施策についての話題となりました。セッションのバックエンドの修正や、静的ファイルの圧縮、DBのマスター、スレーブ構成のためのライブラリの紹介や設定方法について解説しました。実際の事例を元にしたライブラリの紹介だったのでとても参考になりました。

### アプリケーション外

* セッションバックエンド（[django-redis-sessions](https://github.com/martinrusev/django-redis-sessions))
* 静的ファイル圧縮（[django-compressor](https://github.com/django-compressor/django-compressor), [django-asset](https://github.com/miracle2k/django-assets)）
* DBのPrimary/Replica構成（[django-replicated](https://github.com/yandex/django_replicated)）

最後に負荷試験ツールFunkLoadの紹介を行いました。Pythonでシナリオを記述でき、実際にGETやPOSTを行ってパフォーマンスが測定できると説明しました。レポート機能もあり、今後使用してみたいと思いました。

### FunkLoadパフォーマンス測定

* [FunkLoad](http://funkload.nuxeo.org/)
* 負荷試験ツール（Pythonで記述）
* セッション付きのシナリオ
* 静的ファイルの自動取得

![Hiroki KIYOHARA氏（２）](https://farm4.staticflickr.com/3920/15234908786_09c1e988fd_z.jpg)
Hiroki KIYOHARA氏（２） (c) PyCon JP


## Data collection, analysis and optimization with python

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

![Shinji Iwaki氏（１）](https://farm6.staticflickr.com/5581/15295963665_d3531d1ba9_z.jpg)
Shinji Iwaki氏（１） (c) PyCon JP


## Micro Python で組み込み Python

Hirotaka Kawata氏によるMicro Pythonに関するセッションをご紹介します。[Micro Python](http://micropython.org/)はマイコン上で動作する新しいPythonのオープンソースの実装で、PyBoardというボードと共に、KICKSTARTERで投資を集めて開発されていると説明しました。
またMicro Pythonには次のような特徴があり、Raspberry Piやmrubyとの違いなどわかりやすく解説していました。特にmrubyとの思想の違いはとても参考になりました。Micro Pythonは主にマイコンやホビー向けの製品であり、REPLでインタラクティブに操作できるのが大きな特徴のようです。

![Hirotaka Kawata氏](https://farm4.staticflickr.com/3868/15109391118_efe5a0c11e_z.jpg)
Hirotaka Kawata氏 (c) PyCon JP

### Micro Pythonの特徴

* マイコン上でPythonが動く
* Python3互換のPython処理系（マイコン向けに再実装）
* REPLが使える（インタラクティブにマイコンを操作できる）

PyBoardに関しては、KICKSTARTERの購入分は既に発送済みらしく、すぐには入手不可能とのことでしたが、代わりに[STM32F4DISCOVERY](http://akizukidenshi.com/catalog/g/gM-05313/)という秋月電子通称で購入できるボードをカスタマイズする事でMicro Pythonを動作させる事が出来るとの事でした。実際のデモでは、カスタマイズしたボードを利用して、REPLにてLEDを点滅させたり、LCDに文字列を表示させたりしていました。インタラクティブにボードを動かす事ができるのは、とても面白かったです。私もマイコンなどには興味があったので、今後機会があれば挑戦してみたいと思いました。

![講演](https://farm4.staticflickr.com/3850/15109215119_6c964dd3dc_z.jpg)
講演 (c) PyCon JP

## XML-RPC : Pythonが「電池付属」と呼ばれる理由

最後にRansui Iso氏によるPythonのXML-RPCモジュールのセッションをご紹介します。Iso氏は1998年頃からPythonを使っていて、様々な開発を行ってきたそうです。現在はネットの広告配信の仕組みを研究開発しており、最近はCommon Lispで開発をしながら、Pythonもヘビーに使用しているとのことでした。まずは冒頭でRPCに関しての歴史的な紹介と、そもそもRPCとは何かということをわかりやすく説明していました。
そしてPythonでのXML-RPCの特徴について解説を行い、サーバー側、クライアント側の実装について解説を行いました。また設計、実装上のヒントやTipsの紹介を行いました。

![Ransui Iso氏（１）](https://farm4.staticflickr.com/3924/15295647132_5f2dbdfbfc_z.jpg)
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

![セッションの様子](https://farm6.staticflickr.com/5595/15109471407_120ec70621_z.jpg)
セッションの様子 (c) PyCon JP

## 次回予告

第3回ではPyCon JP 2014のカンファレンスのセッション（2日目）の内容をお届けします。