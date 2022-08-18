---
title: UI 擬似クラス
slug: Learn/Forms/UI_pseudo-classes
tags:
  - Beginner
  - CSS
  - Example
  - Forms
  - Guide
  - HTML
  - Pseudo-classes
  - Styling
  - Web
translation_of: Learn/Forms/UI_pseudo-classes
---
<p>{{LearnSidebar}}{{PreviousMenuNext("Learn/Forms/Advanced_form_styling", "Learn/Forms/Form_validation", "Learn/Forms")}}</p>

<p>In the previous articles, we covered the styling of various form controls, in a general manner. This included some usage of pseudo-classes, 例えば、using <code>:checked</code> to target a checkbox only when it is selected. <span class="seoSummary">In this article, we will explore in detail the different UI pseudo-classes available to us in modern browsers for styling forms in different states.</span></p>

<table class="learn-box standard-table">
 <tbody>
  <tr>
   <th scope="row">前提条件:</th>
   <td>Basic computer literacy, and a basic understanding of <a href="/ja/docs/Learn/HTML/Introduction_to_HTML">HTML</a> and <a href="/ja/docs/Learn/CSS/First_steps">CSS</a>, including general knowledge of <a href="/ja/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements">pseudo-classes and pseudo-elements</a>.</td>
  </tr>
  <tr>
   <th scope="row">目的:</th>
   <td>To understand what parts of forms are hard to style, and why; to learn what can be done to customize them.</td>
  </tr>
 </tbody>
</table>

<h2 id="What_pseudo-classes_do_we_have_available" name="What_pseudo-classes_do_we_have_available">疑似クラスで何が利用できるか?</h2>

<p>The original pseudo-classes available to us (as of <a href="http://www.w3.org/TR/CSS21/selector.html#dynamic-pseudo-classes" rel="external">CSS 2.1</a>) that are relevant to forms are:</p>

<ul>
 <li>{{cssxref(":hover")}}: Selects an element only when it is being hovered over by a mouse pointer.</li>
 <li>{{cssxref(":focus")}}: Selects an element only when it is focused (i.e. by being tabbed to via the keyboard).</li>
 <li>{{cssxref(":active")}}: selects an element only when it is being activated (i.e. while it is being clicked on, or when the <kbd>Return</kbd>/<kbd>Enter</kbd> key is being pressed down in the case of a keyboard activation).</li>
</ul>

<p>These basic pseudo-classes should be familiar to you now. More recently, the <a href="http://www.w3.org/TR/css3-selectors/" rel="external">CSS Selector Level 3</a> and <a href="http://dev.w3.org/csswg/css3-ui/#pseudo-classes" rel="external">CSS Basic UI Level 3</a> added more pseudo-classes related to HTML forms that provide several other useful targetting conditions that you can take advantage of. We'll discuss these in more detail in the sections below, but briefly, the main ones we'll be looking at are:</p>

<ul>
 <li>{{cssxref(':required')}} and {{cssxref(':optional')}}: Targets required or optional form controls.</li>
 <li>{{cssxref(":valid")}} and {{cssxref(":invalid")}}, and {{cssxref(":in-range")}} and {{cssxref(":out-of-range")}}: Target form controls that are valid/invalid according to form validation constraints set on them, or in-range/out-of-range.</li>
 <li>{{cssxref(":enabled")}} and {{cssxref(":disabled")}}, and {{cssxref(":read-only")}} and {{cssxref(":read-write")}}: Target enabled or disabled form controls (e.g. with the <code>disabled</code> HTML attribute set), and read-write or read-only form controls (e.g. with the <code>readonly</code> HTML attribute set).</li>
 <li>{{cssxref(":checked")}}, {{cssxref(":indeterminate")}}, and {{cssxref(":default")}}: Respectively target checkboxes and radio buttons that are checked, in an indeterminate state (neither checked or not checked), and the default selected option when the page loads (e.g. an <code><a href="/ja/docs/Web/HTML/Element/input/checkbox">&lt;input type="checkbox"&gt;</a></code> with the <code>checked</code> attribute set, or an <code><a href="/ja/docs/Web/HTML/Element/option">&lt;option&gt;</a></code> element with the <code>selected</code> attribute set).</li>
</ul>

<p>There are many others too, but the ones listed above are the most obviously useful. Some of the others are aimed at solving very specific niche problems, or simply not very well supported in browsers yet. The ones listed above all have pretty good browser support, but of course, you should test your form implementations carefully to make sure they work for your target audience.</p>

<div class="blockIndicator note">
<p><strong>注</strong>: A number of the pseudo-classes discussed here are concerned with styling form controls based on their validation state (is their data valid, or not?) You'll learn much more about setting and controlling validation constraints in our next article — <a href="/ja/docs/Learn/Forms/Form_validation">Client-side form validation</a> — but for now we'll keep things simple with regards to form validation, so it doesn't confuse things.</p>
</div>

