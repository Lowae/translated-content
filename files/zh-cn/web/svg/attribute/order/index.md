---
title: order
slug: Web/SVG/Attribute/order
translation_of: Web/SVG/Attribute/order
---
<p>« <a href="/en/SVG/Attribute">SVG Attribute reference home</a></p>

<p>order 属性确定被用作{{ SVGElement("feConvolveMatrix") }}元素的矩阵的大小。</p>

<p>提供的值必须是大于 0 的<a href="/en/SVG/Content_type#Integer">&lt;整数&gt;</a>. 第一个值&lt;orderX&gt;,确定矩阵的列数。第二个值&lt;orderY&gt;确定矩阵的行数。如果&lt;orderY&gt;没有指定，那么它的默认值相当于&lt;orderX&gt;的值。</p>

<p>一个典型的值是 order="3". 建议只使用较小的值 (例如 3); 大值可能会导致较高的 CPU 开销而且通常界面上并不能表现出高耗能造成的效果。</p>

<p>如果未指定该属性，则其效果就如同指定值为 3.</p>

<h2 id="Usage_context">Usage context</h2>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">Categories</th>
   <td>None</td>
  </tr>
  <tr>
   <th scope="row">Value</th>
   <td><a href="/en/SVG/Content_type#Number-optional-number">&lt;number-optional-number&gt;</a></td>
  </tr>
  <tr>
   <th scope="row">Animatable</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<h2 id="Example">Example</h2>

<h2 id="Elements">Elements</h2>

<p>下列元素可以使用 order 属性</p>

<ul>
 <li>{{ SVGElement("feConvolveMatrix") }}</li>
</ul>

<h2 id="规范">规范</h2>

{{Specifications}}