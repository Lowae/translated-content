---
title: Node
slug: Web/API/Node
tags:
  - DOM
  - Node
translation_of: Web/API/Node
---
<div>{{APIRef("DOM")}}</div>

<p><strong><code>Node</code></strong>는 여러 가지 DOM 타입들이 상속하는 인터페이스이며 그 다양한 타입들을 비슷하게 처리할 수 있게 한다. 예를들어, 똑같은 메소드를 상속하거나 똑같은 방식으로 테스트를 할수있다</p>

<p>다음의 인터페이스들은 모두 <code>Node</code>로부터 메소드와 프라퍼티를 상속한다: {{domxref("Document")}}, {{domxref("Element")}}, {{domxref("CharacterData")}} ({{domxref("Text")}}, {{domxref("Comment")}}, {{domxref("CDATASection")}}이 상속), {{domxref("ProcessingInstruction")}}, {{domxref("DocumentFragment")}}, {{domxref("DocumentType")}}, {{domxref("Notation")}}, {{domxref("Entity")}}, {{domxref("EntityReference")}}</p>

<p>이 인터페이스들은 메소드나 프라퍼티가 적합하지 않은 경우에 null을 반환할 수 있다. 그들은 예외를 발생할 수 있다 - 예를 들어 자식이 있을 수 없는 노드 타입에 자식을 추가할 때 말이다.</p>

<h2 id="프라퍼티_&lt;속성>">프라퍼티 &lt;속성&gt;</h2>

<p><em>부모인 {{domxref("EventTarget")}}으로부터 프라퍼티를 상속한다</em>.<sup>[1]</sup></p>

