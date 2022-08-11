---
title: patternUnits
slug: Web/SVG/Attribute/patternUnits
translation_of: Web/SVG/Attribute/patternUnits
---
<div>{{SVGRef}}</div>

<p>The <strong><code>patternUnits</code></strong> attribute indicates which coordinate system to use for the geometry properties of the {{ SVGElement("pattern") }} element.</p>

<p>Only one element is using this attribute: {{SVGElement('pattern')}}</p>

<h2>示例</h2>

<pre class="brush: css hidden">html,body,svg { height:100% }</pre>

<pre class="brush: html">&lt;svg viewBox="0 0 200 100" xmlns="http://www.w3.org/2000/svg"&gt;
  &lt;!-- All geometry properties are relative to the current user space --&gt;
  &lt;pattern id="p1" x="12.5" y="12.5" width="25" height="25"
           patternUnits="userSpaceOnUse"&gt;
    &lt;circle cx="10" cy="10" r="10" /&gt;
  &lt;/pattern&gt;

  &lt;!-- All geometry properties are relative to the target bounding box --&gt;
  &lt;pattern id="p2" x=".125" y=".125" width=".25" height=".25"
           patternUnits="objectBoundingBox"&gt;
    &lt;circle cx="10" cy="10" r="10" /&gt;
  &lt;/pattern&gt;

  &lt;!-- Left square with user space tiles --&gt;
  &lt;rect x="10"  y="10" width="80" height="80"
        fill="url(#p1)" /&gt;

  &lt;!-- Right square with bounding box tiles --&gt;
  &lt;rect x="110" y="10" width="80" height="80"
        fill="url(#p2)" /&gt;
&lt;/svg&gt;</pre>

<p>{{EmbedLiveSample('示例', '100%', 200)}}</p>

<h2 id="pattern">pattern</h2>

<p>For {{SVGElement('pattern')}}, <code>patternUnits</code> defines the coordinate system in use for the geometry properties ({{ SVGAttr("x") }}, {{ SVGAttr("y") }}, {{ SVGAttr("width") }} and {{ SVGAttr("height") }}) of the element.</p>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">Value</th>
   <td><code>userSpaceOnUse</code> | <code>objectBoundingBox</code></td>
  </tr>
  <tr>
   <th scope="row">Default value</th>
   <td><code>objectBoundingBox</code></td>
  </tr>
  <tr>
   <th scope="row">Animatable</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<dl>
 <dt>userSpaceOnUse</dt>
 <dd>This value indicates that all coordinates for the geometry preoperties refer to the user coordinate system as defined when the pattern was applied.</dd>
 <dt>objectBoundingBox</dt>
 <dd>This value indicates that all coordinates for the geometry properties represent fractions or percentages of the bounding box of the element to which the mask is applied. A bounding box could be considered the same as if the content of the {{ SVGElement("mask") }} were bound to a "<code>0 0 1 1</code>" {{ SVGAttr("viewbox") }}.</dd>
</dl>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}