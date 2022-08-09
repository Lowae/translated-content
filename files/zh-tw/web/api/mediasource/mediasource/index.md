---
title: MediaSource.MediaSource()
slug: Web/API/MediaSource/MediaSource
translation_of: Web/API/MediaSource/MediaSource
---
<div>{{APIRef("Media Source Extensions")}}{{SeeCompatTable}}</div>

<p>{{domxref("MediaSource")}} 介面的 <code><strong>MediaSource()</strong></code> 建構子建構且回傳一個沒有與任何來源緩衝 (source buffer) 關聯的新 <code>MediaSource</code> 物件。</p>

<h2 id="語法">語法</h2>

<pre class="brush: js">var mediaSource = new MediaSource();</pre>

<h3 id="參數">參數</h3>

<p>無。</p>

<h2 id="範例">範例</h2>

<p>以下的片段擷取自 Nick Desaulniers 所編纂的簡單範例（<a href="http://nickdesaulniers.github.io/netfix/demo/bufferAll.html">觀看實際演示</a>，或者<a href="https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html">下載原始碼</a> 以利更進一步研究。）</p>

<pre class="brush: js">var video = document.querySelector('video');

var assetURL = 'frag_bunny.mp4';
// Need to be specific for Blink regarding codecs
// ./mp4info frag_bunny.mp4 | grep Codec
var mimeCodec = 'video/mp4; codecs="avc1.42E01E, mp4a.40.2"';

if ('MediaSource' in window &amp;&amp; MediaSource.isTypeSupported(mimeCodec)) {
  var mediaSource = new MediaSource;
  //console.log(mediaSource.readyState); // closed
  video.src = URL.createObjectURL(mediaSource);
  mediaSource.addEventListener('sourceopen', sourceOpen);
} else {
  console.error('Unsupported MIME type or codec: ', mimeCodec);
}

...
</pre>

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat}}

<h2 id="相關資料">相關資料</h2>

<ul>
 <li>{{domxref("SourceBuffer")}}</li>
 <li>{{domxref("SourceBufferList")}}</li>
</ul>