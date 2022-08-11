---
title: preserveAlpha
slug: Web/SVG/Attribute/preserveAlpha
translation_of: Web/SVG/Attribute/preserveAlpha
---
<p>« <a href="/en/SVG/Attribute">SVG 属性参考</a></p>

<p><code>preserveAlpha</code> 属性表示{{ SVGElement("feConvolveMatrix") }} 元素怎样处透明度。</p>

<p>取值为 <code>false</code> 表示 feConvolveMatrix 元素将应用在包括透明度通道的所有的通道。这是默认的选项。</p>

<p>取值为 <code>true</code> 表示 feConvolveMatrix 仅应用在颜色通道。</p>

<h2 id="用法">用法</h2>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">类别</th>
   <td>None</td>
  </tr>
  <tr>
   <th scope="row">值</th>
   <td><code>true</code> | <code>false</code></td>
  </tr>
  <tr>
   <th scope="row">可变性</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<h2 id="示例">示例</h2>

<h2 id="元素">元素</h2>

<p>下列元素可以使用 <code>preserveAlpha</code> 属性</p>

<ul>
 <li>{{ SVGElement("feConvolveMatrix") }}</li>
</ul>

<h2 id="规范">规范</h2>

{{Specifications}}