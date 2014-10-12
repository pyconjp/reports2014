# PyCon JP 2014参加レポート（第3回）

PyCon JP 2014参加レポート第3回は、カンファレンス2日目のセッションを中心にお届けします。

## OpenCVのpythonインターフェース入門

はじめにMasaki Hayashi氏によるOpenCVのpythonインターフェース入門のセッションをご紹介します。
Hayashi氏は現在大学院にて機械学習の画像認識の研究をしており、ブログやWebなどでもコンピュータービジョンについて記事を執筆しているとの事でした。（[コンピュータビジョンのセカイ - 今そこにあるミライ](http://news.mynavi.jp/series/computer_vision/menu.html)）

![Masaki Hayashi氏](https://farm4.staticflickr.com/3858/15110598479_2e41c306bb_z.jpg)
Masaki Hayashi氏 (c) PyCon JP

まずは導入部分で、Computer Visionについての説明を行いました。Computer Visionとは次のようなものであることを解説し、またComputer Visionのサンプル動画を紹介してとてもわかりやすく説明していました。

### Computer Visionとは？

* カメラで撮影した画像、動画、デプス（Kinect）などから実世界の様子を計算機で（できれば自動的に）把握する技術分野
* 画像認識、画像処理、3D復元などををひっくるめてComputer Visionと呼ぶ

次にOpenCVの概要ついて次の項目をあげて説明を行いました。OpenCVをPythonから使用する場合の主要モジュールや、応用モジュールについて詳しく解説を行いました。

### OpenCVの概要

* C++言語向けのComputer Vision大規模ライブラリ
* Python、Javaなどのラッパーも標準提供されている
* 画像処理、動画像入出力、顔検出などComputer Visionの基本的な道具がそろっている
* 最新バージョンはOpenCV2.4.9

またC++ではなくPythonを利用するメリットとして、次のような特徴を挙げて解説を行いました。特にインタラクティブに実行して、すぐ結果をみて試せるというのは非常に大きな利点があると感じました。

### PythonでOpenCVを使うメリット

* NumPyやSciPyとの連携
* C++と違ってインタラクティブに、実験的に実行できる（IPythonも使用できる）
* IPython Notebookによる全ての結果のノート保存、共有
* scikit-learn, pandasなどの機会学習、データサイエンス用のライブラリとの相性も良い

次にOpenCVによる画像データにのフォーマットに関する説明になりました。OpenCVで読み込んだ画像データはnumpy配列になると説明しました。numpy配列になると色々なライブラリとの連携も簡単にできるので、メリットが大きいと感じました。
実際のデモでは、基本的な画像処理であるガウシアンブラー（ぼかし）、エッジ検出などの例の紹介、画像認識である背景差分、人検出の使用例について解説しました。OpenCVにはあらかじめ色々な関数が用意されているので、デモで見たような処理は比較的簡単にできる事がわかりました。


## Improving code quality through static analysis for Python

次にDaniel Izquierdo氏によるセッションについて紹介します。Izquierdo氏はベネズエラ出身で現在は日本に住んでおり、スタートアップであるMakeLeapsで働いていると自己紹介を行いました。

![Daniel Izquierdo氏](https://farm6.staticflickr.com/5562/15071449128_1451c74114_z.jpg)
Daniel Izquierdo氏 (c) PyCon JP

まずはなぜstatic analysisが必要なのかについて、次の項目をあげて説明を行いました。static analysisを行う事によって、プログラムを走らせたり、テストするとのは違った問題が発見できると説明しました。
色々な側面からコードを改善する事ができるので、是非機会があれば使用して見たいと思いました。

### Why static analysis?

* Find errors.
* Find security issues.
* Reduce complexity.
* Keep code clean.
* Find bugs.
* Enforce coding style.
* Calculate code metrics.

次にPythonでのstatic analysisのツールについてサンプルを交えながら解説しました。Pylintの使用例を元に実際のコードと、解析結果を提示してわかりやすく説明していました。

### Popular static analysis tools for Python

* [Pylint](https://pypi.python.org/pypi/pylint)
* [Pyflakes](https://pypi.python.org/pypi/pyflakes)
* [pep8](http://legacy.python.org/dev/peps/pep-0008/)（Style Guide for Python Code)
* [pep257](http://legacy.python.org/dev/peps/pep-0257/)(Docstring Conventions)
 
次に実際にプロジェクトへstatic analysisへ組み込む方法について説明を行いました。まずはstatic analysisはたくさんの問題や改善点を指摘してくれるので、プロジェクトに組み込んだ方が良いということを説明しました。また開発に組み込む方法として、エディタと連携して使用したり、CIの仕組みに取り入れたりする方法を紹介しました。
実際にエラーを修正する際には、優先順位をつけていくつかのエラーはignore(無視)して、修正出来るときがきたら修正すれば良いと述べました。エラーの数を少なくしておけば、新たなエラーの検知がしやすく、また対応もしやすいので有効な方法だと思いました。

## データ分析の世界へようこそ！ ～マーケティングに活かせるPythonライブラリ～

次にTakahiro Ikeuchi氏によるデータ分析に関するセッションをご紹介します。まずは冒頭で英語によるLTを行いました。前日行われたKennth氏のキーノートに触れ、積極的にPython3を使っていこうと紹介しました。日本でも似たような事例があるとしてPlayStation3とPlayStation4の事を例に挙げて説明しました。
またこれからセッションで紹介する、NumPy,SciPyなどのライブラリはPython3.4をサポートしているので、是非一緒に学んでいきましょうと説明しました。私も機会があれば、積極的に使用していきたいと思います。

![Takahiro Ikeuchi氏（１）](https://farm4.staticflickr.com/3868/15297539462_f76efc3586_z.jpg)
Takahiro Ikeuchi氏 (c) PyCon JP

LT終了後に、まずは簡単な自己紹介を行いIkeuchi氏はデータ分析やマーケティングを仕事で行っていると説明しました。またマーケティングの定義を簡単に説明し、マーケティングには色々な解釈があることや、マーケティングの事例としてのオバマの選挙を紹介していました。
なぜデータ分析が必要かについては次のような特徴を挙げて説明を行いました。またPythonをデータ分析のツールとして活用する事をお勧めしていました。

### なぜデータ分析か？

* 正しい現状認識
* 再現性のある打ち手
* 施策の客観的な評価

次にマーケティングに活用できる、実際のPythonのライブラリの紹介になりました。まずは標準ライブラリであるitertoolとCollectionsの説明を行いました。permutationsやCounterの使用方法など、コード例を元に解説しました。
またPython3.4から追加されたstatistics moduleを使用することで、平均、中央値、分散など一般的な統計情報が簡単に計算できると説明しました。アソシーエーション分析や、共起頻度、レコメンデーションなどのわかりやすいサンプルを元にライブラリの活用方法を説明しました。

### ライブラリ

* [itertool](https://docs.python.org/3.4/library/itertools.html)
* [Collections](http://docs.python.jp/3.4/library/collections.html)
* [statistics module](https://docs.python.org/3/library/statistics.html)

次に[NumPy](http://www.numpy.org)についての説明となりました。行列についての演算が簡単にできること、また偏差値計算の例を挙げて説明していました。

### NumPyとは

* 高速な行列計算のできる数値計算ライブラリ
* 和、積、スカラー倍、転置行列などが出来る
* pandasなども内部で使用している

次に[pandas](http://pandas.pydata.org)と[SciPy](http://www.scipy.org)の説明になりました。pandasを用いるとデータ操作を簡単に行う事ができ、またデータ入出力のための、I/Oが非常に充実していると話しました。pandasを使用すると基本統計量なども取得する事ができるようです。
SciPyでは距離計算などの説明をして、レーダーチャートやクラスタリングの例を紹介しました。

### pandasとは

* データの操作を容易に行える（read_csv、head/tail、merge、describe)
* 直感的な操作ができる
* 各種データ形式へのI/0を備える（Excelファイルなど）

### SciPyとは

* 高度な科学計算ライブラリ
* 統計、距離計算から幾何学変換など

次に[scikit-learn](http://scikit-learn.org/stable/)についての説明となりました。scikit-learnは機会学習のライブラリであり、マーケティングにおいて適用できる事例の紹介をしました。手法と分析の例を挙げておりとても興味深い内容でした。

### scikit-learnとは

* 機械学習のライブラリ
* 日本語の情報はまだ少なめ

最後にデータの可視可についてのお話となりました。データをビジュアライズする分野は注目度が高く、JavaScriptの[D3.js](http://d3js.org)などが有名であると説明しました。
そしてPythonのライブラリである[matplotlib](http://matplotlib.org)について紹介し、実際にIPython上でデモを行いました。

### matplotlibとは

* ビジュアライズのためのモジュール
* IPythonと組み合わせると便利

## Pythonではじめる野球プログラミング

次にShinichi Nakagawa氏によるPythonではじめる野球プログラミングのセッションをご紹介します。Nakagawa氏は野球のソーシャルゲームをプレイしており、野球ゲームで勝つために、まずは選手とチームの成績を可視可することから始めたとお話しました。

![Shinichi Nakagawa氏（１）](https://farm4.staticflickr.com/3844/15071310480_db21658b09_z.jpg)
Shinichi Nakagawa氏 (c) PyCon JP

まずは元となるデータがどこから取得できるかについて説明を行いました。基本的には公式サイトなどからデータを取得することは難しく、個人で公開している[SeanLahman.com](http://www.seanlahman.com/baseball-archive/statistics/)からMLBデータを取得して活用したとお話しました。
実際に取得できるデータには1871年〜2013年までのMLB選手、および球団のデータが含まれていると説明しました。

その後実際のサービスを開発するに当たっての、サーバー構築方法について解説しました。実際のサーバー構築の際はvagrantやchefを利用したそうです。取得したデータの投入については[sqlacodegen](https://pypi.python.org/pypi/sqlacodegen)からModelコードの自動生成を行い、選手および球団のデータを20〜30個位のテーブルに入れたとのことでした。

### sqlacodegenとは

* DBのスキーマからSQLAlchemyのModelコードを自動生成
* MySQLやPostgreSQLに対応

次にDjangoでのアプリ解説についてのお話となりました。フレームワークにはDjango、テンプレートにはBootstrap、グラフや分布図用のJavaScriptライブラリとしてmorris.js、HIGHCHARTSなどを使用したと説明しました。
JavaScriptライブラリは使用した事が無かったので、今度機会があれば試してみたいと思います。

### アプリの構成

* Python3.4 + Django1.7
* [Bootstrap](http://getbootstrap.com)
* [morris.js](http://morrisjs.github.io/morris.js/)
* [HIGHCHARTS](http://www.highcharts.com/)

次に野球の指標について解説し、実際のデモを交えながら説明していました。次の項目にあげた、BABIPと打率の比較についてイチロー選手の例を紹介し、実際にグラフを見ながら解説をしました。
次にピタゴラス勝率と実際の勝率の相関図を表示し、アスレチックスなどの例を挙げ説明しました。実際の勝率とピタゴラス勝率がとても近い場合があること、またその逆もあるという事は興味深かったです。

### 野球の指標

* BABIP（本塁打を除くグランド内に飛んだ打球が安打になった割合）
* ピタゴラス勝率（得点と失点が等しいときの勝率は5割であるという仮説に基づき生み出された指標、予想勝率を算出する）

最後にオープンデータを使用したデータ解析および可視可について解説しました。オープンなスポーツデータを取得する事は簡単ではなく難しいようです。日本でもオープンデータの活用方法が模索されており、政府の[カタログサイト](http://www.data.go.jp/)なども公開されているので、今後活用していきたいと思いました。

## 次回予告

2日日は全部で15個のセッションが行われ、５つの発表が英語での発表となりました。言語仕様から画像解析、ゲーム開発など２日目も多様な内容の発表がありました。どのセッションも大変盛況で立ち見がでたセッションもありました。
参加者の方も前日よりリラックスして楽しんで頂けているように感じました。他のセッションに関しても次のリンクより資料、動画を閲覧する事ができますので、ぜひご覧頂ければと思います。

* [PYCON JP 2014 発表資料一覧](https://pycon.jp/2014/reports/slides/)

第4回ではPyCon JP 2014のキーノート、セッション以外の内容をまとめてレポートします。