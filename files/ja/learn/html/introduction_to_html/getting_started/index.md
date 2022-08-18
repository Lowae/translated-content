---
title: HTML を始めよう
slug: Learn/HTML/Introduction_to_HTML/Getting_started
tags:
  - Attribute
  - Beginner
  - CodingScripting
  - Comment
  - Element
  - Guide
  - HTML
  - entity reference
  - whitespace
translation_of: Learn/HTML/Introduction_to_HTML/Getting_started
---
<div>{{LearnSidebar}}</div>

<div>{{NextMenu("Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML", "Learn/HTML/Introduction_to_HTML")}}</div>

<p class="summary">この記事では HTML の不変的な基礎を扱って、始められるようにします。要素や属性などの重要な用語 (すでに聞き覚えはあるかもしれません)、それらが言語にどう組み込まれているか説明します。また、HTML 要素の構造、典型的な HTML ページの構造を見せて、その他の重要な基礎言語機能について説明します。それでは、 HTML の例とともに見ていきましょう。</p>

<table class="learn-box standard-table">
 <tbody>
  <tr>
   <th scope="row">前提条件:</th>
   <td>基礎的なコンピュータリテラシー、<a href="/ja/Learn/Getting_started_with_the_web/Installing_basic_software">基本的なソフトウェアのインストール</a>、<a href="/ja/Learn/Getting_started_with_the_web/Dealing_with_files">ファイル取扱い</a>の基礎理解。</td>
  </tr>
  <tr>
   <th scope="row">目的:</th>
   <td>
    <p>HTML 言語の基礎習得と、いくつかの HTML 要素を書く練習</p>
   </td>
  </tr>
 </tbody>
</table>

<h2 id="What_is_HTML" name="What_is_HTML">HTML とは？</h2>

<p>{{glossary("HTML")}} (ハイパーテキスト・マークアップ・ランゲージ／Hypertext Markup Language) はプログラミング言語ではありません。HTML 言語は、訪れたウェブサイトの構成をブラウザに対して伝えるために使うマークアップ言語です。HTML 言語はウェブ開発者が望むこと次第で、複雑なものにも簡単なものにもなります。HTML は{{glossary("Element", "要素")}}の集まりからなり、コンテンツの一部を要素で囲む（<em>マークアップ</em>する）ことで、特定の見せ方・動かし方に変えられます。囲むための{{glossary("Tag", "タグ")}}は、コンテンツの一部をハイパーリンク (ウェブ上の別ページへリンクすること) にしたり、単語を斜体にしたりすることができます。たとえば、次の一行を見てください：</p>

<pre>My cat is very grumpy</pre>

<p>この行を独立させたい場合、それを段落タグ ({{htmlelement("p")}}) 要素で囲んで段落指定することで実現できます:</p>

<pre class="brush: html">&lt;p&gt;My cat is very grumpy&lt;/p&gt;</pre>

<div class="note">
<p><strong>注</strong>:HTML の要素は大文字小文字を区別しません。つまり大文字でも小文字でも書くことができます。例えば {{htmlelement("title")}} 要素は <code>&lt;title&gt;</code>、<code>&lt;TITLE&gt;</code>、<code>&lt;Title&gt;</code>、<code>&lt;TiTlE&gt;</code> などと書くことができて、どれも正しく動作します。最も良いのは、一貫性や信頼性、その他の理由のためにすべての要素を小文字で書くことです。</p>
</div>

<h2 id="Anatomy_of_a_HTML_element" name="Anatomy_of_a_HTML_element">HTML 要素の分解</h2>

<p>先ほどの段落タグの要素についてもう少し詳しく見ていきましょう:</p>

<p><img alt="" src="https://mdn.mozillademos.org/files/9347/grumpy-cat-small.png" style="display: block; height: 255px; margin: 0px auto; width: 821px;"></p>

<p>この要素の主要な部分は次のとおりです:</p>

<ol>
 <li><strong>開始タグ(Opening tag):</strong> 要素名 (この場合は "p")、囲んでいる開き<strong>山括弧</strong>と閉じ<strong>山括弧</strong>で構成されています。これは要素が始まってその効果が開始する位置を宣言しますーこの場合、段落が始まる位置です。</li>
 <li><strong>終了タグ(Closing tag):</strong> 要素名の前に一つのスラッシュが含まれることを除けば、開始タグと同じです。これは要素の終了を宣言しますーこの場合、段落が終わる位置です。終了タグを忘れるのは初心者にありがちなミスで、おかしな結果になってしまいます。</li>
 <li><strong>内容(Content):</strong> これは要素の内容で、この場合、テキストそのものです。</li>
 <li><strong>要素(Element):</strong> 開始タグ + 内容 + 終了タグが要素になります。</li>
</ol>

<h3 id="Active_learning_creating_your_first_HTML_element" name="Active_learning_creating_your_first_HTML_element"><strong>実習: 最初の HTML 要素を作ってみる</strong></h3>

<p>以下の Input 欄にある行を <code>&lt;em&gt;</code> と <code>&lt;/em&gt;</code> で囲んでください (要素を開始するために行の先頭に <code>&lt;em&gt;</code> を、要素を終了するために行の末尾に <code>&lt;/em&gt;</code> をそれぞれ置きます) — これによりその行はイタリック体 (斜体) によって強調表示されるはずです！　この変化は Output 欄でリアルタイムで確認できているはずです。</p>

<p>もし入力ミスをしても、<em>Reset</em> ボタンを押すことでいつでもリセットできます。立ち往生してしまっても <em>Show solution</em> ボタンを押せばいつでもカンニングできます。</p>

<div class="hidden">
<h6 id="Playable_code" name="Playable_code">Playable code</h6>

<pre class="brush: html line-numbers  language-html"><code class="language-html"><span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Live output<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>output<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">50</span>px<span class="punctuation token">;</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Editable code<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>p</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>a11y-label<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>Press Esc to move focus away from the code area (Tab inserts a tab character).<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>p</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>textarea</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>code<span class="punctuation token">"</span></span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>playable-code<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">100</span>px<span class="punctuation token">;</span><span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">95%</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  This is my text.
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>textarea</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>controls<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>reset<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Reset<span class="punctuation token">"</span></span> <span class="punctuation token">/&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>solution<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Show solution<span class="punctuation token">"</span></span> <span class="punctuation token">/&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span></code></pre>