<h2 id="Styling_inputs_based_on_whether_they_are_required_or_not" name="Styling_inputs_based_on_whether_they_are_required_or_not">入力が必須か否かでスタイル設定する</h2>

<p>One of the most basic concepts with regards to client-side form validation is whether a form input is required (it has to be filled in before the form can be submitted) or optional.</p>

<p>{{htmlelement('input')}}, {{htmlelement('select')}}, and {{htmlelement('textarea')}} elements have a <code>required</code> attribute available which, when set, means that you have to fill in that control before the form will successfully submit. 例えば、:</p>

<pre class="brush: html notranslate">&lt;form&gt;
  &lt;fieldset&gt;
    &lt;legend&gt;Feedback form&lt;/legend&gt;
    &lt;div&gt;
      &lt;label for="fname"&gt;First name: &lt;/label&gt;
      &lt;input id="fname" name="fname" type="text" required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="lname"&gt;Last name: &lt;/label&gt;
      &lt;input id="lname" name="lname" type="text" required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="email"&gt;Email address (include if you want a response): &lt;/label&gt;
      &lt;input id="email" name="email" type="email"&gt;
    &lt;/div&gt;
    &lt;div&gt;&lt;button&gt;Submit&lt;/button&gt;&lt;/div&gt;
  &lt;/fieldset&gt;
&lt;/form&gt;</pre>

<p>Here, the first name and last name are required, but the email address is optional.</p>

<p>You can match these two states using the {{cssxref(':required')}} and {{cssxref(':optional')}} pseudo-classes. 例えば、if we apply the following CSS to the above HTML:</p>

<pre class="brush: css notranslate">input:required {
  border: 1px solid black;
}

input:optional {
  border: 1px solid silver;
}</pre>

<p>The required controls would have a black border, and the optional control will have a silver border, like so:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/basic-required-optional.html", '100%', 400)}}</p>

<p>You can also try submitting the form without filling it in, to see the client-side validation error messages browsers give you 既定では.</p>

<p>The above form isn't bad, but it isn't great either. For a start, we are signalling required versus optional status using color alone, which isn't great for colorblind people. Second, the standard convention on the web for required status is an asterisk (*), or the word "required" being associated with the controls in question.</p>

<p>In the next section, we'll look at a better example of indicating required fields using <code>:required</code>, which also digs into using generated content.</p>

<div class="blockIndicator note">
<p><strong>注</strong>: You'll probably not find yourself using the <code>:optional</code> pseudo-class very often. Form controls are optional 既定では, so you could just do your optional styling 既定では, and add styles on top for required controls.</p>
</div>

<div class="blockIndicator note">
<p><strong>注</strong>: If one radio button in a same-named group of radio buttons has the <code>required</code> attribute, all the radio buttons will be invalid until one is selected, but only the one with the attribute assigned will actually match {{cssxref(':required')}}<strong>.</strong></p>
</div>

<h2 id="Using_generated_content_with_pseudo-classes" name="Using_generated_content_with_pseudo-classes">疑似クラスでコンテンツを生成する</h2>

<p>In previous articles, we've seen the usage of <a href="/ja/docs/Web/CSS/CSS_Generated_Content">generated content</a>, but we thought now would be a good time to talk about it in a bit more detail.</p>

<p>The idea is that we can use the <code><a href="/ja/docs/Web/CSS/::before">::before</a></code> and <code><a href="/ja/docs/Web/CSS/::after">::after</a></code> pseudo-elements along with the <code><a href="/ja/docs/Web/CSS/content">content</a></code> property to make a chunk of content appear before or after the affected element. The chunk of content is not added to the DOM, so is invisible to screenreaders; it is part of the document's styles. Because it is a pseudo element, it can be targetted with styles in the same way that any actual DOM node can.</p>

<p>This is really useful when you want to add a visual indicator to an element, such as a label or icon, but don't want it to be picked up by assistive technologies. 例えば、in our <a href="https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html">custom radio buttons example</a>, we use generated content to handle the placement and animation of the inner circle when a radio button is selected:</p>

<pre class="brush: css notranslate">input[type="radio"]::before {
  display: block;
  content: " ";
  width: 10px;
  height: 10px;
  border-radius: 6px;
  background-color: red;
  font-size: 1.2em;
  transform: translate(3px, 3px) scale(0);
  transform-origin: center;
  transition: all 0.3s ease-in;
}

input[type="radio"]:checked::before {
  transform: translate(3px, 3px) scale(1);
  transition: all 0.3s cubic-bezier(0.25, 0.25, 0.56, 2);
}</pre>

<p>This is really useful — screenreaders already let their users know when a radio button or checkbox they encounter is checked/selected, so you don't want them to read out another DOM element that indicates selection — that could be confusing. Having a purely visual indicator solves this problem.</p>

