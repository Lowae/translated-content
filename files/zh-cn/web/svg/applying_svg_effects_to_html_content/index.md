---
title: 在 HTML 内容中应用 SVG 效果
slug: Web/SVG/Applying_SVG_effects_to_HTML_content
tags:
  - CSS
  - HTML
  - SVG
  - XHTML
  - 指南
  - 需要示例
translation_of: Web/SVG/Applying_SVG_effects_to_HTML_content
---
<p>现代浏览器支持在 <a href="/en-US/docs/Web/CSS">CSS</a> 样式中使用 <a href="/en-US/docs/SVG">SVG</a> 来对 HTML 内容应用图像效果。</p>

<p>你可以在同一文件中使用 SVG 样式，也可以通过外部样式表引入。有三个属性可以使用： <a href="/en-US/docs/Web/CSS/mask"><code>mask</code></a>, <a href="/en-US/docs/Web/CSS/clip-path"><code>clip-path</code></a>, 和 <code><a href="/en-US/docs/Web/CSS/filter">filter</a>。</code></p>

<div class="note"><strong>备注：</strong> 在外部文件引入的 SVG 必须与原始文件 <a href="/en-US/docs/Web/Security/Same-origin_policy">同源</a> 。</div>

<h2 id="使用内嵌SVG">使用内嵌 SVG</h2>

<p>要想在 CSS 样式中应用 SVG 效果，首先需要创建一个引用 SVG 的 CSS 样式。</p>

