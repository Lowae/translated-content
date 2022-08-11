---
title: cy
slug: Web/SVG/Attribute/cy
tags:
  - SVG
  - SVG 属性
translation_of: Web/SVG/Attribute/cy
---
<div>{{SVGRef}}</div>

<p><strong><code>cy</code></strong> 属性定义一个中心点的 y 轴坐标。</p>

<p>有三个元素在使用此属性：{{SVGElement("circle")}}，{{SVGElement("ellipse")}} 和 {{SVGElement("radialGradient")}}</p>

<h2>示例</h2>

<pre class="brush: css hidden">html,body,svg { height:100% }</pre>

<pre class="brush: html">&lt;svg viewBox="0 0 100 300" xmlns="http://www.w3.org/2000/svg"&gt;
  &lt;radialGradient cy="25%" id="myGradient"&gt;
    &lt;stop offset="0"    stop-color="white" /&gt;
    &lt;stop offset="100%" stop-color="black" /&gt;
  &lt;/radialGradient&gt;

  &lt;circle  cy="50"  cx="50" r="45"/&gt;
  &lt;ellipse cy="150" cx="50" rx="45" ry="25" /&gt;
  &lt;rect x="5" y="205" width="90" height="90" fill="url(#myGradient)" /&gt;
&lt;/svg&gt;</pre>

<p>{{EmbedLiveSample('示例', '100%', 300)}}</p>

<h2 id="圆">圆</h2>

<p>对于 {{SVGElement('circle')}}，<code>cy</code> 用来定义图形中心的 y 轴坐标。</p>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">值</th>
   <td><strong><a href="/docs/Web/SVG/Content_type#Length">&lt;length&gt;</a></strong> | <strong><a href="/docs/Web/SVG/Content_type#Percentage">&lt;percentage&gt;</a></strong></td>
  </tr>
  <tr>
   <th scope="row">默认值</th>
   <td><code>0</code></td>
  </tr>
  <tr>
   <th scope="row">可变性</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<p><strong>注：</strong>起始于 SVG2，<code>cy</code> 是一个几何属性，意味着该属性也可以用作圆的 CSS 属性。</p>

<h2 id="椭圆">椭圆</h2>

<p>对于 {{SVGElement('ellipse')}}，<code>cy</code> 用来定义图形中心的 y 轴坐标。</p>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">值</th>
   <td><strong><a href="/docs/Web/SVG/Content_type#Length">&lt;length&gt;</a></strong> | <strong><a href="/docs/Web/SVG/Content_type#Percentage">&lt;percentage&gt;</a></strong></td>
  </tr>
  <tr>
   <th scope="row">默认值</th>
   <td><code>0</code></td>
  </tr>
  <tr>
   <th scope="row">可变性</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<p><strong>注：</strong>起始于 SVG2，<code>cy</code> 是一个几何属性，意味着该属性也可以用作椭圆的 CSS 属性。</p>

<h2 id="径向渐变">径向渐变</h2>

<p>对于 {{SVGElement('radialGradient')}}，<code>cy</code> 用来定义径向渐变终止圆的 y 轴坐标。</p>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">值</th>
   <td><strong><a href="/docs/Web/SVG/Content_type#Length">&lt;length&gt;</a></strong></td>
  </tr>
  <tr>
   <th scope="row">默认值</th>
   <td><code>50%</code></td>
  </tr>
  <tr>
   <th scope="row">可变性</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<h4 id="示例">示例</h4>

<pre class="brush: css hidden">html,body,svg { height:100% }</pre>

<pre class="brush: html">&lt;svg viewBox="0 0 34 10" xmlns="http://www.w3.org/2000/svg"&gt;
  &lt;defs&gt;
    &lt;radialGradient cy="0" id="myGradient000"&gt;
      &lt;stop offset="0%"   stop-color="gold" /&gt;
      &lt;stop offset="50%"  stop-color="green" /&gt;
      &lt;stop offset="100%" stop-color="white" /&gt;
    &lt;/radialGradient&gt;

    &lt;radialGradient cy="50%" id="myGradient050"&gt;
      &lt;stop offset="0%"   stop-color="gold" /&gt;
      &lt;stop offset="50%"  stop-color="green" /&gt;
      &lt;stop offset="100%" stop-color="white" /&gt;
    &lt;/radialGradient&gt;

    &lt;radialGradient cy="100%" id="myGradient100"&gt;
      &lt;stop offset="0%"   stop-color="gold" /&gt;
      &lt;stop offset="50%"  stop-color="green" /&gt;
      &lt;stop offset="100%" stop-color="white" /&gt;
    &lt;/radialGradient&gt;
  &lt;/defs&gt;

  &lt;rect x="1"  y="1" width="8" height="8" fill="url(#myGradient000)" stroke="black" /&gt;
  &lt;rect x="13" y="1" width="8" height="8" fill="url(#myGradient050)" stroke="black" /&gt;
  &lt;rect x="25" y="1" width="8" height="8" fill="url(#myGradient100)" stroke="black" /&gt;
&lt;/svg&gt;</pre>

<p>{{EmbedLiveSample('径向渐变', 150, '100%')}}</p>

<h2 id="规范">规范</h2>

{{Specifications}}