<div class="blockIndicator note">
<p><strong>注</strong>: This also shows how you can combine a pseudo-class and pseudo-element if required.</p>
</div>

<p>Back to our required/optional example from before, this time we'll not alter the appearance of the input itself — we'll use generated content to add an indicating label (<a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/required-optional-generated.html">see it live here</a>, and see the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/required-optional-generated.html">source code here</a>).</p>

<p>First of all, we'll add a paragraph to the top of the form to say what you are looking for:</p>

<pre class="brush: html notranslate">&lt;p&gt;Required fields are labelled with "required".&lt;/p&gt;</pre>

<p>Screenreader users will get "required" read out as an extra bit of information when they get to each required input, which sighted users will get our label.</p>

<p>Since form inputs don't directly support having generated content put on them (this is because generated content is placed relative to an element's formatting box, but form inputs work more like replaced elements and therefore don't have one), we will add an empty <code><a href="/ja/docs/Web/HTML/Element/span">&lt;span&gt;</a></code> to hang the generated content on:</p>

<pre class="brush: html notranslate">&lt;div&gt;
  &lt;label for="fname"&gt;First name: &lt;/label&gt;
  &lt;input id="fname" name="fname" type="text" required&gt;
  &lt;span&gt;&lt;/span&gt;
&lt;/div&gt;</pre>

<p>The immediate problem with this was that the span was dropping onto a new line below the input because the input and label are both set with <code>width: 100%</code>. To fix this we style the parent <code>&lt;div&gt;</code> to become a flex container, but also tell it to wrap its contents onto new lines if the content becomes too long:</p>

<pre class="brush: css notranslate">fieldset &gt; div {
  margin-bottom: 20px;
  display: flex;
  flex-flow: row wrap;
}</pre>

<p>The effect this has is that the label and input sit on separate lines because they are both <code>width: 100%</code>, but the <code>&lt;span&gt;</code> has a width of 0 so can sit on the same line as the input.</p>

<p>Now onto the generated content. We create it using this CSS:</p>

<pre class="brush: css notranslate">input + span {
  position: relative;
}

input:required + span::after {
  font-size: 0.7rem;
  position: absolute;
  content: "required";
  color: white;
  background-color: black;
  padding: 5px 10px;
  top: -26px;
  left: -70px;
}</pre>

<p>We set the <code>&lt;span&gt;</code> to <code>position: relative</code> simply so that we can set the generated content to <code>position: absolute</code> and position it relative to the <code>&lt;span&gt;</code> rather than the &lt;body&gt; (The generated content acts as though it is a child node of the element it is generated on, for the purposes of positioning).</p>

<p>Then we give the generated content the content "required", which is what we wanted our label to say, and style and position it as we want. The result is seen below.</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/required-optional-generated.html", '100%', 430)}}</p>

<h2 id="Styling_controls_based_on_whether_their_data_is_valid" name="Styling_controls_based_on_whether_their_data_is_valid">データが妥当が否かでコントロールをスタイル設定する</h2>

<p>The other really important, fundamental concept in form validation is whether a form control's data is valid or not (in the case of numerical data, we can also talk about in-range and out-of-range data). Form controls with <a href="/ja/docs/Web/Guide/HTML/HTML5/Constraint_validation">constraint limitations</a> can be targeted based on these states.</p>

<h3 id="valid_and_invalid" name="valid_and_invalid">:valid と :invalid</h3>

<p>You can target from control using the {{cssxref(":valid")}} and {{cssxref(":invalid")}} pseudo-classes. Some points worth bearing in mind:</p>

<ul>
 <li>Controls with no constraint validation will always be valid, and therefore matched with <code>:valid</code>.</li>
 <li>Controls with <code>required</code> set on them that have no value are counted as invalid — they will be matched with <code>:invalid</code> and <code>:required</code>.</li>
 <li>Controls with built-in validation, such as <code>&lt;input type="email"&gt;</code> or <code>&lt;input type="url"&gt;</code> are (matched with) <code>:invalid</code> when the data entered into them does not match the pattern they are looking for (but they are valid when empty).</li>
 <li>Controls whose current value is outside the range limits specified by the {{htmlattrxref("min", "input")}} and {{htmlattrxref("max","input")}} attributes are (matched with) <code>:invalid</code>, but also matched by {{cssxref(":out-of-range")}}, as you'll see later on.</li>
 <li>There are some other ways to make an element matched by <code>:valid</code>/<code>:invalid</code>, as you'll see in the <a href="/ja/docs/Learn/Forms/Form_validation">Client-side form validation</a> article. But we'll keep things simple for now.</li>
</ul>