<pre class="brush: css line-numbers  language-css"><code class="language-css"><span class="selector token">html </span><span class="punctuation token">{</span>
  <span class="property token">font-family</span><span class="punctuation token">:</span> <span class="string token">'Open Sans Light'</span>,Helvetica,Arial,sans-serif<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">h2 </span><span class="punctuation token">{</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">16</span>px<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token"><span class="class token">.a11y-label</span> </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">0</span><span class="punctuation token">;</span>
  <span class="property token">text-align</span><span class="punctuation token">:</span> right<span class="punctuation token">;</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">0.7</span>rem<span class="punctuation token">;</span>
  <span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">98%</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">body </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">10</span>px<span class="punctuation token">;</span>
  <span class="property token">background</span><span class="punctuation token">:</span> <span class="hexcode token">#f5f9fa</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span></code></pre>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> textarea <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'code'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> reset <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'reset'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solution <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'solution'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> output <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">querySelector</span><span class="punctuation token">(</span><span class="string token">'.output'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> code <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="keyword token">var</span> userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  output<span class="punctuation token">.</span>innerHTML <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

reset<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> code<span class="punctuation token">;</span>
  userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>
  solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

solution<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> solutionEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Hide solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> userEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="keyword token">var</span> htmlSolution <span class="operator token">=</span> <span class="string token">'&lt;em&gt;This is my text.&lt;/em&gt;'</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>

textarea<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'input'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>
window<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'load'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// stop tab key tabbing out of textarea and</span>
<span class="comment token">// make it write a tab at the caret position instead</span>

textarea<span class="punctuation token">.</span>onkeydown <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span>e<span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">9</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    e<span class="punctuation token">.</span><span class="function token">preventDefault</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
    <span class="function token">insertAtCaret</span><span class="punctuation token">(</span><span class="string token">'\t'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">27</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span><span class="function token">blur</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">insertAtCaret</span><span class="punctuation token">(</span>text<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">var</span> scrollPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>scrollTop<span class="punctuation token">;</span>
  <span class="keyword token">var</span> caretPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>selectionStart<span class="punctuation token">;</span>

  <span class="keyword token">var</span> front <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span><span class="number token">0</span><span class="punctuation token">,</span> caretPos<span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="keyword token">var</span> back <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>selectionEnd<span class="punctuation token">,</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">.</span>length<span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> front <span class="operator token">+</span> text <span class="operator token">+</span> back<span class="punctuation token">;</span>
  caretPos <span class="operator token">=</span> caretPos <span class="operator token">+</span> text<span class="punctuation token">.</span>length<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionStart <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionEnd <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span><span class="function token">focus</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>scrollTop <span class="operator token">=</span> scrollPos<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="comment token">// Update the saved userCode every time the user updates the text area code</span>

textarea<span class="punctuation token">.</span>onkeyup <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="comment token">// We only want to save the state when the user code is being shown,</span>
  <span class="comment token">// not the solution, so that solution is not saved over the user code</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    solutionEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span></code></pre>
</div>

<p>{{ EmbedLiveSample('Playable_code', 700, 300, "", "", "hide-codepen-jsfiddle") }}</p>

<h3 id="Nesting_elements" name="Nesting_elements">要素のネスト</h3>

<p>要素の中に要素を入れることができますーこれは“<strong>ネスト</strong>” (入れ子) と呼ばれています。たとえば “My cat is <strong>very</strong> grumpy.” と記述したい場合、“very” という語を {{htmlelement("strong")}} 要素で囲むことができ、それはその語がより強く強調表示されることを意味します：</p>

<pre class="brush: html">&lt;p&gt;My cat is &lt;strong&gt;very&lt;/strong&gt; grumpy.&lt;/p&gt;</pre>

<p>ただし、要素が正しくネストされていることを確認する必要はあります: 上の例では、開始タグは最初に <code>p</code> 要素、その次に <code>strong</code> 要素が来ますから、終了タグは最初に <code>strong</code> 要素を、一番最後に <code>p</code> 要素を置くことになります。次は間違った例です:</p>

<pre class="example-bad brush: html">&lt;p&gt;My cat is &lt;strong&gt;very grumpy.&lt;/p&gt;&lt;/strong&gt;</pre>

<p>タグのセットが互いに内側か外側なのかがはっきり分かるように、要素の開始と終了は正しく配置する必要があります。もし上の例のように互いに “掛け違って” しまっている場合、ブラウザーはそのマークアップが本来意図していただろうことを出来るだけ読み取ろうとはしますが、予期しない結果となることは当然に想定されます。ですからこうした “掛け違い” はやめましょう！</p>

<h3 id="Block_versus_inline_elements" name="Block_versus_inline_elements">ブロック要素とインライン要素</h3>

<p>HTML の要素には 2 つの重要なカテゴリーがあり、それは知っておくべきことです。すなわち、ブロックレベル要素とインライン要素です。</p>

<ul>
 <li>ブロックレベル要素はウェブページ上で視認できるブロックを形成します — それらはそれより前にあるいかなるコンテンツに対しても新たな行におけるコンテンツとして表示され、そのブロックの後に来るいかなるコンテンツもまた新たな行で表示されることになります。ブロックレベル要素はそのウェブページの構造、たとえば段落・リスト・ナビゲーションメニュー・フッターなどを表すことに使用される傾向があります。ブロックレベル要素はインライン要素の中にネストされることはできませんが、他のブロックレベル要素にネストされることがあります。</li>
 <li>インライン要素はブロックレベル要素の中に包含され、なおかつ、段落全体やコンテンツのグループではなく、ドキュメントの内容の小さな部分だけを囲む要素です。インライン要素はドキュメント内に新たな行を表示させません; それらは通常、例えば、{{htmlelement("a")}} 要素 (ハイパーリンク) 又は {{htmlelement("em")}} や {{htmlelement("strong")}} といった強調要素のように、テキスト段落の中で表示されます。</li>
</ul>

<p>次の例で考えてみましょう:</p>

<pre class="brush: html">&lt;em&gt;first&lt;/em&gt;&lt;em&gt;second&lt;/em&gt;&lt;em&gt;third&lt;/em&gt;

&lt;p&gt;fourth&lt;/p&gt;&lt;p&gt;fifth&lt;/p&gt;&lt;p&gt;sixth&lt;/p&gt;
</pre>

<p>{{htmlelement("em")}} 要素はインライン要素なので、以下で確認できるように、最初の 3 つの要素は同じ行で他の要素と互いにスペースを空けずにたたずんでいます。一方で、{{htmlelement("p")}} 要素はブロックレベル要素なので、各要素はその上下にスペースを伴った新たな行で表示されます (この間隔はブラウザーが段落に対して適用するデフォルトの <a href="/ja/docs/Learn/CSS/Introduction_to_CSS">CSS のスタイル</a>によるものです)。</p>

<p>{{ EmbedLiveSample('Block_versus_inline_elements', 700, 200, "", "") }}</p>

<div class="note">
<p><strong>注意</strong>: HTML5 においては要素カテゴリが再定義されています: <a href="http://www.whatwg.org/specs/web-apps/current-work/complete/section-index.html#element-content-categories">要素のコンテンツ・カテゴリー</a>を見てください。これらの定義は従来のものに比べてより正確で、なおかつ曖昧さが少ないものとなっていますが、一方では、それらは “ブロックレベル要素” と “インライン要素” の対比よりも遥かに理解することが難しくなっています。このため、私たちはここのトピックを通じて従来の分類を堅持するつもりです。</p>
</div>

<div class="note">
<p><strong>注意</strong>: このトピックで使っている “ブロック” と “インライン” の用語は <a href="/ja/docs/Learn/CSS/Introduction_to_CSS/Box_model#Types_of_CSS_boxes">CSS ボックスのタイプ</a>と同じ名前で混同するでしょう。既定ではこれらは関係ありますが、CSS の表示タイプの変更は要素のカテゴリーを変更しませんし、どの要素が入っているべきでどの要素に入れられるべきかにも影響しません。HTML5 でこの用語が落とされた理由は、このとてもよくある混同を防ぐためです。</p>
</div>

<div class="note">
<p><strong>注意</strong>: ブロックレベル要素とインライン要素のリストを含む有用なリファレンスページがあります — <a href="/ja/docs/Web/HTML/Block-level_elements">ブロックレベル要素</a>と<a href="/ja/docs/Web/HTML/Inline_elements">インライン要素</a>をご覧ください。</p>
</div>

<h3 id="Empty_elements" name="Empty_elements">空要素</h3>

<p>全ての要素が上述の開始タグ・コンテンツ・終了タグのパターンに従っているわけではありません。いくつかの要素は 1 つのタグのみで構成され、それは通常、ドキュメント内でそれが含まれている場所に何かを挿入したり埋め込むために使用されます。例えば、以下の {{htmlelement("img")}} 要素はウェブページ上のそれが含まれた場所に 1 つの画像ファイルを埋め込みます:</p>

<pre class="brush: html">&lt;img src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"&gt;</pre>

<p>これはページに次の画像を出力するはずです:</p>

<p>{{ EmbedLiveSample('Empty_elements', 700, 300, "", "", "hide-codepen-jsfiddle") }}</p>

<div class="note">
<p><strong>注意</strong>: 空要素 (Empty elements) は Void 要素 (Void elements) と呼ばれていることがあります。</p>
</div>

<h2 id="Attributes" name="Attributes">属性</h2>

<p>要素は次のように属性(Attribute)を持つこともできます:</p>

<p><img alt='&amp;amp;amp;lt;p class="editor-note">My cat is very grumpy&amp;amp;amp;lt;/p>' src="https://mdn.mozillademos.org/files/9345/grumpy-cat-attribute-small.png" style="display: block; height: 156px; margin: 0px auto; width: 1287px;"></p>

<p>属性は実際のコンテンツの中で表示させたくない「要素に関する追加情報」を保有します。上のケースでは <code>class</code> 属性は、その要素に後でスタイル情報などが適用される対象であることを示すものとして使用できるような、固有の名前を持つことを許容します。</p>

<p>各属性は次の要件を満たす必要があります:</p>

<ol>
 <li>属性名と要素名の間に 1 つの半角スペース (その要素内にすでに 1 つ以上の属性が設定されている場合は、併せて各属性名の間)</li>
 <li>属性名とそれに続く等号 (=)</li>
 <li>属性値。始端から終端までをクォーテーションマーク (引用符) で囲む</li>
</ol>

<h3 id="Active_learning_Adding_attributes_to_an_element" name="Active_learning_Adding_attributes_to_an_element">実習: 要素に属性を追加する</h3>

<p>要素のもう一つの例として {{htmlelement("a")}} (これを「アンカー」と言って、テキストの一部を囲んでハイパーリンクにするものです) を考えます。アンカー要素は多くの属性を持つことができますが、例えばこれらのものが使われます:</p>

<ul>
 <li><code>href</code>: この属性にはリンクが参照するウェブ上のアドレスを指定します。またはリンクをクリックしたときにブラウザーが遷移する場所のことです。例えば、<code>href="https://www.mozilla.org/"</code> のように指定します。</li>
 <li><code>title</code>: この属性にはリンクについての追加情報（リンク先のページが何であるかなど）を記載します。例えば、<code>title="The Mozilla homepage"</code> のように書きます。この内容はリンクにマウスカーソルを重ねた (マウスホバー) 時にツールチップとして表示されるでしょう。</li>
 <li><code>target</code>: リンク先の内容を表示する場所 (ブラウジングコンテキスト) を指定します。例えば、<code>target="_blank"</code> と指定すると、リンク先の内容を新しいタブに表示します。現在のタブにリンク先の内容を表示させたい場合は <code>target</code>属性を省略します。</li>
</ul>

<p>それでは以下の Input 欄を編集して、あなたの好きなサイトのリンクを張ってみましょう。まず、<code>&lt;a&gt;</code> 要素を追加します。次に、<code>&lt;a&gt;</code> 要素に <code>href</code> 属性と <code>title</code> 属性を追加します。最後に、新しいタブでリンク先を開くために <code>target</code> 属性を追加します。この変化は Output 欄でリアルタイムで確認できているはずです。まずテキストがハイパーリンクに変わります。そのリンクをホバーしてやる (マウスホバー) と <code>title</code> 属性のコンテンツが表示されます。そのリンクをクリックすると <code>href</code> 属性で指定したページに遷移します。要素名と各属性の間に半角スペースを挿入することに気を付けてください。</p>

<p>もし入力ミスをしても、Reset ボタンを押すことでいつでもリセットできます。立ち往生してしまっても Show solution ボタンを押せばいつでもカンニングできます。</p>

<div class="hidden">
<h6 id="Playable_code2" name="Playable_code2">Playable code2</h6>

<pre class="brush: html line-numbers  language-html"><code class="language-html"><span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Live output<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>output<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">50</span>px<span class="punctuation token">;</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Editable code<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>p</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>a11y-label<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>Press Esc to move focus away from the code area (Tab inserts a tab character).<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>p</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>textarea</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>code<span class="punctuation token">"</span></span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>input<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">100</span>px<span class="punctuation token">;</span><span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">95%</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="entity token" title="&lt;">&amp;lt;</span>p<span class="entity token" title=">">&amp;gt;</span>A link to my favourite website.<span class="entity token" title="&lt;">&amp;lt;</span>/p<span class="entity token" title=">">&amp;gt;</span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>textarea</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>playable-buttons<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>reset<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Reset<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>solution<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Show solution<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span></code></pre>

<pre class="brush: css line-numbers  language-css"><code class="language-css"><span class="selector token">html </span><span class="punctuation token">{</span>
  <span class="property token">font-family</span><span class="punctuation token">:</span> sans-serif<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">h2 </span><span class="punctuation token">{</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">16</span>px<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token"><span class="class token">.a11y-label</span> </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">0</span><span class="punctuation token">;</span>
  <span class="property token">text-align</span><span class="punctuation token">:</span> right<span class="punctuation token">;</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">0.7</span>rem<span class="punctuation token">;</span>
  <span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">98%</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">body </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">10</span>px<span class="punctuation token">;</span>
  <span class="property token">background</span><span class="punctuation token">:</span> <span class="hexcode token">#f5f9fa</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span></code></pre>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> textarea <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'code'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> reset <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'reset'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solution <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'solution'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> output <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">querySelector</span><span class="punctuation token">(</span><span class="string token">'.output'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> code <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="keyword token">var</span> userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  output<span class="punctuation token">.</span>innerHTML <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

reset<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> code<span class="punctuation token">;</span>
  userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>
  solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

solution<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> solutionEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Hide solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> userEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="keyword token">var</span> htmlSolution <span class="operator token">=</span> <span class="string token">'&lt;p&gt;A link to my &lt;a href="https://www.mozilla.org/" title="The Mozilla homepage" target="_blank"&gt;favourite website&lt;/a&gt;.&lt;/p&gt;'</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>

textarea<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'input'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>
window<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'load'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// stop tab key tabbing out of textarea and</span>
<span class="comment token">// make it write a tab at the caret position instead</span>

textarea<span class="punctuation token">.</span>onkeydown <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span>e<span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">9</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    e<span class="punctuation token">.</span><span class="function token">preventDefault</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
    <span class="function token">insertAtCaret</span><span class="punctuation token">(</span><span class="string token">'\t'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">27</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span><span class="function token">blur</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">insertAtCaret</span><span class="punctuation token">(</span>text<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">var</span> scrollPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>scrollTop<span class="punctuation token">;</span>
  <span class="keyword token">var</span> caretPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>selectionStart<span class="punctuation token">;</span>

  <span class="keyword token">var</span> front <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span><span class="number token">0</span><span class="punctuation token">,</span> caretPos<span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="keyword token">var</span> back <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>selectionEnd<span class="punctuation token">,</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">.</span>length<span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> front <span class="operator token">+</span> text <span class="operator token">+</span> back<span class="punctuation token">;</span>
  caretPos <span class="operator token">=</span> caretPos <span class="operator token">+</span> text<span class="punctuation token">.</span>length<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionStart <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionEnd <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span><span class="function token">focus</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>scrollTop <span class="operator token">=</span> scrollPos<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="comment token">// Update the saved userCode every time the user updates the text area code</span>

textarea<span class="punctuation token">.</span>onkeyup <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="comment token">// We only want to save the state when the user code is being shown,</span>
  <span class="comment token">// not the solution, so that solution is not saved over the user code</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    solutionEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span></code></pre>
</div>

<p>{{ EmbedLiveSample('Playable_code2', 700, 360, "", "", "hide-codepen-jsfiddle") }}</p>

<h3 id="Boolean_attributes" name="Boolean_attributes">真偽値属性</h3>

<p>沢山の HTML ソースを見ていくうちに、属性値のない属性を発見するでしょう。このことは文法的に許されています。こういった属性のことを「真偽値属性」と言います。真偽値属性は一般的に属性名と同じ属性値だけを取ることができます。例えば、<code>input</code> 要素の {{htmlattrxref("disabled", "input")}} 属性は真偽値属性ですが、下記のように記述した場合、 input 要素が "使用不可能に" (disabled, グレーアウト表示) なり、データを入力することができなくなります。</p>

<pre>&lt;input type="text" disabled="disabled"&gt;
</pre>

<p>真偽値属性は、略記法として次のように書くことが文法的に許されています。比較のために "使用不可能に" (disabled, グレーアウト表示) しなかった場合の <code>input</code> 要素も併記しています。</p>

<pre class="brush: html">&lt;input type="text" disabled&gt;

&lt;input type="text"&gt;</pre>

<p>上記の HTML コードの結果は下記のようになります。</p>

<p>{{ EmbedLiveSample('Boolean_attributes', 700, 50, "", "", "hide-codepen-jsfiddle") }}</p>

<div class="warning">
<p>訳者注：下記の様な真偽値属性の属性名と属性値を一致させない記述は HTML の仕様としては誤りです。このような誤りを防ぐために、真偽値属性の真偽値は必ず省略するようにしましょう。</p>

<pre>&lt;input type="text" disabled="foo bar baz"&gt;
</pre>
</div>

<h3 id="Omitting_quotes_around_attribute_values" name="Omitting_quotes_around_attribute_values">属性値のクォーテーションマークを省略することについて</h3>

<p>ウェブ (正式にはワールド・ワイド・ウェブ) 上の HTML 文章の中には奇妙なマークアップスタイルで記述されているものもあります。その一つとして、「属性値をクォーテーションマークで囲まない」というのがあります。このスタイルでは正しく動作する場合としない場合があります。先ほどの <code>&lt;a&gt;</code> タグの例で言うと、このような <code>href</code> 属性だけの基本的な使い方では正しく動作します。</p>

<pre>&lt;a href=<code>https://www.mozilla.org/</code>&gt;favourite website&lt;/a&gt;</pre>

<p>しかし、例えば次のように半角スペースの入った <code>title</code> 属性を追加すると動作がおかしくなります。</p>

<pre class="example-bad brush: html">&lt;a href=<code>https://www.mozilla.org/</code> title=The Mozilla homepage&gt;favourite website&lt;/a&gt;</pre>

<p>この場合だと「<code>title</code> 属性は "The" という属性値を持ち、それとは別に <code>&lt;a&gt;</code>要素が <code>Mozilla</code> と <code>homepage</code> という真偽値属性を持つ」というようにブラウザーは誤解します。このように、「属性値をクォーテーションマークで囲まない」ことによる違いは HTML を見ただけでは分からないので、コードのエラーや予期しない動作の原因となります。このコードをブラウザーに解釈させたものを下に用意しましたので、このリンク上をホバーしてツールチップに表示される文字がどうなっているかを確認してみましょう。</p>

<p>{{EmbedLiveSample('Omitting_quotes_around_attribute_values', 700, 100, "", "", "hide-codepen-jsfiddle") }}</p>

<p>安全なコードを書くために、必ず属性値にはクォーテーションマークをつけましょう。そうすれば、先ほどのような問題を避けることができ、コードの可読性も向上します。</p>

<h3 id="Single_or_double_quotes" name="Single_or_double_quotes">ダブルクォートかシングルクォートか？</h3>

<p>この記事では属性を囲むクォーテーションマークとしてすべてダブルクォート ( <code>"</code> ) を使用しています。しかし誰かの HTML でシングルクォート ( <code>'</code> ) を見ることがあるかもしれません。これは書き方の問題なので、属性値はダブルクォートで囲んでもシングルクォートで囲んでも構いません。例えば次の 2 つの行は等価です。</p>

<pre class="brush: html">&lt;a href="http://www.example.com"&gt;A link to my example.&lt;/a&gt;

&lt;a href='http://www.example.com'&gt;A link to my example.&lt;/a&gt;</pre>

<p>但し、これらを混在させて使うことはできません。次の記述は誤りです。</p>

<pre class="example-bad brush: html">&lt;a href="http://www.example.com'&gt;A link to my example.&lt;/a&gt;</pre>

<p>属性値をダブルクォートで囲んでいる場合は、その内部でシングルクォートを書くこともできますし、シングルクォートの中でダブルクォートを書くこともできます。</p>

<pre class="brush: html">&lt;a href="http://www.example.com" title="Isn't this fun?"&gt;A link to my example.&lt;/a&gt;</pre>

<p>ただし、両方の引用符が同じ種類 (一重引用符または二重引用符) の引用符の中に引用符を含める場合は、引用符に <a href="/ja/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Entity_references_Including_special_characters_in_HTML">HTML エンティティを使用する</a>必要があります。たとえば、これは壊れます：</p>

<pre class="example-bad brush: html line-numbers  language-html"><code class="language-html">&lt;a href='http://www.example.com' title='Isn't this fun?'&gt;A link to my example.<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>a</span><span class="punctuation token">&gt;</span></span></code></pre>

<p>だからあなたはこのようにする必要があります：</p>

<pre class="brush: html line-numbers  language-html"><code class="language-html"><span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>a</span> <span class="attr-name token">href</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">'</span>http://www.example.com<span class="punctuation token">'</span></span> <span class="attr-name token">title</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">'</span>Isn&amp;#39;t this fun?<span class="punctuation token">'</span></span><span class="punctuation token">&gt;</span></span>A link to my example.<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>a</span><span class="punctuation token">&gt;</span></span></code></pre>

<h2 id="Anatomy_of_a_HTML_document" name="Anatomy_of_a_HTML_document">HTML 文書の構成</h2>

<p>これまで、個々の HTML の要素の基礎を説明しましたが、それら単体ではあまり有用ではありません。ここでは個々の HTML の要素を使って HTML ページを構成する方法を説明していきます。</p>

<pre class="brush: html">&lt;!DOCTYPE html&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;meta charset="utf-8"&gt;
    &lt;title&gt;My test page&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;This is my page&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</pre>

<p>上記の HTML 文書を例に、順に解説していきます。</p>

<ol>
 <li>
  <p><code>&lt;!DOCTYPE html&gt;</code>: いわゆる "doctype" というものです。 HTML の黎明期(1991～1992年あたり)には、 "doctype" というものは HTML の文法セットへのリンクとしての役割を持っていました。当時の "doctype" の記述は自動エラーチェックが容易であるなどの長所も持っていました。当時の "doctype" は、次のようなものでした。</p>

  <pre><code>&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"&gt;</code></pre>

  <p>しかし、今日においては誰も HTML における "doctype" の本来的な役割なんて考えていません。 "doctype" はつじつま合わせのための歴史的な産物です。今日においてには <code>&lt;!DOCTYPE html&gt;</code> は正しい "doctype" と認識させるための最も簡潔な記述です。 "doctype" について、これ以上知る必要はありません。</p>
 </li>
 <li><code>&lt;html&gt;&lt;/html&gt;</code>: {{htmlelement("html")}} 要素。 HTML 文書は<code>&lt;html&gt;</code>要素 1 つだけからなります。この要素はページ全体であり、<code>&lt;html&gt;</code> タグはページ全体を囲んでいます。<code>&lt;html&gt;</code> 要素はルート要素とも呼ばれます。</li>
 <li><code>&lt;head&gt;&lt;/head&gt;</code>: {{htmlelement("head")}} 要素。この要素は、HTML ページに入れておきたいが見せたくないすべてのものを入れておくコンテナーの働きをします。例えば、検索結果に出したいページのキーワードや説明や、ページのスタイルを指定するための CSS や、文字エンコーディングの定義などが含まれます。より詳しくは、このシリーズの次の記事で詳しく説明します。</li>
 <li><code>&lt;meta charset="utf-8"&gt;</code>: この要素はこの文書が UTF-8 という文字コードを使用しているということをブラウザーに伝えるためのものです。UTF-8 は世界中の自然言語の大半をカバーしている文字コードです。重要なこととしてあらゆるテキストコンテンツを扱うことができます。文字コードとして UTF-8 を指定しない手はなく、そうしておけば後で説明する問題を回避できます。</li>
 <li><code>&lt;title&gt;&lt;/title&gt;</code>: {{htmlelement("title")}} 要素。これはページのタイトルを指定するもので、ページが読み込まれたブラウザーのタブに表示されます。また、このページをブラウザー上でブックマークしたりお気に入りに追加したりすると <code>&lt;title&gt;</code> 要素の内容がページの説明として使われます。</li>
 <li><code>&lt;body&gt;&lt;/body&gt;</code>: {{htmlelement("body")}} 要素。この中にユーザーがページを訪問した時に表示したいコンテンツ (例えば、テキスト、画像、ビデオ、ゲーム、オーディオトラック等) を記述します。</li>
</ol>

<div class="note">
<p>訳者注: 1. の "doctype" は文書型宣言(DTD)と呼ばれております。 HTML 以外のマークアップ言語(XML, SVG, MathML等)においては今日においても重要な意味を持っています。</p>
</div>

<h3 id="Active_learning_Adding_some_features_to_an_HTML_document" name="Active_learning_Adding_some_features_to_an_HTML_document">実習: HTML 文書をカスタマイズする</h3>

<p>もし HTML 文書を書く練習をローカルコンピューターで試したい場合は、次のようにします。</p>

<ol>
 <li>上記の HTML ページのコードサンプルの全体を選択して「コピー」します。</li>
 <li>テキストエディタ上で新規ファイルを作成します。</li>
 <li>新規テキストファイルの中で「貼り付け」、または「ペースト」します。</li>
 <li><code>index.html</code> という名前でファイルを保存します。</li>
</ol>

<div class="note">
<p><strong>脚注</strong>: 元となる HTML テンプレートは <a href="https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html">MDN ラーニングエリア GitHub リポジトリ </a>にも置いてあります。</p>
</div>

<p>ウェブブラウザーでこのファイルを開くとレンダリングされた HTML 文書が表示されます。コードを編集した場合は、ブラウザー上でページの更新 (または、再読み込み) を行うと編集結果が反映されます。最初はこんな表示です。</p>

<p><img alt="A simple HTML page that says This is my page" src="https://mdn.mozillademos.org/files/12279/template-screenshot.png" style="display: block; height: 365px; margin: 0px auto; width: 595px;">この実習では、 上に示したようにあなたのコンピューター内部でコード編集してもいいですが、この節の下の方に編集できるフォーム (Input, Output と付されているものです) を使うこともできます。スマートフォンなどで学習する際はこのフォームが役に立つと思います。この節のフォームの Input の部分は、 {{htmlelement("body")}} 要素の中身を表しています。以下の手順を踏んで、ページをカスタマイズしてみましょう。</p>

<div class="note">
<p>訳者注: 下記の演習項目は後で詳しく学習できますので、できなくても構いません。</p>
</div>

<ul>
 <li>{{htmlelement("body")}} 要素の開始タグ以降にページのメインタイトルを書きます。このメインタイトルは  <code>&lt;h1&gt;</code> 開始タグと <code>&lt;/h1&gt;</code> 終了タグで囲みます。ちなみにこれは <code>head</code> 要素の中に記述する <code>title</code> 要素とは異なります。実際にやってみると理解できると思います。フォームで編集する場合はすでに <code>body</code> 要素の中なので、コードの先頭にメインタイトルを記述する形になります。</li>
 <li>すでに<code>&lt;p&gt;</code>要素が記述されていますので、その段落を好きな内容にしてみましょう。また、新しい段落を好きなように追加してみましょう。</li>
 <li>段落 (<code>&lt;p&gt;</code>要素) 内で重要な言葉は <code>&lt;strong&gt;</code> 開始タグと <code>&lt;/strong&gt;</code> 終了タグで囲んで太字で強調しましょう。 </li>
 <li><a href="/ja/Learn/HTML/Introduction_to_HTML/Getting_started#Active_learning_Adding_attributes_to_an_element">この記事の前半あたり</a>で説明したリンクを段落のどれかに張ってみましょう。</li>
 <li><a href="/ja/Learn/HTML/Introduction_to_HTML/Getting_started#Empty_elements">この記事の前半あたり</a>で説明した方法を使って、段落の下に画像を挿入しましょう。説明では Firefox のロゴ画像を使用しましたが、他の画像を持ってくることにチャレンジしてもいいと思います。自分のコンピューターの中のファイルやウェブ上のどこか他の場所にある画像リンクといったものです。</li>
</ul>

<p>間違えた場合は <em>Reset</em> ボタンを押すことで元に戻すことができます。分からない場合は Show solution ボタンを押して答えを見てみましょう。</p>

<div class="hidden">
<h6 id="Playable_code3" name="Playable_code3">Playable code3</h6>

<pre class="brush: html line-numbers  language-html"><code class="language-html"><span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Live output<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>output<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">50</span>px<span class="punctuation token">;</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>h2</span><span class="punctuation token">&gt;</span></span>Editable code<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>h2</span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>p</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>a11y-label<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>Press Esc to move focus away from the code area (Tab inserts a tab character).<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>p</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>textarea</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>code<span class="punctuation token">"</span></span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>input<span class="punctuation token">"</span></span><span class="language-css style-attr token"><span class="attr-name token"> <span class="attr-name token">style</span></span><span class="punctuation token">="</span><span class="attr-value token"><span class="property token">min-height</span><span class="punctuation token">:</span> <span class="number token">100</span>px<span class="punctuation token">;</span><span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">95%</span></span><span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="entity token" title="&lt;">&amp;lt;</span>p<span class="entity token" title=">">&amp;gt;</span>This is my page<span class="entity token" title="&lt;">&amp;lt;</span>/p<span class="entity token" title=">">&amp;gt;</span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>textarea</span><span class="punctuation token">&gt;</span></span>

<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>div</span> <span class="attr-name token">class</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>playable-buttons<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>reset<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Reset<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
  <span class="tag token"><span class="tag token"><span class="punctuation token">&lt;</span>input</span> <span class="attr-name token">id</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>solution<span class="punctuation token">"</span></span> <span class="attr-name token">type</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>button<span class="punctuation token">"</span></span> <span class="attr-name token">value</span><span class="attr-value token"><span class="punctuation token">=</span><span class="punctuation token">"</span>Show solution<span class="punctuation token">"</span></span><span class="punctuation token">&gt;</span></span>
<span class="tag token"><span class="tag token"><span class="punctuation token">&lt;/</span>div</span><span class="punctuation token">&gt;</span></span></code></pre>

<pre class="brush: css line-numbers  language-css"><code class="language-css"><span class="selector token">html </span><span class="punctuation token">{</span>
  <span class="property token">font-family</span><span class="punctuation token">:</span> sans-serif<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">h2 </span><span class="punctuation token">{</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">16</span>px<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token"><span class="class token">.a11y-label</span> </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">0</span><span class="punctuation token">;</span>
  <span class="property token">text-align</span><span class="punctuation token">:</span> right<span class="punctuation token">;</span>
  <span class="property token">font-size</span><span class="punctuation token">:</span> <span class="number token">0.7</span>rem<span class="punctuation token">;</span>
  <span class="property token">width</span><span class="punctuation token">:</span> <span class="number token">98%</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">img </span><span class="punctuation token">{</span>
  <span class="property token">max-width</span><span class="punctuation token">:</span> <span class="number token">100%</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="selector token">body </span><span class="punctuation token">{</span>
  <span class="property token">margin</span><span class="punctuation token">:</span> <span class="number token">10</span>px<span class="punctuation token">;</span>
  <span class="property token">background</span><span class="punctuation token">:</span> <span class="hexcode token">#f5f9fa</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span></code></pre>

<pre class="brush: js line-numbers  language-js"><code class="language-js"><span class="keyword token">var</span> textarea <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'code'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> reset <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'reset'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solution <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">getElementById</span><span class="punctuation token">(</span><span class="string token">'solution'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> output <span class="operator token">=</span> document<span class="punctuation token">.</span><span class="function token">querySelector</span><span class="punctuation token">(</span><span class="string token">'.output'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> code <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="keyword token">var</span> userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  output<span class="punctuation token">.</span>innerHTML <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

reset<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> code<span class="punctuation token">;</span>
  userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>
  solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

solution<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'click'</span><span class="punctuation token">,</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> solutionEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Hide solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> userEntry<span class="punctuation token">;</span>
    solution<span class="punctuation token">.</span>value <span class="operator token">=</span> <span class="string token">'Show solution'</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="keyword token">var</span> htmlSolution <span class="operator token">=</span> <span class="string token">'&lt;p&gt;I really enjoy &lt;strong&gt;playing the drums&lt;/strong&gt;. One of my favourite drummers is Neal Peart, who\ plays in the band &lt;a href="https://en.wikipedia.org/wiki/Rush_%28band%29" title="Rush Wikipedia article"&gt;Rush&lt;/a&gt;.\ My favourite Rush album is currently &lt;a href="http://www.deezer.com/album/942295"&gt;Moving Pictures&lt;/a&gt;.&lt;/p&gt;\ &lt;img src="http://www.cygnus-x1.net/links/rush/images/albums/sectors/sector2-movingpictures-cover-s.jpg"&gt;'</span><span class="punctuation token">;</span>
<span class="keyword token">var</span> solutionEntry <span class="operator token">=</span> htmlSolution<span class="punctuation token">;</span>

textarea<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'input'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>
window<span class="punctuation token">.</span><span class="function token">addEventListener</span><span class="punctuation token">(</span><span class="string token">'load'</span><span class="punctuation token">,</span> updateCode<span class="punctuation token">)</span><span class="punctuation token">;</span>

<span class="comment token">// stop tab key tabbing out of textarea and</span>
<span class="comment token">// make it write a tab at the caret position instead</span>

textarea<span class="punctuation token">.</span>onkeydown <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span>e<span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">9</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    e<span class="punctuation token">.</span><span class="function token">preventDefault</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
    <span class="function token">insertAtCaret</span><span class="punctuation token">(</span><span class="string token">'\t'</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="keyword token">if</span> <span class="punctuation token">(</span>e<span class="punctuation token">.</span>keyCode <span class="operator token">===</span> <span class="number token">27</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    textarea<span class="punctuation token">.</span><span class="function token">blur</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="punctuation token">}</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span>

<span class="keyword token">function</span> <span class="function token">insertAtCaret</span><span class="punctuation token">(</span>text<span class="punctuation token">)</span> <span class="punctuation token">{</span>
  <span class="keyword token">var</span> scrollPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>scrollTop<span class="punctuation token">;</span>
  <span class="keyword token">var</span> caretPos <span class="operator token">=</span> textarea<span class="punctuation token">.</span>selectionStart<span class="punctuation token">;</span>

  <span class="keyword token">var</span> front <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span><span class="number token">0</span><span class="punctuation token">,</span> caretPos<span class="punctuation token">)</span><span class="punctuation token">;</span>
  <span class="keyword token">var</span> back <span class="operator token">=</span> <span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>value<span class="punctuation token">)</span><span class="punctuation token">.</span><span class="function token">substring</span><span class="punctuation token">(</span>textarea<span class="punctuation token">.</span>selectionEnd<span class="punctuation token">,</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">.</span>length<span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>value <span class="operator token">=</span> front <span class="operator token">+</span> text <span class="operator token">+</span> back<span class="punctuation token">;</span>
  caretPos <span class="operator token">=</span> caretPos <span class="operator token">+</span> text<span class="punctuation token">.</span>length<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionStart <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>selectionEnd <span class="operator token">=</span> caretPos<span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span><span class="function token">focus</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
  textarea<span class="punctuation token">.</span>scrollTop <span class="operator token">=</span> scrollPos<span class="punctuation token">;</span>
<span class="punctuation token">}</span>

<span class="comment token">// Update the saved userCode every time the user updates the text area code</span>

textarea<span class="punctuation token">.</span>onkeyup <span class="operator token">=</span> <span class="keyword token">function</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">{</span>
  <span class="comment token">// We only want to save the state when the user code is being shown,</span>
  <span class="comment token">// not the solution, so that solution is not saved over the user code</span>
  <span class="keyword token">if</span><span class="punctuation token">(</span>solution<span class="punctuation token">.</span>value <span class="operator token">===</span> <span class="string token">'Show solution'</span><span class="punctuation token">)</span> <span class="punctuation token">{</span>
    userEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span> <span class="keyword token">else</span> <span class="punctuation token">{</span>
    solutionEntry <span class="operator token">=</span> textarea<span class="punctuation token">.</span>value<span class="punctuation token">;</span>
  <span class="punctuation token">}</span>

  <span class="function token">updateCode</span><span class="punctuation token">(</span><span class="punctuation token">)</span><span class="punctuation token">;</span>
<span class="punctuation token">}</span><span class="punctuation token">;</span></code></pre>
</div>

<p>{{ EmbedLiveSample('Playable_code3', 700, 360, "", "", "hide-codepen-jsfiddle") }}</p>

<h3 id="Whitespace_in_HTML" name="Whitespace_in_HTML">HTML 内の空白</h3>

<p>上記の例において、大量の半角スペースが挿入されていることに気づいたかもしれません。大量の半角スペースはあっても無くても構わないものです。次の２つのコードスニペット (それ単体では動作しないコード例のこと) は等価です。</p>

<pre class="brush: html">&lt;p&gt;Dogs are silly.&lt;/p&gt;

&lt;p&gt;Dogs        are
         silly.&lt;/p&gt;</pre>

<p>半角スペースをどれ程入力しても (そして、どれ程改行しても)、 HTML パーサはそれを１つの半角スペースとして認識します。ではどうして半角スペースを沢山入力するのでしょうか。それは HTML コードの可読性を向上させるためです。 HTML のコードがいいフォーマット(書式)で記述されていて、１行の中に沢山タグをゴチャゴチャに詰め込まなければ、そのコードの中がどうなっているかが分かりやすくなります。この記事ではインデント(字下げ)として半角スペース２文字分を挿入しています。 HTML のフォーマット(例えば、インデントとして半角スペース何文字分を挿入するのか等)については HTML の書き手によって様々ですが、フォーマットを意識して記述しなければなりません。</p>

<div class="warning">
<p>訳者注: 全角スペースは、 HTML の文法としては半角スペースや改行とは全く異なる扱いになるので、全角スペースを用いてインデントを行ったりしないでください。また、日本語の文章を段落要素<code>&lt;p&gt;</code>の中で改行すると、半角スペースが挿入されます。</p>

<pre>&lt;p&gt;私は日本人です。
四季を好みます。&lt;/p&gt;</pre>

<p>従って、段落要素(<code>&lt;p&gt;</code>)の中では一切改行はしないでください。ただ、長い文章では段落要素の中身が横に長くなってしまいます。その場合は、テキストエディタで「右端で折り返す」などの設定を行ってみてください。</p>

<pre>&lt;p&gt;私は日本人です。四季を好みます。&lt;/p&gt;</pre>

<p>段落要素の中で改行したい場合は、改行要素<code>&lt;br&gt;</code>を用います(文章内の会話や、詩などに用います)。</p>

<pre>&lt;p&gt;彼は言いました。&lt;br&gt;
「私は日本人です。四季を好みます。」&lt;br&gt;
私は彼の発した突然の一言にはっと驚きました。&lt;/p&gt;</pre>
</div>

<h2 id="Entity_references_Including_special_characters_in_HTML" name="Entity_references_Including_special_characters_in_HTML">実体参照: HTML に特殊文字を含める</h2>

<div class="note">
<p>訳者注: HTML エンティティ、実体参照、文字参照、文字実体参照、は、それぞれほぼ同じ意味で用いられます。</p>
</div>

<p>HTML では<code>&lt;</code>、<code>&gt;</code>、<code>"</code>、<code>'</code>、<code>&amp;</code>の５つの文字は特殊文字と呼ばれています。これら５つの文字は HTML の文法自身の一部です。ではこれらの文字そのものを組版したい場合はどうすればいいのでしょうか。例えば「 You &amp; Me 」や「 x &lt; y 」等の表記をしたい場合です。</p>

<p>そのような場合は、「文字参照」を使用する必要があります。文字参照とは「文字を表す特別なコード」のことであり、これを使うことで正確な組版を行うことができます。文字参照は必ずアンパサンド (&amp;) で始まり、セミコロン(;)で終わります。</p>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">実際の文字</th>
   <th scope="col">等価な文字参照</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>&lt;</td>
   <td>&amp;lt;</td>
  </tr>
  <tr>
   <td>&gt;</td>
   <td>&amp;gt;</td>
  </tr>
  <tr>
   <td>"</td>
   <td>&amp;quot;</td>
  </tr>
  <tr>
   <td>'</td>
   <td>&amp;apos;</td>
  </tr>
  <tr>
   <td>&amp;</td>
   <td>&amp;amp;</td>
  </tr>
 </tbody>
</table>

<p>次の例では Web 技術について記述している段落要素を２つ並べています。</p>

<pre class="brush: html">&lt;p&gt;HTML では、&lt;p&gt;要素で段落を定義します。&lt;/p&gt;

&lt;p&gt;HTML では、&amp;lt;p&amp;gt;要素で段落を定義します。&lt;/p&gt;
</pre>

<p>上記の例をブラウザーに解釈させたものを下記に出力しています。１つ目の段落の出力が間違っていることが分かるかと思います。2 つ目の <code>&lt;p&gt;</code> を新しい段落の始まりとして認識しているためです。２つ目の段落は正しく出力されています。山括弧(<code>&lt;</code>、<code>&gt;</code>)を文字参照に置き換えているためです。</p>

<p>{{ EmbedLiveSample('Entity_references_Including_special_characters_in_HTML', 700, 200, "", "", "hide-codepen-jsfiddle") }}</p>

<div class="note">
<p>脚注: HTML で使用することのできる文字実体参照のリストはこの Wikipedia の記事で確認することができます: <a class="external text" href="http://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references" rel="nofollow">List of XML and HTML character entity references</a>.</p>
</div>

<h2 id="HTML_comments" name="HTML_comments">HTML におけるコメント</h2>

<p>大抵のプログラミング言語同様、HTML においてもコード内にコメントを書くことができます。コメントはブラウザーによって無視されるので、組版には反映されません。コメントの目的としては、 HTML コードがどのように動作するのかや、コードの別の部分がどのように動作するのかを述べるることできます。コメントは、 HTML のコードを書いて半年以上経ってから自分で見返して、自分が何をしたのかを思い出すことができない時に大変有用となります。また、自分のコードを他の人に読んでもらう時にも有用です。</p>

<p>HTML ファイル内の一部をコメントにするには、その箇所を特別なマーカーの <code>&lt;!--</code> と <code>--&gt;</code> で囲みます。例えば次のような感じです。</p>

<pre class="brush: html">&lt;p&gt;私はコメントの外にいます。&lt;/p&gt;

&lt;!-- &lt;p&gt;私はコメントの中にいます。&lt;/p&gt; --&gt;</pre>

<p>下記を見ると、最初の段落は表示されますが、次の段落は表示されないことが分かります。</p>

<p>{{ EmbedLiveSample('HTML_comments', 700, 100) }}</p>

<h2 id="Summary" name="Summary">要約</h2>

<p>この記事の最後にたどり着きました — HTML のほんの初歩のツアーを楽しんでこられたことを望んでいます！ここではこの言語がどのようなものか、基本的にどうやって動作するのかを理解し、いくつかの要素と属性を書くことができるようになったでしょう。あなたがいる場所は完璧な場所です、続きの記事ではすでに見てきたことをもっと詳細に経験して、いくつか新しい言語機能を紹介します。引き続き注目！</p>

<div class="note">
<p><strong>脚注</strong>: さて、 HTML についてより深く学習するために <a href="/ja/docs/Learn/CSS">CSS</a> (Cascading Style Sheets)の基礎についても理解しておきましょう。 CSS はウェブページのスタイルをカスタマイズするために使用します。具体的には、テキストのフォントや色を変えたり、ページレイアウトを設定したりといったことがあげられます。 HTML と CSS は相互補完、つまり２つで１つです。両方学習するとすぐ気づくでしょう。</p>
</div>

<h2 id="See_also" name="See_also">関連情報</h2>

<ul>
 <li><a href="/ja/docs/Web/HTML/Applying_color">CSS を使って HTML要素に色をつける</a></li>
</ul>

<div>{{NextMenu("Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML", "Learn/HTML/Introduction_to_HTML")}}</div>

<h2 id="In_this_module" name="In_this_module">このモジュール内</h2>

<ul>
 <li><a href="/ja/docs/Learn/HTML/Introduction_to_HTML/Getting_started">HTML 入門</a></li>
 <li><a href="/ja/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML">Head とは？HTML のメタデータ</a></li>
 <li><a href="/ja/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals">HTML テキストの基礎</a></li>
 <li><a href="/ja/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks">ハイパーリンクを作成する</a></li>
 <li><a class="new" href="/ja/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting" rel="nofollow">上級のテキスト整形</a></li>
 <li><a class="new" href="/ja/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure" rel="nofollow">ドキュメントとウェブサイトの構造</a></li>
 <li><a class="new" href="/ja/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML" rel="nofollow">HTML をデバッグする</a></li>
 <li><a class="new" href="/ja/docs/Learn/HTML/Introduction_to_HTML/Marking_up_a_letter" rel="nofollow">手紙をマークアップする</a></li>
 <li><a class="new" href="/ja/docs/Learn/HTML/Introduction_to_HTML/Structuring_a_page_of_content" rel="nofollow">コンテンツページを構造化する</a></li>
</ul>