<dl>
 <dt>{{domxref("Node.baseURI")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("DOMString")}} representing the base URL. The concept of base URL changes from one language to another; in HTML, it corresponds to the protocol, the domain name and the directory structure, that is all until the last <code>'/'</code>.</dd>
 <dt>{{domxref("Node.baseURIObject")}} {{Non-standard_inline()}}</dt>
 <dd>(Not available to web content.) The read-only <code>nsIURI</code> object representing the base URI for the element.</dd>
 <dt>{{domxref("Node.childNodes")}} {{readonlyInline}}</dt>
 <dd>Returns a live {{domxref("NodeList")}} containing all the children of this node. {{domxref("NodeList")}} being live means that if the children of the <code>Node</code> change, the {{domxref("NodeList")}} object is automatically updated.</dd>
 <dt>{{domxref("Node.firstChild")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("Node")}} representing the first direct child node of the node, or <code>null</code> if the node has no child.</dd>
 <dt>{{domxref("Node.lastChild")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("Node")}} representing the last direct child node of the node, or <code>null</code> if the node has no child.</dd>
 <dt>{{domxref("Node.localName")}} {{deprecated_inline}}{{readonlyInline}}</dt>
 <dd>Returns a {{domxref("DOMString")}} representing the local part of the qualified name of an element. In Firefox 3.5 and earlier, the property upper-cases the local name for HTML elements (but not XHTML elements). In later versions, this does not happen, so the property is in lower case for both HTML and XHTML. {{ gecko_minversion_inline("1.9.2") }}<br>
 Though recent specifications require <code>localName</code> to be defined on the {{domxref("Element")}} interface, Gecko-based browsers still implement it on the {{domxref("Node")}} interface.</dd>
 <dt>{{domxref("Node.namespaceURI")}} {{deprecated_inline}}{{readonlyInline}}</dt>
 <dd>The namespace URI of this node, or <code>null</code> if it is no namespace. In Firefox 3.5 and earlier, HTML elements are in no namespace. In later versions, HTML elements are in the <code><a class="linkification-ext external" href="http://www.w3.org/1999/xhtml" title="Linkification: http://www.w3.org/1999/xhtml">http://www.w3.org/1999/xhtml</a></code> namespace in both HTML and XML trees. {{ gecko_minversion_inline("1.9.2") }}<br>
 Though recent specifications require <code>namespaceURI</code> to be defined on the {{domxref("Element")}} interface, Gecko-based browsers still implement it on the {{domxref("Node")}} interface.</dd>
 <dt>{{domxref("Node.nextSibling")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("Node")}} representing the next node in the tree, or <code>null</code> if there isn't such node.</dd>
 <dt>{{domxref("Node.nodeName")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("DOMString")}} containing the name of the <code>Node</code>. The structure of the name will differ with the name type. E.g. An {{domxref("HTMLElement")}} will contain the name of the corresponding tag, like <code>'audio'</code> for an {{domxref("HTMLAudioElement")}}, a {{domxref("Text")}} node will have the <code>'#text'</code> string, or a {{domxref("Document")}} node will have the <code>'#document'</code> string.</dd>
 <dt>{{domxref("Node.nodePrincipal")}} {{Non-standard_inline()}}</dt>
 <dd>A <code>nsIPrincipal</code> representing the node principal.</dd>
 <dt>{{domxref("Node.nodeType")}}{{readonlyInline}}</dt>
 <dd>Returns an <code>unsigned short</code> representing the type of the node. Possible values are:
 <table class="standard-table">
  <tbody>
   <tr>
    <th scope="col">Name</th>
    <th scope="col">Value</th>
   </tr>
   <tr>
    <td><code>ELEMENT_NODE</code></td>
    <td><code>1</code></td>
   </tr>
   <tr>
    <td><code>ATTRIBUTE_NODE</code> {{deprecated_inline()}}</td>
    <td><code>2</code></td>
   </tr>
   <tr>
    <td><code>TEXT_NODE</code></td>
    <td><code>3</code></td>
   </tr>
   <tr>
    <td><code>CDATA_SECTION_NODE</code> {{deprecated_inline()}}</td>
    <td><code>4</code></td>
   </tr>
   <tr>
    <td><code>ENTITY_REFERENCE_NODE</code> {{deprecated_inline()}}</td>
    <td><code>5</code></td>
   </tr>
   <tr>
    <td><code>ENTITY_NODE</code> {{deprecated_inline()}}</td>
    <td><code>6</code></td>
   </tr>
   <tr>
    <td><code>PROCESSING_INSTRUCTION_NODE</code></td>
    <td><code>7</code></td>
   </tr>
   <tr>
    <td><code>COMMENT_NODE</code></td>
    <td><code>8</code></td>
   </tr>
   <tr>
    <td><code>DOCUMENT_NODE</code></td>
    <td><code>9</code></td>
   </tr>
   <tr>
    <td><code>DOCUMENT_TYPE_NODE</code></td>
    <td><code>10</code></td>
   </tr>
   <tr>
    <td><code>DOCUMENT_FRAGMENT_NODE</code></td>
    <td><code>11</code></td>
   </tr>
   <tr>
    <td><code>NOTATION_NODE</code> {{deprecated_inline()}}</td>
    <td><code>12</code></td>
   </tr>
  </tbody>
 </table>
 </dd>
 <dt>{{domxref("Node.nodeValue")}}</dt>
 <dd>Is a {{domxref("DOMString")}} representing the value of an object. For most <code>Node</code> type, this returns <code>null</code> and any set operation is ignored. For nodes of type <code>TEXT_NODE</code> ({{domxref("Text")}} objects), <code>COMMENT_NODE</code> ({{domxref("Comment")}} objects), and <code>PROCESSING_INSTRUCTION_NODE</code> ({{domxref("ProcessingInstruction")}} objects), the value corresponds to the text data contained in the object.</dd>
 <dt>{{domxref("Node.ownerDocument")}} {{readonlyInline}}</dt>
 <dd>Returns the {{domxref("Document")}} that this node belongs to. If no document is associated with it, returns <code>null</code>.</dd>
 <dt>{{domxref("Node.parentNode")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("Node")}} that is the parent of this node. If there is no such node, like if this node is the top of the tree or if doesn't participate in a tree, this property returns <code>null</code>.</dd>
 <dt>{{domxref("Node.parentElement")}} {{readonlyInline}}</dt>
 <dd>Returns an {{domxref("Element")}} that is the parent of this node. If the node has no parent, or if that parent is not an {{domxref("Element")}}, this property returns <code>null</code>.</dd>
 <dt>{{domxref("Node.prefix")}} {{deprecated_inline}}{{readonlyInline}}</dt>
 <dd>Is a {{domxref("DOMString")}} representing the namespace prefix of the node, or <code>null</code> if no prefix is specified.<br>
 Though recent specifications require <code>prefix</code> to be defined on the {{domxref("Element")}} interface, Gecko-based browsers still implement it on the {{domxref("Node")}} interface.</dd>
 <dt>{{domxref("Node.previousSibling")}} {{readonlyInline}}</dt>
 <dd>Returns a {{domxref("Node")}} representing the previous node in the tree, or <code>null</code> if there isn't such node.</dd>
 <dt>{{domxref("Node.textContent")}}</dt>
 <dd>Is a {{domxref("DOMString")}} representing the textual content of an element and all its descendants.</dd>
</dl>

<h2 id="메소드">메소드</h2>

<p><em>부모인 {{domxref("EventTarget")}}으로부터 메소드를 상속한다</em>.<sup>[1]</sup></p>