<p>Let's go in and look at a simple example of <code>:valid</code>/<code>:invalid</code> (see <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/valid-invalid.html">valid-invalid.html</a> for the live version, and also check out the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/valid-invalid.html">source code</a>).</p>

<p>As in the previous example, we've got extra <code>&lt;span&gt;</code>s to generate content on, which we'll use to provide indicators of valid/invalid data:</p>

<pre class="brush: html notranslate">&lt;div&gt;
  &lt;label for="fname"&gt;First name *: &lt;/label&gt;
  &lt;input id="fname" name="fname" type="text" required&gt;
  &lt;span&gt;&lt;/span&gt;
&lt;/div&gt;</pre>

<p>To provide these indicators, we use the following CSS:</p>

<pre class="brush: css notranslate">input + span {
  position: relative;
}

input + span::before {
  position: absolute;
  right: -20px;
  top: 5px;
}

input:invalid {
  border: 2px solid red;
}

input:invalid + span::before {
  content: '✖';
  color: red;
}

input:valid + span::before {
  content: '✓';
  color: green;
}</pre>

<p>As before, we set the <code>&lt;span&gt;</code>s to <code>position: relative</code> so that we can position the generated content relative to them. We then absolutely position different generated content depending on whether the form's data is valid or invalid — a green check or a red cross, respectively. To add a bit of extra urgency to the invalid data, we've also given the inputs a thick red border when invalid.</p>

<div class="blockIndicator note">
<p><strong>注</strong>: We've used <code>::before</code> to add these labels, as we were already using <code>::after</code> for the "required" labels.</p>
</div>

<p>You can try it below:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/valid-invalid.html", '100%', 430)}}</p>

<p>Notice how the required text inputs are invalid when empty, but valid when they have something filled in. The email input on the other hand is valid when empty, as it is not required, but invalid when it contains something that is not a proper email address.</p>

<h3 id="In-range_and_out-of-range_data" name="In-range_and_out-of-range_data">範囲内と範囲外のデータ</h3>

<p>As we hinted at above, there are two other related pseudo-classes to consider — {{cssxref(":in-range")}} and {{cssxref(":out-of-range")}}. These match numeric inputs where range limits are specified by the {{htmlattrxref("min", "input")}} and {{htmlattrxref("max","input")}}, when their data is inside or outside the specified range, respectvely.</p>

<div class="blockIndicator note">
<p><strong>注</strong>: Numeric input types are <code>date</code>, <code>month</code>, <code>week</code>, <code>time</code>, <code>datetime-local</code>, <code>number</code>, and <code>range</code>.</p>
</div>

<p>It is worth noting that inputs whose data is in-range will also be matched by the <code>:valid</code> pseudo-class and inputs whose data is out-of-range will also be matched by the <code>:invalid</code> pseudo-class. So why have both? The issue is really one of semantics — out-of-range is a more specific type of invalid communication, so you might want to provide a different message for out-of-range inputs, which will be more helpful to users than just saying "invalid". You might even want to provide both.</p>

<p>Let's look at an example that does exactly this. Our <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/out-of-range.html">out-of-range.html</a> demo (see also the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/out-of-range.html">source code</a>) builds on top of the previous example to provide out-of-range messages for the numeric inputs, as well as saying whether they are required.</p>

<p>The numeric input looks like this:</p>

<pre class="brush: html notranslate">&lt;div&gt;
  &lt;label for="age"&gt;Age (must be 12+): &lt;/label&gt;
  &lt;input id="age" name="age" type="number" min="12" max="120" required&gt;
  &lt;span&gt;&lt;/span&gt;
&lt;/div&gt;</pre>

<p>And the CSS looks like this:</p>

<pre class="brush: css notranslate">input + span {
  position: relative;
}

input + span::after {
  font-size: 0.7rem;
  position: absolute;
  padding: 5px 10px;
  top: -26px;
}

input:required + span::after {
  color: white;
  background-color: black;
  content: "Required";
  left: -70px;
}

input:out-of-range + span::after {
  color: white;
  background-color: red;
  width: 155px;
  content: "Outside allowable value range";
  left: -182px;
}</pre>

<p>This is a similar story to what we had before in the <code>:required</code> example, except that here we've split out the declarations that apply to any <code>::after</code> content into a separate rule, and given the separate <code>::after</code> content for <code>:required</code> and <code>:out-of-range</code> states their own content and styling. You can try it here:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/out-of-range.html", '100%', 430)}}</p>

<p>It is possible for the number input to be both required and out-of-range at the same time, so what happens then? Because the <code>:out-of-range</code> rule appears later in the source code than the <code>:required</code> rule, the <a href="/ja/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#Understanding_the_cascade">cascade rules</a> come into play, and the out of range message is shown.</p>

