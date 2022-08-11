---
title: width
slug: Web/SVG/Attribute/width
tags:
  - SVG
  - SVG 属性
  - 需要兼容性表
translation_of: Web/SVG/Attribute/width
---
<p>« <a href="/en/SVG/Attribute">SVG 属性参考主页</a></p>

<p>该属性在用户坐标系统中标识了一个水平长度。该坐标的确切效果依赖于每个元素。大多数时候，它体现引用元素的矩形区域的宽度（请阅读每个元素的文档以了解例外情况）。</p>

<p>除了<code>&lt;svg&gt;</code>元素之外，别的元素都必须指定该属性，<code>&lt;svg&gt;</code>的宽度默认是<strong>100%</strong>，而<code>&lt;filter&gt;</code>元素以及<code>&lt;mask&gt;</code>元素的默认宽度是<strong>120%</strong>。</p>

<h2 id="用法">用法</h2>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">类别</th>
   <td>无</td>
  </tr>
  <tr>
   <th scope="row">值</th>
   <td><a href="/en/SVG/Content_type#Length">&lt;length&gt;</a></td>
  </tr>
  <tr>
   <th scope="row">可变性</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<p>{{ page("/zh-CN/docs/Web/SVG/Content_type","长度") }}</p>

<h2 id="元素">元素</h2>

<p>下列元素可以使用<code>width</code>属性：</p>

<ul>
 <li><a href="/en/SVG/Element#FilterPrimitive">滤镜元素</a> »</li>
 <li>{{ SVGElement("filter") }}</li>
 <li>{{ SVGElement("foreignObject") }}</li>
 <li>{{ SVGElement("image") }}</li>
 <li>{{ SVGElement("pattern") }}</li>
 <li>{{ SVGElement("rect") }}</li>
 <li>{{ SVGElement("svg") }}</li>
 <li>{{ SVGElement("use") }}</li>
 <li>{{ SVGElement("mask") }}</li>
</ul>

<h2 id="规范">规范</h2>

{{Specifications}}