<dl>
 <dt>{{domxref("Node.appendChild()")}}</dt>
 <dd>Insert a {{domxref("Node")}} as the last child node of this element.</dd>
 <dt>{{domxref("Node.cloneNode()")}}</dt>
 <dd>Clone a {{domxref("Node")}}, and optionally, all of its contents. By default, it clones the content of the node.</dd>
 <dt>{{domxref("Node.compareDocumentPosition()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.contains()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.getFeature()")}} {{deprecated_inline}}</dt>
 <dd>...</dd>
 <dt>{{domxref("Node.getUserData()")}} {{deprecated_inline}}</dt>
 <dd>Allows a user to get some {{domxref("DOMUserData")}} from the node.</dd>
 <dt>{{domxref("Node.hasAttributes()")}} {{deprecated_inline}}</dt>
 <dd>Returns a {{domxref("Boolean")}} indicating if the element has any attributes, or not.</dd>
 <dt>{{domxref("Node.hasChildNodes()")}}</dt>
 <dd>Returns a {{domxref("Boolean")}} indicating if the element has any child nodes, or not.</dd>
 <dt>{{domxref("Node.insertBefore()")}}</dt>
 <dd>Inserts the first {{domxref("Node")}} given in a parameter immediately before the second, child of this element, {{domxref("Node")}}.</dd>
 <dt>{{domxref("Node.isDefaultNamespace()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.isEqualNode()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.isSameNode()")}} {{deprecated_inline}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.isSupported()")}} {{deprecated_inline}}</dt>
 <dd>Returns a <a href="https://developer.mozilla.org/en-US/docs/Web/API/Boolean" title="The Boolean object is an object wrapper for a boolean value."><code>Boolean</code></a> flag containing the result of a test whether the DOM implementation implements a specific feature and this feature is supported by the specific node.</dd>
 <dt>{{domxref("Node.lookupPrefix()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.lookupNamespaceURI()")}}</dt>
 <dd></dd>
 <dt>{{domxref("Node.normalize()")}}</dt>
 <dd>Clean up all the text nodes under this element (merge adjacent, remove empty).</dd>
 <dt>{{domxref("Node.removeChild()")}}</dt>
 <dd>Removes a child node from the current element, which must be a child of the current node.</dd>
 <dt>{{domxref("Node.replaceChild()")}}</dt>
 <dd>Replaces one child {{domxref("Node")}} of the current one with the second one given in parameter.</dd>
 <dt>{{domxref("Node.setUserData()")}} {{deprecated_inline}}</dt>
 <dd>Allows a user to attach, or remove, {{domxref("DOMUserData")}} to the node.</dd>
</dl>

<h2 id="예제">예제</h2>

<h3 id="모든_자식_노드_탐색">모든 자식 노드 탐색</h3>

<p>The following function recursively cycles all child nodes of a node and executes a callback function upon them (and upon the parent node itself).</p>

<pre class="brush: js">function DOMComb (oParent, oCallback) {
  if (oParent.hasChildNodes()) {
    for (var oNode = oParent.firstChild; oNode; oNode = oNode.nextSibling) {
      DOMComb(oNode, oCallback);
    }
  }
  oCallback.call(oParent);
}</pre>

<h4 id="Syntax">Syntax</h4>

<pre>DOMComb(parentNode, callbackFunction);</pre>

<h4 id="Description">Description</h4>

<p>Recursively cycle all child nodes of <code>parentNode</code> and <code>parentNode</code> itself and execute the <code>callbackFunction</code> upon them as <a href="/en-US/docs/JavaScript/Reference/Operators/this" title="en-US/docs/JavaScript/Reference/Operators/this"><code>this</code></a> objects.</p>

<h4 id="Parameters">Parameters</h4>

<dl>
 <dt><code>parentNode</code></dt>
 <dd>The parent node (<code><strong>Node</strong> <a href="/en-US/docs/JavaScript/Reference/Global_Objects/Object" title="en-US/docs/JavaScript/Reference/Global_Objects/Object">Object</a></code>).</dd>
 <dt><code>callbackFunction</code></dt>
 <dd>The callback function (<a href="/en-US/docs/JavaScript/Reference/Global_Objects/Function" title="en-US/docs/JavaScript/Reference/Global_Objects/Function"><code>Function</code></a>).</dd>
</dl>

<h4 id="Sample_usage">Sample usage</h4>

<p>The following example send to the <code>console.log</code> the text content of the body:</p>

<pre class="brush: js">function printContent () {
  if (this.nodeValue) { console.log(this.nodeValue); }
}

onload = function () {
  DOMComb(document.body, printContent);
};</pre>

<h3 id="한_노드_안에_중첩된_모든_자식_제거">한 노드 안에 중첩된 모든 자식 제거</h3>

<pre class="brush: js">Element.prototype.removeAll = function () {
  while (this.firstChild) { this.removeChild(this.firstChild); }
  return this;
};</pre>

<h4 id="Sample_usage_2">Sample usage</h4>

<pre class="brush: js">/* ... an alternative to document.body.innerHTML = "" ... */
document.body.removeAll();</pre>

<h2 id="명세">명세</h2>

{{Specifications}}

<h2 id="브라우저_호환성">브라우저 호환성</h2>

<p>{{Compat("api.Node")}}</p>