<p>This works quite nicely — when the page first loads, "Required" is shown, along with a red cross and border. When you've typed in a valid age (i.e. in the range of 12-120), the input turns valid. If however, you then change the age entry to one that is out of range, the "Outside allowable value range" message then pops up in place of "Required".</p>

<div class="blockIndicator note">
<p><strong>注</strong>: To enter an invalid/out-of-range value, you'll have to actually focus the form and type it in using the keyboard. The spinner buttons won't let you increment/decrement the value outside the allowable range.</p>
</div>

<h2 id="Styling_enabled_and_disabled_inputs_and_read-only_and_read-write" name="Styling_enabled_and_disabled_inputs_and_read-only_and_read-write">有効/無効や読み取り専用/読み書き可能の入力をスタイル設定する</h2>

<p>An enabled element is an element that can be activated; it can be selected, clicked on, typed into, etc.  A disabled element on the other hand cannot be interacted with in any way, and its data isn't even sent to the server</p>

<p>These two states can be targeted using {{cssxref(":enabled")}} and {{cssxref(":disabled")}}. Why are disabled inputs useful? Well, sometimes if some data does not apply to a certain user, you might not even want to submit that data when they submit the form. A classic example is a shipping form — commonly you'll get asked if you want to use the same address for billing and shipping; if so, you can just send a single address to the server, and might as well just disable the billing address fields.</p>

<p>Let's have a look at an example that does just this. First of all, the HTML is a simple form containing text inputs, plus a checkbox to toggle disabling the billing address on and off. The billing address fields are disabled 既定では.</p>

<pre class="brush: html notranslate">&lt;form&gt;
  &lt;fieldset id="shipping"&gt;
    &lt;legend&gt;Shipping address&lt;/legend&gt;
    &lt;div&gt;
      &lt;label for="name1"&gt;Name: &lt;/label&gt;
      &lt;input id="name1" name="name1" type="text" required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="address1"&gt;Address: &lt;/label&gt;
      &lt;input id="address1" name="address1" type="text" required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="pcode1"&gt;Zip/postal code: &lt;/label&gt;
      &lt;input id="pcode1" name="pcode1" type="text" required&gt;
    &lt;/div&gt;
  &lt;/fieldset&gt;
  &lt;fieldset id="billing"&gt;
    &lt;legend&gt;Billing address&lt;/legend&gt;
    &lt;div&gt;
      &lt;label for="billing-checkbox"&gt;Same as shipping address:&lt;/label&gt;
      &lt;input type="checkbox" id="billing-checkbox" checked&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="name" class="billing-label disabled-label"&gt;Name: &lt;/label&gt;
      &lt;input id="name" name="name" type="text" disabled required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="address2" class="billing-label disabled-label"&gt;Address: &lt;/label&gt;
      &lt;input id="address2" name="address2" type="text" disabled required&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;label for="pcode2" class="billing-label disabled-label"&gt;Zip/postal code: &lt;/label&gt;
      &lt;input id="pcode2" name="pcode2" type="text" disabled required&gt;
    &lt;/div&gt;
  &lt;/fieldset&gt;

  &lt;div&gt;&lt;button&gt;Submit&lt;/button&gt;&lt;/div&gt;
&lt;/form&gt;</pre>

<p>Now onto the CSS. The most relevant parts of this example are as follows:</p>

<pre class="brush: css notranslate">input[type="text"]:disabled {
    background: #eee;
    border: 1px solid #ccc;
}

.disabled-label {
  color: #aaa;
}</pre>

<p>We've directly selected the inputs we want to disable using <code>input[type="text"]:disabled</code>, but we also wanted to gray out the corresponding text labels. These weren't quite as easy to select, so we've used a class to provide them with that styling.</p>

<p>Now finally, we've used some JavaScript to toggle the disabling of the billing address fields:</p>

<pre class="brush: js notranslate">// Wait for the page to finish loading
document.addEventListener('DOMContentLoaded', function () {

  // Attach `change` event listener to checkbox
  document.getElementById('billing-checkbox').addEventListener('change', toggleBilling);
}, false);

function toggleBilling() {
  // Select the billing text fields
  let billingItems = document.querySelectorAll('#billing input[type="text"]');
  // Select the billing text labels
  let billingLabels = document.querySelectorAll('.billing-label');

  // Toggle the billing text fields and labels
  for (let i = 0; i &lt; billingItems.length; i++) {
    billingItems[i].disabled = !billingItems[i].disabled;

    if(billingLabels[i].getAttribute('class') === 'billing-label disabled-label') {
      billingLabels[i].setAttribute('class', 'billing-label');
    } else {
      billingLabels[i].setAttribute('class', 'billing-label disabled-label');
    }
  }
}</pre>

<p>It uses the <a href="/ja/docs/Web/API/HTMLElement/change_event"><code>change</code> event</a> to let the user enable/disable the billing fields, and toggle the styling of the associated labels.</p>

