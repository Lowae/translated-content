---
title: Express/Node のイントロダクション
slug: Learn/Server-side/Express_Nodejs/Introduction
tags:
  - Beginner
  - CodingScripting
  - Express
  - Learn
  - Node
  - nodejs
  - server-side
  - サーバーサイド
  - 初心者
translation_of: Learn/Server-side/Express_Nodejs/Introduction
---
<div>{{LearnSidebar}}</div>

<div>{{NextMenu("Learn/Server-side/Express_Nodejs/development_environment", "Learn/Server-side/Express_Nodejs")}}</div>

<p class="summary">Express の最初の記事では ”Node って何だろう？”、”Express って何だろう？”という疑問に答え、なぜ Express ウェブフレームワークが特別なのかについて概要を説明します。主な特徴、Express アプリケーションの主な基本要素(テスト開発環境についてはここではまだ触れません) を大まかに説明します。</p>

<table class="learn-box standard-table">
 <tbody>
  <tr>
   <th scope="row">前提条件</th>
   <td>基本的なコンピューターリテラシー。<a href="/ja/docs/Learn/Server-side/First_steps">サーバーサイドのウェブサイトプログラミング</a>の一般的な理解、特に<a href="/ja/docs/Learn/Server-side/First_steps/Client-Server_overview">ウェブサイトにおけるクライアントとサーバーのやりとり</a>の仕組み。</td>
  </tr>
  <tr>
   <th scope="row">目標</th>
   <td>Express の特徴、Node との適合性、提供する機能、Express アプリケーションの主要な基本要素に慣れてください。</td>
  </tr>
 </tbody>
</table>

<h2 id="Node_の紹介"><span class="short_text" id="result_box" lang="ja"><span>Node の紹介</span></span></h2>

<p><a href="https://nodejs.org/">Node</a><span class="short_text" id="result_box" lang="ja"><span> (正式には Node.js) </span></span><span id="result_box" lang="ja"><span>はオープンソースのクロスプラットフォーム、実行環境で、開発者はあらゆるサーバーサイドのツールやアプリケーションを <a href="/ja/docs/Glossary/JavaScript">JavaScript</a> で作成することができます。この実行環境はブラウザーコンテキスト外での使用 (すなわち、コンピューターまたはサーバー OS 上での直接実行) を目的としています。そのため、クライアントサイドではブラウザー固有の JavaScript API が省略され、HTTP やファイルシステムライブラリを含む従来の OS API がサポートされます</span></span><span lang="ja"><span>。</span></span></p>

<p>ウェブサーバー開発の観点から Node には多くの利点があります。</p>

<ul>
 <li>素晴らしいパフォーマンス！ Node はウェブアプリケーションのスループットとスケーラビリティを最適化するように設計されており、多くの一般的なウェブ開発の問題 (リアルタイムウェブアプリケーションなど) に非常に適しています</li>
 <li>コードは "plain old JavaScript" で書かれています。つまり、ブラウザーとウェブサーバーの両方のコードを記述しているときに、言語間の "コンテキストシフト" に費やす時間が短くなります</li>
 <li>JavaScript は比較的新しいプログラミング言語であり、他の従来の ウェブサーバー言語 (Python、PHPなど) と比較して言語設計の改善のメリットがあります。CoffeeScript、ClosureScript、Scala、LiveScript などを使用できるように、新しく普及している多くの言語が JavaScript にコンパイル/変換されます。</li>
 <li>Node パッケージマネージャー (NPM) は、何十万もの再利用可能なパッケージへのアクセスを提供します。クラス最高の依存関係解決機能もあり、ほとんどのビルドツールチェーンの自動化にも使用できます。</li>
 <li>Node.js は移植可能です。Microsoft Windows、macOS、Linux、Solaris、FreeBSD、OpenBSD、WebOS、および NonStop OS で利用できます。さらに、多くの ウェブホスティングプロバイダが、Node サイトをホスティングするための特定のインフラストラクチャとドキュメントが提供しています。</li>
 <li>非常に活発な第三者のエコシステムと開発者コミュニティがあり、多くの方々が 快く協力しています。</li>
</ul>

<p>Node HTTP パッケージを使用することで、Node.js で簡単な ウェブサーバーを作成できます。</p>

<h3 id="Hello_Node.js">Hello Node.js</h3>

<p>次の例では、URL <code>http://127.0.0.1:8000/</code> にあるあらゆる種類の HTTP リクエストを待ち受ける ウェブサーバーを作成します。リクエストが受信されると、スクリプトは "Hello World" という文字列でレスポンスします。すでに Node をインストールしている場合は、次の手順に従ってこの例を試すことができます。</p>

<ol>
 <li>ターミナルを開きます (Windows ではコマンドラインユーティリティを開きます)。</li>
 <li>プログラムを保存するフォルダ (たとえば "test-node") を作成し、端末に次のコマンドを入力して移動します。</li>
</ol>

<pre class="line-numbers  language-html"><code class="language-html">cd test-node</code></pre>

<ol start="3">
 <li>好きなテキストエディタを使って "hello.js" というファイルを作成し、次のコードを貼り付けます。</li>
</ol>

<pre class="brush: js">// HTTPモジュールの読み込み
var http = require("http");

//  <span id="result_box" lang="ja"><span>HTTPサーバーを作成し、ポート8000でリクエスト</span></span>を行う
http.createServer(function(request, response) {

   // HTTP ステータスとコンテントタイプを持つ HTTP ヘッダのレスポンスを設定
   response.writeHead(200, {'Content-Type': 'text/plain'});

   // レスポンスボディー"Hello World"を送信
   response.end('Hello World\n');
}).listen(8000);

//  <span class="short_text" id="result_box" lang="ja"><span>サーバーにアクセスするための URL を出力</span></span>
console.log('Server running at http://127.0.0.1:8000/');</pre>

<ol start="4">
 <li>上記で作成したフォルダにファイルを保存します。</li>
 <li>ターミナルに戻り、次のコマンドを入力します。</li>
</ol>

<pre class="brush: bash line-numbers  language-bash"><code class="language-bash">node "hello.js"</code></pre>

<p>最後に、ウェブブラウザーで <code>"http://localhost:8000"</code> に移動します。テキスト以外は空の ウェブページの左上に "Hello World" というテキストが表示されます。</p>

<h2 id="ウェブフレームワーク">ウェブフレームワーク</h2>

