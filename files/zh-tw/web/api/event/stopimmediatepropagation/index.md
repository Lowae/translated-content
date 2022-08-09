---
title: Event.stopImmediatePropagation()
slug: Web/API/Event/stopImmediatePropagation
tags:
  - API
  - Event
translation_of: Web/API/Event/stopImmediatePropagation
---
<p>{{APIRef("DOM")}}</p>

<p>除了停止事件繼續捕捉或冒泡傳遞外，也阻止事件被傳入同元素中註冊的其它相同事件類型之監聽器。</p>

<h2 id="Syntax">語法</h2>

<pre class="eval">event.stopImmediatePropagation();
</pre>

<h2 id="Notes">備註</h2>

<p>如果一個元素中註冊了多個相同事件類型的監聽器，監聽器將會按照註冊的先後順序被呼叫。在其中任何一個監聽器執行的期間，若是呼叫了事件物件的 <code>stopImmediatePropagation()</code> 方法，則接下來尚未執行的監聽器皆不會被呼叫。</p>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.Event.stopImmediatePropagation")}}