<p>You can see the example in action below (also <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/enabled-disabled-shipping.html">see it live here</a>, and see the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/enabled-disabled-shipping.html">source code</a>):</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/enabled-disabled-shipping.html", '100%', 600)}}</p>

<h3 id="Read-only_and_read-write" name="Read-only_and_read-write">Read-only and read-write</h3>

<p>In a similar manner to <code>:disabled</code> and <code>:enabled</code>, the <code>:read-only</code> and <code>:read-write</code> pseudo-classes target two states that form inputs toggle between. Read-only inputs have their values submitted to the server, but the user can't edit them, whereas read-write means they can be edited — their default state.</p>

<p>An input is set to read-only using the <code>readonly</code> attribute. As an example, imagine a confirmation page where the developer has sent the details filled in on previous pages over to this page, with the aim of getting the user to check them all in one place, add any final data that is needed, and then confirm the order by submitting. At this point, all the final form data can be sent to the server in one go.</p>

<p>Let's look at what a form might look like (see <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/readonly-confirmation.html">readonly-confirmation.html</a> for the live example; also <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/readonly-confirmation.html">see the source code</a>).</p>

<p>A fragment of the HTML is as follows — note the readonly attribute:</p>

<pre class="brush: html notranslate">&lt;div&gt;
  &lt;label for="name"&gt;Name: &lt;/label&gt;
  &lt;input id="name" name="name" type="text"
         value="Mr Soft" readonly&gt;
&lt;/div&gt;</pre>

<p>If you try the live example, you'll see that the top set of form elements are not focusable, however the values are submitted when the form is submitted. We've styled the form controls using the <code>:read-only</code> and <code>:read-write</code> pseudo-classes, like so:</p>

<pre class="brush: css notranslate">input:-moz-read-only, textarea:-moz-read-only,
input:read-only, textarea:read-only {
  border: 0;
  box-shadow: none;
  background-color: white;
}

textarea:-moz-read-write,
textarea:read-write {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}</pre>

<p>Firefox only supported these pseudo-classes with a prefix up to version 78; at which point it started to support the unprefixed version. The full example looks like so:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/readonly-confirmation.html", '100%', 660)}}</p>

<div class="blockIndicator note">
<p><strong>注</strong>: <code>:enabled</code> and <code>:read-write</code> are two more pseudo-classes that you'll probably rarely use, given that they describe the default states of input elements.</p>
</div>

<h2 id="ラジオとチェックボックスの状態_—_チェック済み、既定、中間">ラジオとチェックボックスの状態 — チェック済み、既定、中間</h2>

<p>As we've seen in earlier articles in the module, {{HTMLElement("input/radio", "radio buttons")}} and {{HTMLElement("input/checkbox", "checkboxes")}} can be checked or unchecked. But there are a couple of other states to consider too:</p>

<ul>
 <li>{{cssxref(":default")}}: Matches radios/checkboxes that are checked 既定では, on page load (i.e. by setting the <code>checked</code> attribute on them) These match the {{cssxref(":default")}} pseudo-class, even if the user unchecks them.</li>
 <li>{{cssxref(":indeterminate")}}: When radios/checkboxes are neither checked nor unchecked, they are considered <em>indeterminate</em> and will match the {{cssxref(":indeterminate")}} pseudo-class. More on what this means below.</li>
</ul>

<h3 id="checked" name="checked">:checked</h3>

<p>When checked, they will be matched by the {{cssxref(":checked")}} pseudo-class.</p>

<p>The most common use of this is to add a different style onto the checkbox/radiobutton when it is checked, in cases where you've removed the system default styling with <code>appearance: none;</code> and want to build the styles back up yourself. We saw examples of this in the previous article when we talked about <a href="/ja/docs/Learn/Forms/Advanced_form_styling#Using_appearence_none_on_radioscheckboxes">Using <code>appearence: none</code> on radios/checkboxes</a>.</p>

<p>As a recap, the <code>:checked</code> code from our <a href="https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html">Styled radio buttons</a> example looks like so:</p>

<pre class="brush: css notranslate">input[type="radio"]::before {
  display: block;
  content: " ";
  width: 10px;
  height: 10px;
  border-radius: 6px;
  background-color: red;
  font-size: 1.2em;
  transform: translate(3px, 3px) scale(0);
  transform-origin: center;
  transition: all 0.3s ease-in;
}

input[type="radio"]:checked::before {
  transform: translate(3px, 3px) scale(1);
  transition: all 0.3s cubic-bezier(0.25, 0.25, 0.56, 2);
}</pre>

<p>You can try it out here:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/styling-examples/radios-styled.html", '100%', 200)}}</p>