<p>その他の一般的なウェブ開発タスクは、Node 自体では直接サポートされていません。異なる HTTP 動詞 (<code>GET</code>, <code>POST</code>, <code>DELETE</code> など) に特定の処理を追加したい場合、別々の URL パス ("routes") でリクエストを個別に処理したり、静的ファイルを提供したり、テンプレートを使用してレスポンスを動的に作成したり、あなた自身でコードを書く必要があります。そうしない場合はウェブフレームワークを使用して、車輪の再発明を避けることができます。</p>

<h2 id="Express_のイントロダクション">Express のイントロダクション</h2>

<p><a href="https://expressjs.com/ja/">Express</a> は最も一般的な Node ウェブフレームワークであり、他の多くの一般的な <a href="https://expressjs.com/en/resources/frameworks.html">Node ウェブフレームワーク</a>の基礎となるライブラリです。それは以下のメカニズムを提供します：</p>

<ul>
 <li>異なる URL のパス (ルート) で異なる HTTP 動詞を使用してリクエストのハンドラを作成します。</li>
 <li>テンプレートにデータを挿入してレスポンスを生成するために、「ビュー」レンダリングエンジンと統合します。</li>
 <li>接続に使用するポートやレスポンスのレンダリングに使用されるテンプレートの場所などの一般的なウェブアプリケーション設定値を設定します。</li>
 <li>リクエスト処理パイプライン内の任意の時点で、追加のリクエスト処理「ミドルウェア」を追加します。</li>
</ul>

<p>Express 自体はかなりシンプルですが、開発者はほぼすべてのウェブ開発問題に対応する互換性のあるミドルウェアパッケージを作成しています。Cookie、セッション、ユーザーログイン、URL パラメータ、POST データ、セキュリティヘッダーなどを扱うライブラリがあります。Express チームが管理するミドルウェア・パッケージのリストは、<a href="http://expressjs.com/en/resources/middleware.html">Express Middleware</a> (一般的なサード・パーティ・パッケージのリストとともに) にあります。</p>

<div class="note">
<p><strong>注:</strong> この柔軟性は両刃の剣です。ほぼすべての問題や要件に対応するミドルウェアパッケージがありますが、適切なパッケージを使用して作業することは時には挑戦になることがあります。アプリケーションを構造化する「正しい方法」もなく、インターネット上で見つかる多くの例は最適ではないし、ウェブアプリケーションを開発するために必要なことのほんの一部を示しているだけです。</p>
</div>

<h2 id="Node_と_Express_はどこから来たのですか？">Node と Express はどこから来たのですか？</h2>

<p>Node は 2009 年に Linux 用に最初にリリースされました。NPM パッケージマネージャは 2010 年にリリースされ、ネイティブ Windows サポートは 2012 年に追加されました。現在の LTS リリースは Node v10.13.0 で、最新のリリースは Node 11.2.0 です。これは、豊かな歴史の小さなスナップショットです。もっと知りたいのであれば、<a href="https://en.wikipedia.org/wiki/Node.js#History">Wikipedia</a> を掘り下げてみてください。</p>

<p>Express は 2010 年 11 月に最初にリリースされ、現在 API のバージョンが 4.16.3 になっています。現在のリリースの変更点については<a href="https://expressjs.com/en/changelog/4x.html">更新履歴</a>を、詳細な履歴リリースノートについては <a href="https://github.com/expressjs/express/blob/master/History.md">GitHub</a> を参照してください。</p>

<h2 id="Node_と_Express_はどれくらい普及していますか？">Node と Express はどれくらい普及していますか？</h2>

<p>ウェブフレームワークの普及は、それが維持されるかどうかの指標であり、ドキュメンテーション、アドオンライブラリ、テクニカルサポートの面でどのようなリソースが利用される可能性が高いかという点で重要です。</p>

<p>サーバー側のフレームワークの普及率 (<a href="http://hotframeworks.com/">Hot Frameworks</a> のようなサイトでは、GitHub プロジェクトの数や各プラットフォームの StackOverflow の質問数などの仕組みを使って人気を評価しようとしています) は、すぐに利用可能で決定的なものではありません。より良い質問は、人気のないプラットフォームの問題を避けるために Node と Express が「人気がある」かどうかです。それらは進化し続けていますか？あなたがそれを必要としたら助けを得ることができますか？あなたが Express を学ぶならば、あなたは職を得る機会がありますか？</p>

<p>Express を使用している<a href="https://expressjs.com/en/resources/companies-using-express.html">有名企業</a>の数、コードベースに貢献している人の数、および無料と有料の両方でサポートを提供している人の数に基づけば、Express は一般的なフレームワークです。</p>

<h2 id="Expressは指図をしたがりますか？">Expressは指図をしたがりますか？</h2>

<p>ウェブフレームワークはしばしば自身を「指図をしたがる」または「指図をしない」ものと称します。</p>

<p>指図をしたがるフレームワークは、特定のタスクを扱うのに「正しい方法」があるという考えを持っています。何であれ正しい方法であれば普通よく理解され細かく文書化されているため、（特定のタイプの問題を解決するような）特定の領域における素早い開発をサポートします。しかしながら、彼らが主眼とする領域の外にある問題を解決するにあたっては柔軟性に劣り、利用できるコンポーネントやアプローチの選択肢が限られたものになりがちです。</p>

<p>一方、指図をしないフレームワークは、目的の達成のためにコンポーネントをつなぎ合わせる最善の方法や、どのコンポーネントを使うかにさえも、あまり制約を設けません。<br>
 開発者は、コンポーネントを自分自身で探す必要があるという手間をかければ、特定のタスクを完了させるのに最適なツールの利用をより容易にします。</p>

<p>Express は指図をしません。リクエストを処理するチェインの中で、互換性のある好きなミドルウェアを、好きな順番で挿し込むことができます。1 つのファイルまたは複数のファイル、任意のディレクトリ構造を使ってアプリケーションを構成できます。<br>
 ときに選択肢が多すぎるようにも感じられるでしょう！</p>

<h2 id="Expressコードはどのように見えますか？">Expressコードはどのように見えますか？</h2>

<p>従来のデータ駆動型ウェブサイトでは、ウェブアプリケーションはウェブブラウザー (または他のクライアント) からの HTTP リクエストを待機します。リクエストが受信されると、アプリケーションは URL パターンと、<code>POST</code> データまたは <code>GET</code> データに含まれる可能性のある関連情報に基づいて、必要なアクションを実行します。必要に応じて、データベースから情報を読み書きしたり、リクエストを満たすために必要な他のタスクを実行することができます。アプリケーションはウェブブラウザーにレスポンスを返し、検索されたデータを HTML テンプレートのプレースホルダに挿入することによってブラウザーが表示する HTML ページを動的に作成することがよくあります。</p>