<pre class="brush: html notranslate">&lt;style&gt;p { mask: url(#my-mask); }&lt;/style&gt;</pre>

<p>在上面的例子中，所有段落会被<a href="/en-US/docs/Web/HTML/Global_attributes/id">ID</a> 为<code>my-mask 的</code><a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask">SVG <code>&lt;mask&gt;</code></a>遮罩。</p>

<h3 id="例子_Masking">示例：Masking</h3>

<p>例如，你可以在你的 HTML 文档中用 SVG 和 CSS 代码对 HTML 内容作渐变 mask 效果。</p>

<pre class="brush: html notranslate">&lt;svg height="0"&gt;
  &lt;mask id="mask-1"&gt;
    &lt;linearGradient id="gradient-1" y2="1"&gt;
      &lt;stop stop-color="white" offset="0"/&gt;
      &lt;stop stop-opacity="0" offset="1"/&gt;
    &lt;/linearGradient&gt;
    &lt;circle cx="0.25" cy="0.25" r="0.25" id="circle" fill="white"/&gt;
    &lt;rect x="0.5" y="0.2" width="300" height="100" fill="url(#gradient-1)"/&gt;
  &lt;/mask&gt;
&lt;/svg&gt;
</pre>

<pre class="brush: css notranslate">.target {
  mask: url(#mask-1);
}
p {
  width: 300px;
  border: 1px solid #000;
  display: inline-block;
}</pre>

<p>注意，在 CSS 中 遮罩（mask）使用一个指向 ID 为 <code>#mask-1</code>的 URL，这个 ID 是在上面的 SVG 中指定的。 SVG 中其他的内容指定了渐变遮罩的细节。</p>

<p>将 SVG 效果应用于 (X)HTML 是通过将 <code>target</code> 这个 class 应用于其他元素来实现的，如下所示：</p>

<pre class="brush: html notranslate">&lt;p class="target" style="background:lime;"&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua. Ut enim ad minim veniam.
&lt;/p&gt;
&lt;p&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing
    &lt;b class="target"&gt;elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua.&lt;/b&gt;
    Ut enim ad minim veniam.
&lt;/p&gt;
</pre>

<p>上面的示例将渲染出一个有遮罩的例子</p>

<p>{{EmbedLiveSample('示例：Masking', 650, 200)}}</p>

<h3 id="例子_Clipping">示例：Clipping</h3>

<p>此示例演示如何使用 SVG 剪辑 HTML 内容。请注意，即使链接的可点击区域也被剪切。</p>

<pre class="brush: html notranslate">&lt;p class="target" style="background:lime;"&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua. Ut enim ad minim veniam.
&lt;/p&gt;
&lt;p&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing
    &lt;b class="target"&gt;elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua.&lt;/b&gt;
    Ut enim ad minim veniam.
&lt;/p&gt;

&lt;button onclick="toggleRadius()"&gt;Toggle radius&lt;/button&gt;

&lt;svg height="0"&gt;
  &lt;clipPath id="clipping-path-1" clipPathUnits="objectBoundingBox"&gt;
    &lt;circle cx="0.25" cy="0.25" r="0.25" id="circle"/&gt;
    &lt;rect x="0.5" y="0.2" width="0.5" height="0.8"/&gt;
  &lt;/clipPath&gt;
&lt;/svg&gt;
</pre>

<pre class="brush: css notranslate">.target {
  clip-path: url(#clipping-path-1);
}
p {
  width: 300px;
  border: 1px solid #000;
  display: inline-block;
}</pre>

<p>这个例子将建立一个由圆形和矩形组成的剪切区域，为其指定 ID <code>#clipping-path-1</code>，然后在 CSS 中引用它。剪切路径可以分配给具有 <code>target</code> class 的任何元素。</p>

<p>你可以实时地对 SVG 进行更改，并看到它们立即影响 HTML 的渲染。例如，可以在上面建立的剪切路径中调整圆形的大小：</p>

<pre class="brush: js notranslate">function toggleRadius() {
  var circle = document.getElementById("circle");
  circle.r.baseVal.value = 0.40 - circle.r.baseVal.value;
}
</pre>

<p>{{EmbedLiveSample('示例：Clipping', 650, 200)}}</p>

<h3 id="例子_Filtering">示例：Filtering</h3>

<p>这个例子演示了如何使用 SVG 对 HTML 内容进行过滤。它建立了几个过滤器，这些过滤器与 CSS 一起作用于正常和鼠标悬停状态 <a href="/en-US/docs/Web/CSS/:hover">hover</a> 下的三个元素。</p>

<pre class="brush: html notranslate">&lt;p class="target" style="background: lime;"&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua. Ut enim ad minim veniam.
&lt;/p&gt;
&lt;pre class="target"&gt;lorem&lt;/pre&gt;
&lt;p&gt;
    Lorem ipsum dolor sit amet, consectetur adipisicing
    &lt;b class="target"&gt;elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua.&lt;/b&gt;
    Ut enim ad minim veniam.
&lt;/p&gt;
</pre>

<p>任何 SVG 过滤器都可以这样使用。例如，要应用模糊效果，你可以这样使用：</p>

<pre class="brush: html notranslate">&lt;svg height="0"&gt;
  &lt;filter id="f1"&gt;
    &lt;feGaussianBlur stdDeviation="3"/&gt;
  &lt;/filter&gt;
&lt;/svg&gt;</pre>

<p>也可以应用于颜色矩阵：</p>

<pre class="brush: html notranslate">&lt;svg height="0"&gt;
  &lt;filter id="f2"&gt;
    &lt;feColorMatrix values="0.3333 0.3333 0.3333 0 0
                           0.3333 0.3333 0.3333 0 0
                           0.3333 0.3333 0.3333 0 0
                           0      0      0      1 0"/&gt;
  &lt;/filter&gt;
&lt;/svg&gt;
</pre>

<p>或更多的过滤器：</p>

<pre class="brush: html notranslate">&lt;svg height="0"&gt;
  &lt;filter id="f3"&gt;
    &lt;feConvolveMatrix filterRes="100 100" style="color-interpolation-filters:sRGB"
      order="3" kernelMatrix="0 -1 0   -1 4 -1   0 -1 0" preserveAlpha="true"/&gt;
  &lt;/filter&gt;
  &lt;filter id="f4"&gt;
    &lt;feSpecularLighting surfaceScale="5" specularConstant="1"
                        specularExponent="10" lighting-color="white"&gt;
      &lt;fePointLight x="-5000" y="-10000" z="20000"/&gt;
    &lt;/feSpecularLighting&gt;
  &lt;/filter&gt;
  &lt;filter id="f5"&gt;
    &lt;feColorMatrix values="1 0 0 0 0
                           0 1 0 0 0
                           0 0 1 0 0
                           0 1 0 0 0" style="color-interpolation-filters:sRGB"/&gt;
  &lt;/filter&gt;
&lt;/svg&gt;</pre>

<p>使用以下 CSS 应用五个过滤器：</p>

<pre class="brush: css notranslate">p.target { filter:url(#f3); }
p.target:hover { filter:url(#f5); }
b.target { filter:url(#f1); }
b.target:hover { filter:url(#f4); }
pre.target { filter:url(#f2); }
pre.target:hover { filter:url(#f3); }
</pre>

<p>{{EmbedLiveSample('示例：Filtering', 650, 200)}}</p>

<p><a href="/files/3329/filterdemo.xhtml">View this example live</a></p>

<h3 id="例子_Blurred_Text">示例：Blurred Text</h3>

<p>为了模糊文本，基于 Webkit 的浏览器有一个名为 blur 的（前缀）CSS 过滤器，（另见 <a href="/en-US/docs/Web/CSS/filter#blur%28%29_2">CSS filter</a>）。你可以使用 SVG 过滤器获得相同的效果。</p>

<pre class="brush: html notranslate">&lt;p class="blur"&gt;Time to clean my glasses&lt;/p&gt;
&lt;svg height="0"&gt;
  &lt;defs&gt;
    &lt;filter id="wherearemyglasses" x="0" y="0"&gt;
    &lt;feGaussianBlur in="SourceGraphic" stdDeviation="1"/&gt;
    &lt;/filter&gt;
  &lt;/defs&gt;
&lt;/svg&gt;
</pre>

<p>你可以在同一个 class 中使用 SVG 和 CSS 过滤器：</p>

<pre class="brush: css notranslate">.blur { filter: url(#wherearemyglasses); }</pre>

<p>{{ EmbedLiveSample('示例：Blurred Text', 300, 100) }}</p>

<p>模糊的计算量很大，所以请谨慎使用它，尤其是在包含滚动或动画的元素中。</p>

<h3 id="例子_Text_Effects">示例：Text Effects</h3>

<p>SVG 还可以用于添加比纯 HTML 文本更动态、更灵活的文本添加方法。</p>

<p>通过使用 SVG 元素与 HTML 结合创建文本，你可以产生不同的文本的效果。如旋转文本：</p>

<pre class="brush: svg">&lt;svg height="60" width="200"&gt;
  &lt;text x="0" y="15" fill="blue" transform="rotate(30 20,50)"&gt;Example text&lt;/text&gt;
&lt;/svg&gt;</pre>

<h2 id="使用外部引用">使用外部引用</h2>

<p>用来 clipping，masking，filtering 的 SVG 可以从其他外部源载入，只要外部源是与要使用 SVG 的该 HTML 文档同源的。</p>

<p>例如，CSS 规则在一个名为 default.css 的文件中，如下这样：</p>

<pre class="brush: css notranslate">.target { clip-path: url(resources.svg#c1); }</pre>

<p>这个 SVG 就可以从一个名为 resources.svg 的文件中导入，clip 路径为 ID c1。</p>

<h2 id="参见">参见</h2>

<ul>
 <li><a href="/en-US/docs/SVG">SVG</a></li>
 <li><a href="http://robert.ocallahan.org/2008/06/applying-svg-effects-to-html-content_04.html">SVG Effects for HTML Content</a> (blog post)</li>
 <li><del><a href="/web-tech/2008/10/10/svg-external-document-references">SVG External Document References</a></del> (blog post) (<a href="http://web.archive.org/web/20120512132948/https://developer.mozilla.org/web-tech/2008/10/10/svg-external-document-references/">[archive.org] Web Tech Blog » Blog Archive » SVG External Document References</a>)</li>
</ul>