<p>Basically, we build the styling for the radio button "inner circle" using the <code>::before</code> pseudo element, but set a <code>scale(0)</code> <code><a href="/ja/docs/Web/CSS/transform">transform</a></code> on it. We then use a <code><a href="/ja/docs/Web/CSS/transition">transition</a></code> to make it nicely animate into view when the radio is selected/checked. The advantage of using a transform rather than transitioning <code><a href="/ja/docs/Web/CSS/width">width</a></code>/<code><a href="/ja/docs/Web/CSS/height">height</a></code> is that you can use <code><a href="/ja/docs/Web/CSS/transform-origin">transform-origin</a></code> to make it grow from the center of the circle, rather than having it appear to grow from the circle's corner.</p>

<h3 id="default_and_indeterminate" name="default_and_indeterminate">:default と :indeterminate</h3>

<p>As mentioned above, the {{cssxref(":default")}} pseudo-class matches radios/checkboxes that are checked 既定では, on page load, even when unchecked. This could be useful for adding an indicator to a list of options to remind the user what the defaults (or starting options) were, in case they want to reset their choices.</p>

<p>Also mentioned above radios/checkboxes will be matched by the {{cssxref(":indeterminate")}} pseudo-class when they are in a state where they are neither checked nor unchecked. But what does this mean? Elements that are indeterminate include:</p>

<ul>
 <li>{{HTMLElement("input/radio")}} inputs, when all radio buttons in a same-named group are unchecked</li>
 <li>{{HTMLElement("input/checkbox")}} inputs whose <code>indeterminate</code> property is set to <code>true</code> via JavaScript</li>
 <li>{{HTMLElement("progress")}} elements that have no value.</li>
</ul>

<p>This isn't something you'll likely use very often. One use case could be an indicator to tell users that they really need to select a radio button before they move on.</p>

<p>Let's look at a couple of modified versions of the previous example that remind the user what the default option was, and style the radio buttons when indeterminate. Both of these have the following HTML structure for the inputs:</p>

<pre class="brush: html notranslate">&lt;p&gt;
  &lt;input type="radio" name="fruit" value="cherry" id="cherry"&gt;
  &lt;label for="cherry"&gt;Cherry&lt;/label&gt;
  &lt;span&gt;&lt;/span&gt;
&lt;/p&gt;</pre>

<p>For the <code>:default</code> example, we've added the <code>checked</code> attribute to the middle radio button input, so it will be selected 既定では when loaded. We then style this with the following CSS:</p>

<pre class="brush: css notranslate">input ~ span {
  position: relative;
}

input:default ~ span::after {
  font-size: 0.7rem;
  position: absolute;
  content: "Default";
  color: white;
  background-color: black;
  padding: 5px 10px;
  right: -65px;
  top: -3px;
}</pre>

<p>This provides a little "Default" label on the one the was originally selected when the page loaded. Note here we are using the general sibling combinator (<code>~</code>) rather than the adjacent sibling combinator (<code>+</code>) — we need to do this because the <code>&lt;span&gt;</code> does not come right after the <code>&lt;input&gt;</code> in the source order.</p>

<p>See the live result below:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/radios-checked-default.html", '100%', 200)}}</p>

<div class="blockIndicator note">
<p><strong>注</strong>: You can also find the example live on GitHub at <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-default.html">radios-checked-default.html</a> (also see the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/radios-checked-default.html">source code</a>.)</p>
</div>

<p>For the <code>:indeterminate</code> example, we've got no default selected radio button — this is important — if there was, then there would be no indeterminate state to style. We style the indeterminate radio buttons with the following CSS:</p>

<pre class="brush: css notranslate">input[type="radio"]:indeterminate {
  border: 2px solid red;
  animation: 0.4s linear infinite alternate border-pulse;
}

@keyframes border-pulse {
  from {
    border: 2px solid red;
  }

  to {
    border: 6px solid red;
  }
}</pre>

<p>This creates a fun little animated border on the radio buttons, which hopefully indicates that you need to select one of them!</p>

<p>See the live result below:</p>

<p>{{EmbedGHLiveSample("learning-area/html/forms/pseudo-classes/radios-checked-indeterminate.html", '100%', 200)}}</p>

<div class="blockIndicator note">
<p><strong>注</strong>: You can also find the example live on GitHub at <a href="https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-indeterminate.html">radios-checked-indeterminate.html</a> (also see the <a href="https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/radios-checked-indeterminate.html">source code</a>.)</p>
</div>

<div class="blockIndicator note">
<p><strong>注</strong>: You can find an <a href="/ja/docs/Web/HTML/Element/Input/checkbox#Indeterminate_state_checkboxes">interesting example involving <code>indeterminate</code> states</a> on the <code><a href="/ja/docs/Web/HTML/Element/input/checkbox">&lt;input type="checkbox"&gt;</a></code> reference page.</p>
</div>

<h2 id="More_pseudo-classes" name="More_pseudo-classes">その他の疑似クラス</h2>