<p>Express は特定の HTTP 動詞 (<code>GET</code>, <code>POST</code>, <code>SET</code> など) と URL パターン ("Route") に対してどの関数が呼び出されるかを指定するメソッドと、どのテンプレート ("view") エンジンが使用されるかを指定するメソッドを提供します。テンプレートエンジンを使用するには、レスポンスをレンダリングするためのテンプレートファイルを配置します。Express ミドルウェアを使用して、Cookie、セッション、およびユーザー、<code>POST</code>/<code>GET</code> パラメーターなどのサポートを追加することができます。Node がサポートするデータベース・メカニズムを使用できます (Express はデータベース関連の動作を定義しません)。</p>

<p>次のセクションでは、Express およびノー​​ド・コードを使用して作業するときに表示される一般的な事項について説明します。</p>

<h3 id="Helloworld_Express">Helloworld Express</h3>

<p>最初に、標準の Express の <a href="https://expressjs.com/ja/starter/hello-world.html">Hello World</a> の例を考えてみましょう (これについては、以下の各セクションで説明します)。</p>

<div class="note">
<p><strong>Tip:</strong> Node と Express がすでにインストールされている場合 (または<a href="/ja/docs/Learn/Server-side/Express_Nodejs/development_environment">次の記事</a>のようにインストールする場合) は、このコードを <strong>app.js</strong> というテキストファイルに保存し、bash コマンドプロンプトで次のように呼び出して実行できます。</p>

<p><strong><code>node ./app.js</code></strong></p>
</div>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> express <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'express'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> app <span class="operator token">=</span> <span class="function token">express</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