<p>There are a number of other pseudo-classes of interest, and we don't have space to write about them all in detail here. Let's talk about a few more that you should take the time to investigate.</p>

<p>The following are fairly well-supported in modern browsers:</p>

<ul>
 <li>The {{cssxref(":focus-within")}} pseudo-class matches an element that has received focus or <em>contains</em> an element that has received focus. This is useful if you want a whole form to highlight in some way when an input inside it is focused.</li>
 <li>The {{cssxref(":focus-visible")}} pseudo-class matches focused elements that received focus via keyboard interaction (rather than touch or mouse) — useful if you want to show a different style for keyboard focus compared to mouse (or other) focus.</li>
 <li>The {{cssxref(":placeholder-shown")}} pseudo-class matches {{htmlelement('input')}} and {{htmlelement('textarea')}} elements that have their placeholder showing (i.e. the contents of the <code><a href="/ja/docs/Web/HTML/Attributes/placeholder">placeholder</a></code> attribute) because the value of the element is empty.</li>
</ul>

<p>The following are also interesting, but as yet not well-supported in browsers:</p>

<ul>
 <li>The {{cssxref(":blank")}}<strong> </strong>pseudo-class selects empty form controls. {{cssxref(":empty")}} also matches elements that have no children, like {{HTMLElement("input")}}, but it is more general — it also matches other empty elements like {{HTMLElement("br")}} and {{HTMLElement("hr")}}. <code>:empty</code> has reasonable browser support; the <code>:blank</code> pseudo-class's specification is not yet finished, so it not yet supported in any browser.</li>
 <li>The <code><a href="https://drafts.csswg.org/selectors-4/#user-invalid-pseudo">:user-invalid</a></code> pseudo-class, when supported, will be similar to {{cssxref(":invalid")}}, but with better user experience. If the value is valid when the input receives focus, the element may match <code>:invalid</code> as the user enters data if the value is temporarily invalid, but will only match <code>:user-invalid</code> when the element loses focus. If the value was originally invalid, it will match both <code>:invalid</code> and <code>:user-invalid</code> for the whole duration of the focus. In a similar manner to <code>:invalid</code>, it will stop matching <code>:user-invalid</code> if the value does become valid.</li>
</ul>

<h2 id="Test_your_skills!">Test your skills!</h2>

<p>You've reached the end of this article, but can you remember the most important information? You can find some further tests to verify that you've retained this information before you move on — see <a href="/ja/docs/Learn/Forms/Test_your_skills:_Advanced_styling">Test your skills: Advanced styling</a>.</p>

<h2 id="Summary" name="Summary">まとめ</h2>

<p>This completes our look at UI pseudo-classes that relate to form inputs. Keep playing with them, and create some fun form styles! Next up, we'll move on to something different — <a href="/ja/docs/Learn/Forms/Form_validation">client-side form validation</a>.</p>

<p>{{PreviousMenuNext("Learn/Forms/Advanced_form_styling", "Learn/Forms/Form_validation", "Learn/Forms")}}</p>

<h2 id="In_this_module" name="In_this_module">このモジュール</h2>

<ul>
 <li><a href="/ja/docs/Learn/HTML/Forms/Your_first_HTML_form">初めてのフォーム</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/How_to_structure_an_HTML_form">フォームの構築方法</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/The_native_form_widgets">ネイティブフォームウィジェット</a></li>
 <li><a class="external" href="/ja/docs/Learn/Forms/HTML5_input_types" rel="noopener">The HTML5 input types</a></li>
 <li><a class="external" href="/ja/docs/Learn/Forms/Other_form_controls" rel="noopener">Other form controls</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/Styling_HTML_forms">フォームへのスタイル設定</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/Advanced_styling_for_HTML_forms">フォームへの高度なスタイル設定</a></li>
 <li><a class="external" href="/ja/docs/Learn/Forms/UI_pseudo-classes" rel="noopener">UI pseudo-classes</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/Data_form_validation">フォームデータの検証</a></li>
 <li><a href="/ja/docs/Learn/HTML/Forms/Sending_and_retrieving_form_data">フォームデータの送信</a></li>
</ul>

<h3 id="Advanced_Topics" name="Advanced_Topics">上級トピック</h3>

<ul>
 <li><a class="external" href="/ja/docs/Learn/Forms/How_to_build_custom_form_controls" rel="noopener">カスタムフォームコントロールの作成方法</a></li>
 <li><a class="external" href="/ja/docs/Learn/Forms/Sending_forms_through_JavaScript" rel="noopener">JavaScript によるフォームの送信</a></li>
 <li><a class="external" href="/ja/docs/Learn/Forms/Property_compatibility_table_for_form_widgets" rel="noopener">フォームウィジェット向けプロパティ実装状況一覧</a></li>
</ul>