app<span class="punctuation token">.</span><span class="keyword token">get</span><span class="punctuation token">(</span><span class="string token">'/'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  res<span class="punctuation token">.</span><span class="function token">send</span><span class="punctuation token">(</span><span class="string token">'Hello World!'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

app<span class="punctuation token">.</span><span class="function token">listen</span><span class="punctuation token">(</span><span class="number token">3000</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'Example app listening on port 3000!'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>最初の2行は <code>require()</code> で express モジュールをインポートして <a href="https://expressjs.com/ja/4x/api.html#app">Express アプリケーション</a>を作成します。このオブジェクトは伝統的に <code>app</code> と呼ばれ、HTTP リクエストのルーティング、ミドルウェアの設定、HTML ビューのレンダリング、テンプレートエンジンの登録、アプリケーションの動作を制御する<a href="https://expressjs.com/ja/4x/api.html#app.settings.table">アプリケーション設定</a>の変更 (環境モード、ルート定義の大文字と小文字の区別など) のためのメソッドがあります。</p>

<p>コードの中央部分 (<code>app.get</code> で始まる3行) はルート定義を示しています。<code>app.get()</code> メソッドは、サイトルートからの相対パス (<code>'/'</code>) を持つ HTTP <code>GET</code> リクエストがあるたびに呼び出されるコールバック関数を指定します。コールバック関数はリクエストとレスポンスオブジェクトを引数として取り、レスポンスに対して単に <code><a href="https://expressjs.com/ja/4x/api.html#res.send">send()</a></code> を呼び出して文字列 "Hello World!" を返します。</p>

<p>最後のブロックは3000番ポートでサーバーを起動し、コンソールにログコメントを出力します。 サーバーが稼働している場合は、ブラウザーの <code>localhost:3000</code> にアクセスして、レスポンスの例を確認することができます。</p>

<h3 id="モジュールのインポートと作成">モジュールのインポートと作成</h3>

<p>モジュールは Node の <code>require()</code> 関数を使って他のコードにインポートできる JavaScript ライブラリ/ファイルです。 Express 自体はモジュールです。Express アプリケーションで使用するミドルウェアおよびデータベースライブラリも同様です。</p>

<p>以下のコードは、例として Express フレームワークを使用して、モジュールを名前でインポートする方法を示しています。 最初に <code style="font-style: normal; font-weight: normal;">require()</code> 関数を呼び出し、モジュールの名前を文字列 (<code>'express'</code>) として指定し、返されたオブジェクトを呼び出して <a href="https://expressjs.com/ja/4x/api.html#app.settings.table">Express アプリケーション</a>を作成します。その後、アプリケーションオブジェクトのプロパティと機能にアクセスできます。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> express <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'express'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> app <span class="operator token">=</span> <span class="function token">express</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>独自のモジュールを作成して、同じ方法でインポートすることもできます。</p>

<div class="note">
<p><strong>メモ:</strong> あなたは自身のモジュールを作成したいと思うでしょう、これはあなたが自身のコードを管理しやすい部品に分けることを可能にします 。ちなみに、モノリシックな単一ファイルのアプリケーションは理解し維持するのが難しいです。モジュールを使用すると、明示的にエクスポートした変数のみがインポートされるため、モジュールを使用すると名前空間を管理するのにも役立ちます。</p>
</div>

<p>オブジェクトをモジュールの外部で利用可能にするには、それらを <code>exports</code> オブジェクトの追加プロパティとして公開するだけです。たとえば、以下の <strong>square.js</strong> モジュールは <code>area()</code> メソッドと <code>perimeter()</code> メソッドをエクスポートしたファイルです。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">exports<span class="punctuation token">.</span>area <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span>width<span class="punctuation token">)</span> <span class="punctuation token">{</span> <span class="keyword token">return</span> width <span class="operator token">*</span> width<span class="punctuation token">;</span> <span class="punctuation token">}</span><span class="punctuation token">;</span>
exports<span class="punctuation token">.</span>perimeter <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span>width<span class="punctuation token">)</span> <span class="punctuation token">{</span> <span class="keyword token">return</span> <span class="number token">4</span> <span class="operator token">*</span> width<span class="punctuation token">;</span> <span class="punctuation token">}</span><span class="punctuation token">;</span></code></pre>

<p><code>require()</code> を使ってこのモジュールをインポートし、次に示すようにエクスポートされたメソッドを呼び出すことができます。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> square <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'./square'</span><span class="punctuation token">)</span><span class="punctuation token">;</span> <span class="comment token">//  require() にはファイル拡張子を除いたファイル名を引数に指定します。</span>
console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'The area of a square with a width of 4 is '</span> <span class="operator token">+</span> square<span class="punctuation token">.</span><span class="function token">area</span><span class="punctuation token">(</span><span class="number token">4</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<div class="note">
<p><strong>メモ:</strong> モジュールへの絶対パス (または最初に行ったように名前) を指定することもできます。</p>
</div>

<p>一度に1つのプロパティを構築するのではなく、1つの割り当てで完全なオブジェクトをエクスポートする場合は、次のように <code>module.exports</code> に割り当てます (これを実行して、エクスポートオブジェクトのルートをコンストラクタまたは他の関数にすることもできます)。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">module<span class="punctuation token">.</span>exports <span class="operator token">=</span> <span class="punctuation token">{</span>
  area<span class="punctuation token">:</span> <span class="keyword token">function</span><span class="punctuation token">(</span>width<span class="punctuation token">)</span> <span class="punctuation token">{</span>
    <span class="keyword token">return</span> width <span class="operator token">*</span> width<span class="punctuation token">;</span>
  <span class="punctuation token">}</span><span class="punctuation token">,</span>

  perimeter<span class="punctuation token">:</span> <span class="keyword token">function</span><span class="punctuation token">(</span>width<span class="punctuation token">)</span> <span class="punctuation token">{</span>
    <span class="keyword token">return</span> <span class="number token">4</span> <span class="operator token">*</span> width<span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span></code></pre>

<div class="note">
<p><strong>Note:</strong> あなたは <code>exports</code> を与えられたモジュール内の <code>module.exports</code> への<a href="https://nodejs.org/api/modules.html#modules_exports_shortcut">ショートカット</a>として考えることができます。実際、<code>exports</code> は、モジュールが評価される前に <code>module.exports</code> の値に初期化される単なる変数です。 その値はオブジェクト (この場合は空のオブジェクト) への参照です。これは、<code>exports</code> が <code>module.exports</code> によって参照されるのと同じオブジェクトへの参照を保持することを意味します。また、エクスポートに別の値を代入することで、<code>module.exports</code> にバインドされなくなることも意味します。</p>
</div>

<p>モジュールの詳細については、<a href="https://nodejs.org/api/modules.html#modules_modules">モジュール</a> (Node API のドキュメント) を参照してください。</p>

<h3 id="非同期_API_の使用">非同期 API の使用</h3>

<p>JavaScriptコードでは、操作に同期APIよりも非同期APIが頻繁に使用されるため、処理に時間がかかることがあります。 同期APIは、各操作を完了してから次の操作を開始できるAPIです。 たとえば、次のログ関数は同期的で、テキストをコンソールに順番に印刷します(First、Second)。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'First'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'Second'</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>対照的に、非同期 API は、API が操作を開始してすぐに (操作が完了する前に) 戻るものです。操作が終了すると、API は何かのメカニズムを使用して追加の実行を行います。例えば、次のコードでは最初に <code>setTimeout()</code> メソッドが呼び出されてすぐに返されても、操作が数秒間完了しないため、 "Second, First" が出力されます。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="function token">setTimeout</span><span class="punctuation token">(</span><span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
   console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'First'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
   <span class="punctuation token">}</span><span class="punctuation token">,</span> <span class="number token">3000</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'Second'</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>Node はシングルスレッドのイベント駆動型実行環境であるため、ノンブロッキングの非同期 API を使用することは、ブラウザーよりも Node にとってさらに重要です。シングルスレッドとは、サーバーへのすべてのリクエストが (別々のプロセスに分割されるのではなく) 同じスレッドで実行されることを意味します。このモデルは速度とサーバーリソースの点で非常に効率的です。しかし、完了に時間がかかる同期メソッドを呼び出す関数があると、それらは現在のリクエストだけでなく、他のすべてのリクエストがウェブアプリケーションによって処理されることをブロックします。</p>

<p>非同期 API がアプリケーションに完了したことを通知するにはいくつかの方法があります。最も一般的な方法は、非同期 API を呼び出すときにコールバック関数を登録することです。これは、操作が完了したときにコールバックされます。 これが上記で使用されているアプローチです。</p>

<div class="note">
<p><strong>Tip:</strong> コールバックを使用することは、順番に実行しなければならない一連の従属非同期操作がある場合、かなり "面倒" になる可能性があります。これは、複数レベルのネストされたコールバックをもたらすためです。この問題は一般に「コールバック地獄」として知られています。この問題は、優れたコーディング方法 ( <a href="http://callbackhell.com/">http://callbackhell.com/</a> を参照)、<a href="https://www.npmjs.com/package/async">async</a> などのモジュールの使用、または <a href="/ja/docs/Web/JavaScript/Reference/Global_Objects/Promise">Promise</a> などの ES6 機能への移行によっても軽減できます。</p>
</div>

<div class="note">
<p><strong>メモ:</strong> Node と Express の一般的な規約は、エラー優先コールバックを使うことです。この規約では、コールバック関数の最初の値はエラー値ですが、後続の引数には成功データが含まれます。 なぜこのアプローチがこのブログで役に立つのかについての良い説明があります：<a href="http://fredkschott.com/post/2014/03/understanding-error-first-callbacks-in-node-js">Node.jsの方法 - エラーファーストコールバックについて</a> (fredkschott.com)。</p>
</div>

<h3 id="ルートハンドラの作成">ルートハンドラの作成</h3>

<p>上記の Hello World Express の例では、サイトルート (<code>'/'</code>) への HTTP <code>GET</code> リクエストに対して(callback)ルートハンドラ関数を定義しました。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="keyword token">get</span><span class="punctuation token">(</span><span class="string token">'/'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  res<span class="punctuation token">.</span><span class="function token">send</span><span class="punctuation token">(</span><span class="string token">'Hello World!'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>コールバック関数はリクエストとレスポンスオブジェクトを引数として取ります。 この場合、メソッドは単にレスポンスに対して <code><a href="https://expressjs.com/en/4x/api.html#res.send">send()</a></code> を呼び出して、文字列 "Hello World!" を返します。リクエスト/レスポンスサイクルを終了するための<a href="https://expressjs.com/ja/guide/routing.html#response-methods">レスポンスメソッドは他にも多数</a>あります。たとえば、JSONレスポンスを送信するために <code><a href="https://expressjs.com/en/4x/api.html#res.json">res.json()</a></code> を呼び出し、ファイルを送信するために <code><a href="https://expressjs.com/en/4x/api.html#res.sendFile">res.sendFile()</a></code> を呼び出すことができます。</p>

<div class="note">
<p><strong>JavaScript tip:</strong> コールバック関数で好きな引数名を使うことができます。 コールバックが呼び出されると、最初の引数は常にリクエストになり、2番目の引数は常にレスポンスになります。 コールバックの本体で作業しているオブジェクトを識別できるようにそれらの名前を付けることは意味があります。</p>
</div>

<p>Express アプリケーションオブジェクトには、他のすべての HTTP 動詞のルートハンドラを定義するためのメソッドもあります。これらのメソッドはほとんど同じ方法で使用されます。</p>

<p><code>checkout()</code>, <code>copy()</code>, <strong><code>delete()</code></strong>, <strong><code>get()</code></strong>, <code>head()</code>, <code>lock()</code>, <code>merge()</code>, <code>mkactivity()</code>, <code>mkcol()</code>, <code>move()</code>, <code>m-search()</code>, <code>notify()</code>, <code>options()</code>, <code>patch()</code>, <strong><code>post()</code></strong>, <code>purge()</code>, <strong><code>put()</code></strong>, <code>report()</code>, <code>search()</code>, <code>subscribe()</code>, <code>trace()</code>, <code>unlock()</code>, <code>unsubscribe()</code>.</p>

<p><code>app.all()</code> という特別なルーティングメソッドがあります。これはあらゆる HTTP メソッドにレスポンスして呼び出されます。これはすべてのリクエストメソッドの特定のパスにミドルウェア機能をロードするために使用されます。次の例　(Express の資料から) は、使用される HTTP 動詞に関係なく、 <code>/secret</code> へのリクエストに対して実行されるハンドラを示しています(<a href="https://nodejs.org/api/http.html#http_http_methods">http モジュール</a>でサポートされている場合)。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="function token">all</span><span class="punctuation token">(</span><span class="string token">'/secret'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">,</span> next<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span><span class="string token">'Accessing the secret section ...'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="function token">next</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span> <span class="comment token">// 次のハンドラに制御を渡します。</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>ルートを使用すると、URL 内の特定のパターンの文字を照合し、URL からいくつかの値を抽出し、それらをパラメータとしてルートハンドラに渡すことができます(パラメータとして渡されるリクエストオブジェクトの属性として)。</p>

<p>多くの場合、サイトの特定の部分のルートハンドラをまとめて、共通のルートプレフィックスを使用してそれらにアクセスすると便利です (たとえば、Wiki のあるサイトでは、1つのファイルにすべての Wiki 関連ルートがあり、ルートプレフィックス <em>/wiki/</em> を使用してアクセスすることがあります)。 Expressでは、これは <code><a href="http://expressjs.com/ja/guide/routing.html#express-router">express.Router</a></code> オブジェクトを使用して実現されます。たとえば、<strong>wiki.js</strong> という名前のモジュールで Wiki ルートを作成してから、次に示すように <code>Router</code> オブジェクトをエクスポートできます。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="comment token">// wiki.js - Wiki ルートモジュール</span>

<span class="keyword token">var</span> express <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'express'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> router <span class="operator token">=</span> express<span class="punctuation token">.</span><span class="function token">Router</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// ホームページルート</span>
router<span class="punctuation token">.</span><span class="keyword token">get</span><span class="punctuation token">(</span><span class="string token">'/'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  res<span class="punctuation token">.</span><span class="function token">send</span><span class="punctuation token">(</span><span class="string token">'Wiki home page'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// about ページルート</span>
router<span class="punctuation token">.</span><span class="keyword token">get</span><span class="punctuation token">(</span><span class="string token">'/about'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  res<span class="punctuation token">.</span><span class="function token">send</span><span class="punctuation token">(</span><span class="string token">'About this wiki'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

module<span class="punctuation token">.</span>exports <span class="operator token">=</span> router<span class="punctuation token">;</span></code></pre>

<div class="note">
<p><strong>メモ:</strong> <code>Router</code> オブジェクトにルートを追加することは、(前述のように) <code>app</code> オブジェクトにルートを追加するのと同じです。</p>
</div>

<p>メインアプリケーションファイルでルーターを使用するには、ルートモジュール (<strong>wiki.js</strong>) を <code>require()</code> してから、Express アプリケーションで <code>use()</code> を呼び出してミドルウェア処理パスにルーターを追加します。 2つの経路は <code style="font-style: normal; font-weight: normal;">/wiki/</code> と <code style="font-style: normal; font-weight: normal;">/wiki/about/</code> からアクセス可能になります。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> wiki <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'./wiki.js'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="comment token">// ...</span>
app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span><span class="string token">'/wiki'</span><span class="punctuation token">,</span> wiki<span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>ルートを扱うことについて、そして特に <code>Router</code> を使うことについてもっとより多くのことがあります。それらについては、リンクされたセクション、<a href="/ja/docs/Learn/Server-side/Express_Nodejs/routes">ルートとコントローラ</a>で説明します。</p>

<h3 id="ミドルウェアの使用">ミドルウェアの使用</h3>

<p>ミドルウェアは静的ファイルの提供からエラー処理、HTTP レスポンスの圧縮まで、Express アプリケーションで広く使用されています。ルート関数は HTTP クライアントにレスポンスを返すことで HTTP リクエスト - レスポンスサイクルを終了しますが、ミドルウェア関数は通常、リクエストまたはレスポンスに対して何らかの操作を実行してから、「スタック」内の次の機能を呼び出します。これは、より多くのミドルウェアまたはルートハンドラの場合があります。ミドルウェアが呼び出される順序はアプリ開発者次第です。</p>

<div class="note">
<p><strong>Note:</strong> ミドルウェアは任意の操作を実行し、任意のコードを実行し、リクエストおよびレスポンスオブジェクトに変更を加えることができ、またリクエスト - レスポンスサイクルを終了することもできます。サイクルが終了しない場合は、<code>next()</code> を呼び出して次のミドルウェア機能に制御を渡す必要があります (そうでない場合、リクエストは中断されたままになります)。</p>
</div>

<p>Cookie の操作、セッション、ユーザ認証、リクエスト <code>POST</code> および JSON データへのアクセス、ロギングなどの一般的なウェブ開発タスクを簡素化するために、ほとんどのアプリはサードパーティ製ミドルウェアを使用します。<a href="http://expressjs.com/ja/resources/middleware.html">Express チームが管理するミドルウェアパッケージのリスト</a>を見つけることができます。(他の人気のあるサードパーティのパッケージも含みます)。他の Express パッケージは NPM パッケージマネージャーで入手できます。</p>

<p>サードパーティのミドルウェアを使用するには、まず NPM を使用してそれをアプリにインストールする必要があります。たとえば、 <a href="http://expressjs.com/en/resources/middleware/morgan.html">morgan</a> という HTTP リクエストロガーミドルウェアをインストールするには、次のようにします。</p>

<pre class="brush: bash"><code>$ npm install morgan
</code></pre>

<p>次に、Express アプリケーションオブジェクトで <code>use()</code> を呼び出してミドルウェアをスタックに追加できます。</p>

<pre class="brush: js">var express = require('express');
<strong>var logger = require('morgan');</strong>
var app = express();
<strong>app.use(logger('dev'));</strong>
...</pre>

<div class="note">
<p><strong>メモ:</strong> ミドルウェアおよびルーティング機能は、宣言されている順序で呼び出されます。ミドルウェアによっては、順序が重要です (たとえば、セッションミドルウェアが cookie ミドルウェアに依存している場合は、最初に cookie ハンドラを追加する必要があります)。ほとんどの場合、ミドルウェアはルートを設定する前に呼び出されます。そうでないとルートハンドラがミドルウェアによって追加された機能にアクセスすることはできません。</p>
</div>

<p>あなたは自身のミドルウェア機能を書くことができ、そうする必要があるでしょう (エラー処理コードを作成するためだけの場合)。ミドルウェア関数とルートハンドラコールバックの<strong>唯一の</strong>違いは、ミドルウェア関数が次に <code>next</code> 引数を持つことです。ミドルウェア関数はリクエストサイクルを完了させるものではない場合に呼び出されます (ミドルウェア関数が呼び出されるとき、その中には呼び出される next 関数が含まれていなければなりません)。</p>

<p>ミドルウェアをすべてのレスポンスに適用するのか、特定の HTTP 動詞を含むレスポンス (<code>GET</code>、<code>POST</code> など) に適用するのかに応じて、 <code>app.use()</code> または <code>app.add()</code> のいずれかを使用してミドルウェア機能を処理チェーンに追加できます)。 <code>app.use()</code> を呼び出すときの経路はオプションですが、どちらの場合も同じ経路を指定します。</p>

<p>以下の例は、ルートの有無に関わらず、両方の方法を使用してミドルウェア関数を追加する方法を示しています。</p>

<pre class="brush: js">var express = require('express');
var app = express();

// ミドルウェア関数の例
var a_middleware_function = function(req, res, <em>next</em>) {
  // ... perform some operations
  next(); // next() を呼ぶことで Express はチェイン中の次のミドルウェア関数を呼びます。

// すべてのルートと動詞に対して use() で関数を追加します。
app.use(a_middleware_function);

// 指定ルートに対して use() でミドルウェア関数を追加します。
app.use('/someroute', a_middleware_function);

// 指定の HTTP 動詞とルートに対してミドルウェア関数を追加します。
app.get('/', a_middleware_function);

app.listen(3000);</pre>

<div class="note">
<p><strong>JavaScript Tip:</strong> 上記ではミドルウェア関数を別々に宣言してからコールバックとして設定しています。以前のルートハンドラ関数では、使用時にコールバック関数を宣言しました。JavaScript では、どちらの方法も有効です。</p>
</div>

<p>Express の資料には、Express ミドルウェアの<a href="https://expressjs.com/ja/guide/using-middleware.html">使用</a>および<a href="http://expressjs.com/ja/guide/writing-middleware.html">作成</a>に関するより優れた資料があります。</p>

<h3 id="静的ファイルの提供">静的ファイルの提供</h3>

<p><a href="http://expressjs.com/ja/4x/api.html#express.static">express.static</a> ミドルウェアを使用して、画像、CSS、JavaScript などの静的ファイルを提供できます (<code>static()</code> は、実際には Express の<strong>一部</strong>である唯一のミドルウェア関数です)。 たとえば、node を呼び出す場所と同じレベルで、'<strong>public</strong>' という名前のディレクトリーから画像、CSS ファイル、および JavaScript ファイルを配信するには、次の行を使用します。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span>express<span class="punctuation token">.</span><span class="keyword token">static</span><span class="punctuation token">(</span><span class="string token">'public'</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>public ディレクトリー内のファイルはすべて、ベース URL にそのファイル名 (ベースの "public" ディレクトリーに対する相対パス) を追加することによって提供されます。そのため、例えば：</p>

<pre><code>http://localhost:3000/images/dog.jpg
http://localhost:3000/css/style.css
http://localhost:3000/js/app.js
http://localhost:3000/about.html
</code></pre>

<p><code>static()</code> を複数回呼び出して、複数のディレクトリーを扱うことができます。ファイルが1つのミドルウェア関数で見つからない場合は、そのファイルは後続のミドルウェアに単純に渡されます (ミドルウェアが呼び出される順序は宣言の順序に基づいています)。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span>express<span class="punctuation token">.</span><span class="keyword token">static</span><span class="punctuation token">(</span><span class="string token">'public'</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span>express<span class="punctuation token">.</span><span class="keyword token">static</span><span class="punctuation token">(</span><span class="string token">'media'</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>ファイルをベース URL に追加するのではなく、静的 URL の仮想プレフィックスを作成することもできます。たとえば、ここではファイルがプレフィックス "/media" でロードされるように<a href="http://expressjs.com/ja/4x/api.html#app.use">マウントパスを指定</a>します。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span><span class="string token">'/media'</span><span class="punctuation token">,</span> express<span class="punctuation token">.</span><span class="keyword token">static</span><span class="punctuation token">(</span><span class="string token">'public'</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>これで、<code>public</code> ディレクトリーにあるファイルを <code>/media</code> パスプレフィックスから読み込むことができます。</p>

<pre><code>http://localhost:3000/media/images/dog.jpg
http://localhost:3000/media/video/cat.mp4
http://localhost:3000/media/cry.mp3</code>
</pre>

<p>詳しくは、<a href="/ja/docs/Learn/Server-side/Express_Nodejs/Serving static files in Express">Expressでの静的ファイルの提供</a>を参照してください。</p>

<h3 id="エラーの処理">エラーの処理</h3>

<p>エラーは、通常の3つの引数ではなく、4つの引数 <code>(err、req、res、next)</code> を持つ1つ以上の特別なミドルウェア関数によって処理されます。例えば：</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="function token">use</span><span class="punctuation token">(</span><span class="keyword token">function</span><span class="punctuation token">(</span>err<span class="punctuation token">,</span> req<span class="punctuation token">,</span> res<span class="punctuation token">,</span> next<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  console<span class="punctuation token">.</span><span class="function token">error</span><span class="punctuation token">(</span>err<span class="punctuation token">.</span>stack<span class="punctuation token">)</span><span class="punctuation token">;</span>
  res<span class="punctuation token">.</span><span class="function token">status</span><span class="punctuation token">(</span><span class="number token">500</span><span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">send</span><span class="punctuation token">(</span><span class="string token">'Something broke!'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>これらは必要なコンテンツを返すことができますが、他のすべての <code>app.use()</code> および呼び出しをルーティングした後に呼び出して、リクエスト処理プロセスの最後のミドルウェアになるようにする必要があります。</p>

<p>Express にはエラーハンドラが組み込まれています。これは、アプリで発生する可能性がある残りのエラーを処理します。 このデフォルトのエラー処理ミドルウェア関数は、ミドルウェア関数スタックの最後に追加されます。<code>next()</code> にエラーを渡し、それをエラーハンドラで処理しなかった場合、それは組み込みエラーハンドラによって処理されます。エラーはスタックトレースとともにクライアントに書き込まれます。</p>

<div class="note">
<p><strong>メモ:</strong> スタックトレースは実稼働環境に含まれていません。プロダクションモードで実行するには、環境変数 <code>NODE_ENV</code> を '<code>production</code>' に設定する必要があります。</p>
</div>

<div class="note">
<p><strong>メモ:</strong> HTTP 404 およびその他の "エラー" ステータスコードはエラーとして扱われません。これらを処理したい場合は、ミドルウェア関数を追加して処理することができます。詳しくは <a href="http://expressjs.com/ja/starter/faq.html#how-do-i-handle-404-responses">FAQ</a> を見てください。</p>
</div>

<p>詳しくは<a href="http://expressjs.com/ja/guide/error-handling.html">エラー処理</a> (Express ドキュメント) を参照してください。</p>

<h3 id="データベースの使用">データベースの使用</h3>

<p>Express アプリケーションは、Node によってサポートされている任意のデータベースメカニズムを使用できます (Express 自体はデータベース管理のための特定の追加の動作や要件を定義していません)。PostgreSQL、MySQL、Redis、SQLite、MongoDB などを含む多くのオプションがあります。</p>

<p>これらを使用するには、まず NPM を使用してデータベースドライバをインストールする必要があります。たとえば、一般的な NoSQL MongoDB 用のドライバをインストールするには、次のコマンドを使用します。</p>

<pre class="brush: bash"><code>$ npm install mongodb
</code></pre>

<p>データベース自体はローカルにインストールすることも、クラウドサーバーにインストールすることもできます。Express コードではドライバが必要で、データベースへの接続から、作成、参照、更新、削除 (CRUD) 操作を実行します。以下の (Express ドキュメントからの) 例は、MongoDB を使ってどのように「哺乳類の」レコードを見つけることができるかを示しています。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="comment token">// これは mongodb バージョン 2.2.33 までの古いバージョンで動作します</span>
<span class="keyword token">var</span> MongoClient <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'mongodb'</span><span class="punctuation token">)</span><span class="punctuation token">.</span>MongoClient<span class="punctuation token">;</span>

MongoClient<span class="punctuation token">.</span><span class="function token">connect</span><span class="punctuation token">(</span><span class="string token">'mongodb://localhost:27017/animals'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>err<span class="punctuation token">,</span> db<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">if</span> <span class="punctuation token">(</span>err<span class="punctuation token">)</span> <span class="keyword token">throw</span> err<span class="punctuation token">;</span>

  db<span class="punctuation token">.</span><span class="function token">collection</span><span class="punctuation token">(</span><span class="string token">'mammals'</span><span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">find</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">toArray</span><span class="punctuation token">(</span><span class="keyword token">function</span> <span class="punctuation token">(</span>err<span class="punctuation token">,</span> result<span class="punctuation token">)</span> <span class="punctuation token">{</span>
    <span class="keyword token">if</span> <span class="punctuation token">(</span>err<span class="punctuation token">)</span> <span class="keyword token">throw</span> err<span class="punctuation token">;</span>

    console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span>result<span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>


<span class="comment token">// mongodb バージョン 3.0 以上のためのコード</span>
<span class="keyword token">let</span> MongoClient <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'mongodb'</span><span class="punctuation token">)</span><span class="punctuation token">.</span>MongoClient<span class="punctuation token">;</span>
MongoClient<span class="punctuation token">.</span><span class="function token">connect</span><span class="punctuation token">(</span><span class="string token">'mongodb://localhost:27017/animals'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>err<span class="punctuation token">,</span> client<span class="punctuation token">)</span><span class="punctuation token">{</span>
   <span class="keyword token">if</span><span class="punctuation token">(</span>err<span class="punctuation token">)</span> <span class="keyword token">throw</span> err<span class="punctuation token">;</span>

   <span class="keyword token">let</span> db <span class="operator token">=</span> client<span class="punctuation token">.</span><span class="function token">db</span><span class="punctuation token">(</span><span class="string token">'animals'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
   db<span class="punctuation token">.</span><span class="function token">collection</span><span class="punctuation token">(</span><span class="string token">'mammals'</span><span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">find</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">toArray</span><span class="punctuation token">(</span><span class="keyword token">function</span><span class="punctuation token">(</span>err<span class="punctuation token">,</span> result<span class="punctuation token">)</span><span class="punctuation token">{</span>
     <span class="keyword token">if</span><span class="punctuation token">(</span>err<span class="punctuation token">)</span> <span class="keyword token">throw</span> err<span class="punctuation token">;</span>
     console<span class="punctuation token">.</span><span class="function token">log</span><span class="punctuation token">(</span>result<span class="punctuation token">)</span><span class="punctuation token">;</span>
     client<span class="punctuation token">.</span><span class="function token">close</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
   <span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>もう1つの一般的な方法は、Object Relational Mapper ( "ORM") を介して間接的にデータベースにアクセスすることです。このアプローチではデータを「オブジェクト」または「モデル」として定義し、ORM はそれらを基礎となるデータベース形式にマッピングします。このアプローチには、開発者としてデータベースのセマンティクスではなく JavaScript オブジェクトの観点から考え続けることができ、受信データの検証とチェックを実行するための明らかな場所があるという利点があります。データベースについての詳細は、後の記事で説明します。</p>

<p>詳しくは<a href="https://expressjs.com/ja/guide/database-integration.html">データベース統合</a> (Express ドキュメント) を参照してください。</p>

<h3 id="データのレンダリング_ビュー">データのレンダリング (ビュー)</h3>

<p>テンプレートエンジン (Express では「ビューエンジン」と呼ばれます) を使用すると、ページの生成時に埋められるデータのプレースホルダを使用して、テンプレート内の出力ドキュメントの構造を指定できます。テンプレートは HTML の作成によく使用されますが、他の種類の文書も作成できます。 Express は<a href="https://github.com/expressjs/express/wiki#template-engines">いくつかのテンプレートエンジン</a>をサポートしています。ここでは、より人気の高いエンジンの便利な比較ができます。<a href="https://strongloop.com/strongblog/compare-javascript-templates-jade-mustache-dust/">JavaScript テンプレートエンジンの比較：Jade、Moustache、Dustなど</a></p>

<p>次に示すように、アプリケーション設定コードで、使用するテンプレートエンジンと、Express が 'ビュー' および 'ビューエンジン' 設定を使用してテンプレートを探す場所を設定します (テンプレートライブラリを含むパッケージもインストールする必要があります！)</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> express <span class="operator token">=</span> <span class="function token">require</span><span class="punctuation token">(</span><span class="string token">'express'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> app <span class="operator token">=</span> <span class="function token">express</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// ('views') テンプレートを含むディレクトリーを設定</span>
app<span class="punctuation token">.</span><span class="keyword token">set</span><span class="punctuation token">(</span><span class="string token">'views'</span><span class="punctuation token">,</span> path<span class="punctuation token">.</span><span class="function token">join</span><span class="punctuation token">(</span>__dirname<span class="punctuation token">,</span> <span class="string token">'views'</span><span class="punctuation token">)</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// 利用するビューエンジン、この場合は 'some_template_engine_name' を設定</span>
app<span class="punctuation token">.</span><span class="keyword token">set</span><span class="punctuation token">(</span><span class="string token">'view engine'</span><span class="punctuation token">,</span> <span class="string token">'some_template_engine_name'</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>テンプレートの外観は使用するエンジンによって異なります。"title" および "message" という名前のデータ変数のプレースホルダを含む "index.&lt;テンプレート拡張子&gt;" という名前のテンプレートファイルがあると仮定すると、ルートハンドラ関数で <code><a href="http://expressjs.com/ja/4x/api.html#res.render">Response.render()</a></code> を呼び出して HTML レスポンスを作成し、送信することになります。</p>

<pre class="brush: js line-numbers  language-js"><code class="language-js">app<span class="punctuation token">.</span><span class="keyword token">get</span><span class="punctuation token">(</span><span class="string token">'/'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span>req<span class="punctuation token">,</span> res<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  res<span class="punctuation token">.</span><span class="function token">render</span><span class="punctuation token">(</span><span class="string token">'index'</span><span class="punctuation token">,</span> <span class="punctuation token">{</span> title<span class="punctuation token">:</span> <span class="string token">'About dogs'</span><span class="punctuation token">,</span> message<span class="punctuation token">:</span> <span class="string token">'Dogs rock!'</span> <span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span></code></pre>

<p>詳しくは <a href="http://expressjs.com/ja/guide/using-template-engines.html">Express でのテンプレートエンジンの使用</a> (Express ドキュメント) を参照してください。</p>

<h3 id="ファイル構造">ファイル構造</h3>

<p>Express は、構造や使用するコンポーネントに関しては何も想定していません。ルート、ビュー、静的ファイル、およびその他のアプリケーション固有のロジックは、任意のディレクトリー構造を持つ任意の数のファイルに存在できます。 Express アプリケーション全体を1つのファイルにまとめることは完全に可能ですが、通常は機能 (アカウント管理、ブログ、ディスカッション掲示板など) およびアーキテクチャ上の問題のドメイン (<a href="/ja/docs/Web/Apps/Build/Modern_web_app_architecture/MVC_architecture">MVC アーキテクチャ</a>を使用している場合は、モデル、ビュー、コントローラーなど) に基づいてアプリケーションをファイルに分割します。</p>

<p>後のトピックでは、ウェブアプリケーションを作成するために簡単に拡張できるモジュール式のアプリケーションスケルトンを作成する Express Application Generator を使用します。</p>

<ul>
</ul>

<h2 id="まとめ">まとめ</h2>

<p>おめでとうございます、Express/Node の旅の最初のステップを完了しました。これで Express と Node の主な利点と、Express アプリケーションの主要部分がどのように見えるか (ルート、ミドルウェア、エラー処理、およびテンプレートコード) をおおまかに理解できています。また、Express は指図しないフレームワークであるため、これらの部分をどのようにまとめるかやどのライブラリを使用するかは、ほとんどあなた次第です。</p>

<p>もちろん、Express は意図的に非常に軽量なウェブアプリケーションフレームワークであるため、その利点と可能性の多くはサードパーティのライブラリと機能からもたらされています。以下の記事でそれらをより詳しく見ていきます。次回の記事では、Node 開発環境のセットアップについて見ていきます。そうすれば、いくつかの Express コードが実際に動作しているところを見始めることができます。</p>

<h2 id="関連情報">関連情報</h2>

<ul>
 <li><a href="https://medium.com/@ramsunvtech/manage-multiple-node-versions-e3245d5ede44">Venkat.R - Manage Multiple Node versions</a></li>
 <li><a href="https://nodejs.org/api/modules.html#modules_modules">Modules</a> (Node API docs)</li>
 <li><a href="https://expressjs.com/ja">Express</a> (home page)</li>
 <li><a href="http://expressjs.com/ja/starter/basic-routing.html">Basic routing</a> (Express ドキュメント)</li>
 <li><a href="http://expressjs.com/ja/guide/routing.html">Routing guide</a> (Express ドキュメント)</li>
 <li><a href="http://expressjs.com/ja/guide/using-template-engines.html">Using template engines with Express</a> (Express ドキュメント)</li>
 <li><a href="https://expressjs.com/ja/guide/using-middleware.html">Using middleware</a> (Express ドキュメント)</li>
 <li><a href="http://expressjs.com/ja/guide/writing-middleware.html">Writing middleware for use in Express apps</a> (Express ドキュメント)</li>
 <li><a href="https://expressjs.com/ja/guide/database-integration.html">Database integration</a> (Express ドキュメント)</li>
 <li><a href="http://expressjs.com/ja/starter/static-files.html">Serving static files in Express</a> (Express ドキュメント)</li>
 <li><a href="http://expressjs.com/ja/guide/error-handling.html">Error handling</a> (Express ドキュメント)</li>
</ul>

<div>{{NextMenu("Learn/Server-side/Express_Nodejs/development_environment", "Learn/Server-side/Express_Nodejs")}}</div>

<h2 id="このモジュール">このモジュール</h2>

<ul>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/Introduction">Express/Node のイントロダクション</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/development_environment">Node 開発環境の設定</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/Tutorial_local_library_website">Express チュートリアル: 地域図書館のウェブサイト</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/skeleton_website">Express チュートリアル Part 2: スケルトンウェブサイトの作成</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/mongoose">Express チュートリアル Part 3: データベースを使う (Mongoose を使用)</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/routes">Express チュートリアル Part 4: ルートとコントローラ</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/Displaying_data">Express チュートリアル Part 5: ライブラリデータの表示</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/forms">Express チュートリアル Part 6: フォームの操作</a></li>
 <li><a href="/ja/docs/Learn/Server-side/Express_Nodejs/deployment">Express チュートリアル Part 7: プロダクションへのデプロイ</a></li>
</ul>