
# CSS - All About Flexbox

<http://preaction.github.io/CSS-All-About-Flexbox/>

<div style="width: 40%; float: left">

by [Doug Bell](http://preaction.me)  
<small>(he, him, his)</small>  
[<i class="fa fa-twitter"></i> @preaction](http://twitter.com/preaction)  
[<i class="fa fa-github"></i> preaction](http://github.com/preaction)  
<img src="http://chicago.pm.org/theme/images/chicagopm-small.png" style="border: none; vertical-align: middle" />
[Chicago.PM](http://chicago.pm.org)  

</div>
<div style="width: 20%; float: left; text-align: center">
<img src="http://preaction.me/images/avatar-small.jpg" style="display: inline-block; max-width: 100%"/>
</div>
<div style="width: 40%; float: left">

[<i class="fa fa-file-text-o"></i> Notes](https://github.com/preaction/CSS-All-About-Flexbox/blob/master/NOTES.md)  
<small> </small>  
[Source on <i class="fa fa-github"></i>](https://github.com/preaction/CSS-All-About-Flexbox/)  

[CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode)  

<small data-markdown>
For navigation help, press `?`  
For speaker view, press `S`  
For full-screen, press `F`
</small>
</div>

------

# Web

---

# HTML

## Web Data

---

# JavaScript

## Web Interactivity

---

# CSS

## Web Design

------

# CSS is Simple

---

# CSS is not Easy

---

# CSS is Evolving

------

# 2000

## Tables

---

# 2008

## Floats

---

# 2016

## Flexbox

------

# Old Solutions

---

# Tables

[View example](table-layout.html)  
[View example outlined](table-layout-outline.html)

---

<pre><code>
&lt;table style="width: 100%"&gt;
    &lt;tr&gt;
        &lt;td colspan="2" class="header"&gt;
            &lt;table style="width: 100%"&gt;
                &lt;tr&gt;
                    &lt;td style="width: 70%"&gt;&lt;h1&gt;Pet Palace&lt;/h1&gt;&lt;/td&gt;
                    &lt;td&gt;&lt;small&gt;
                    1000 Example Road.&lt;br&gt;
                    Chicago, IL 60010&lt;br&gt;
                    (312) 555-0123&lt;br&gt;
                    Open from 10:00 AM to 8:00 PM every day!
                    &lt;/small&gt;&lt;/td&gt;
                &lt;/tr&gt;
            &lt;/table&gt;
        &lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
        &lt;td colspan="2"&gt;
            &lt;a href="#"&gt;Home&lt;/a&gt; | 
            &lt;a href="#"&gt;Blog&lt;/a&gt; |
            &lt;a href="#"&gt;About Us&lt;/a&gt; |
            &lt;a href="#"&gt;Shop&lt;/a&gt; |
        &lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
        &lt;td style="vertical-align: top; width: 80%"&gt;
            &lt;h2&gt;Welcome to our store!&lt;/h2&gt;
            &lt;p&gt;Pet Palace has all your pet needs!&lt;/p&gt;
            &lt;table&gt;
                &lt;tr&gt;
                    &lt;td style="vertical-align: top; width: 50%"&gt;
                        &lt;ul&gt;
                            &lt;li&gt;A wide selection of food for cats, dogs, birds, fish, and more&lt;/li&gt;
                            &lt;li&gt;On-site grooming and boarding services&lt;/li&gt;
                            &lt;li&gt;Veterinary doctor on-call for emergencies&lt;/li&gt;
                        &lt;/ul&gt;
                    &lt;/td&gt;
                    &lt;td style="vertical-align: top; width: 50%"&gt;
                        &lt;ul&gt;
                            &lt;li&gt;Equipment and supplies for salt- and fresh-water fish tanks&lt;/li&gt;
                            &lt;li&gt;Friendly and well-trained staff to answer any questions&lt;/li&gt;
                            &lt;li&gt;Everything you need for your pet's health and well-being&lt;/li&gt;
                        &lt;/ul&gt;
                    &lt;/td&gt;
                &lt;/tr&gt;
            &lt;/table&gt;
        &lt;/td&gt;
        &lt;td style="vertical-align: top; width: 20%"&gt;
            &lt;h4&gt;What's new!&lt;/h4&gt;
            &lt;ul&gt;
                &lt;li&gt;&lt;b&gt;2017-07-04&lt;/b&gt;: We now stock new brands of
                all-natural, high quality cat food!&lt;/li&gt;
                &lt;li&gt;&lt;b&gt;2017-06-30&lt;/b&gt;: Check out our newly-remodelled
                grooming and boarding rooms!&lt;/li&gt;
                &lt;li&gt;&lt;b&gt;2017-06-12&lt;/b&gt;: Puppy parade! Come adopt an
                adorable puppy from the Humane Society today!&lt;/li&gt;
            &lt;/ul&gt;
        &lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
        &lt;td class="footer" colspan="2"&gt;
            &amp;copy; 2017 Pet Palace, LLC
        &lt;/td&gt;
    &lt;/tr&gt;
&lt;/table&gt;
</code></pre>

---

# Floats

[View example](float-layout.html)  
[View example outlined](float-layout-outline.html)

---

<pre><code>
&lt;header class="header"&gt;
    &lt;h1&gt;Pet Palace&lt;/h1&gt;
    &lt;address&gt;1000 Example Road.
        Chicago, IL 60010
        (312) 555-0123
        Open from 10:00 AM to 8:00 PM every day!
    &lt;/address&gt;
&lt;/header&gt;

&lt;nav&gt;
    &lt;ul&gt;
        &lt;li&gt;&lt;a href="#"&gt;Home&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#"&gt;Blog&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#"&gt;About Us&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="#"&gt;Shop&lt;/a&gt;&lt;/li&gt;
    &lt;/ul&gt;
&lt;/nav&gt;

&lt;div class="sidebar"&gt;
    &lt;h4&gt;What's new!&lt;/h4&gt;
    &lt;ul&gt;
        &lt;li&gt;&lt;b&gt;2017-07-04&lt;/b&gt;: We now stock new brands of
        all-natural, high quality cat food!&lt;/li&gt;
        &lt;li&gt;&lt;b&gt;2017-06-30&lt;/b&gt;: Check out our newly-remodelled
        grooming and boarding rooms!&lt;/li&gt;
        &lt;li&gt;&lt;b&gt;2017-06-12&lt;/b&gt;: Puppy parade! Come adopt an
        adorable puppy from the Humane Society today!&lt;/li&gt;
    &lt;/ul&gt;
&lt;/div&gt;

&lt;main&gt;
    &lt;h2&gt;Welcome to our store!&lt;/h2&gt;
    &lt;p&gt;Pet Palace has all your pet needs!&lt;/p&gt;
    &lt;ul class="two-column"&gt;
        &lt;li&gt;A wide selection of food for cats, dogs, birds, fish, and more&lt;/li&gt;
        &lt;li&gt;On-site grooming and boarding services&lt;/li&gt;
        &lt;li&gt;Veterinary doctor on-call for emergencies&lt;/li&gt;
        &lt;li&gt;Equipment and supplies for salt- and fresh-water fish tanks&lt;/li&gt;
        &lt;li&gt;Friendly and well-trained staff to answer any questions&lt;/li&gt;
        &lt;li&gt;Everything you need for your pet's health and well-being&lt;/li&gt;
    &lt;/ul&gt;
&lt;/main&gt;

&lt;footer&gt;
    &amp;copy; 2017 Pet Palace, LLC
&lt;/footer&gt;
</code></pre>

---

<pre><code>
body {
    font: 12pt Verdana, sans-serif;
    margin: 0;
    padding: 0;
}
div {
    margin: 0;
    padding: 0;
}
header, footer {
    background: blue;
    color: white;
}
header h1 {
    float: left;
    width: 70%;
    margin-bottom: 0;
}
header address {
    font-size: 10pt;
    white-space: pre-line;
    font-style: normal;
}
nav {
    clear: both;
    overflow: hidden;
}
nav ul {
    list-style: none;
    margin: 1em;
    padding: 0;
}
nav li {
    float: left;
    list-style: none;
    margin-right: 1em;
}
footer {
    clear: both;
}
.sidebar {
    float: right;
    width: 20%;
}
.two-column li {
    width: 46%;
    float: left;
    margin-left: 2%;
}
.two-column {
    overflow: hidden;
}
.outline * {
    outline: 1px dotted hotpink;
}
</code></pre>

---

# Floats are Weird

[View Example](float-noclear.html)
[View Original](float-layout.html)

---

# Floats are hard

Top FAQ in #css

---

# Floats are not responsive

---

# Grid Libraries

---

# Increased complexity

---

# Flexbox

[View example](flex-layout.html)

---

# Easier

Declare behavior

---

# Responsive

[View example](flex-layout.html)

------

# Flex Basics

---

# Container

---

# Contents on a Line

---

[View example](flex-01.html)

---

# Context

---

# New Rules

------

# Grow/Shrink

---

# Default: Shrink

[View example](flex-02.html)

---

# `flex-shrink`
# `flex-grow`

---

# `flex-shrink: 0`

[View example](flex-03-shrink.html)

---

# `flex-grow: 1`

[View example](flex-04-grow.html)

---

# Values are scale

---

# `flex-grow: 9`

[View example](flex-05-grow-2.html)

---

# `flex-shrink: 6`

[View example](flex-06-shrink-2.html)

------

# Wrap

`flex-wrap`

---

# `flex-wrap: wrap`

[View example](flex-wrap.html)

------

# Justify

---

# `justify-content: center`

[View example](flex-07-justify-1.html)

---

# `justify-content: space-between`
# `justify-content: space-around`

[View example](flex-08-justify-2.html)

---

# Uniform Content

---

# Varying Content

[View example](flex-09-varying.html)

---

# Top/Left

---

# Spread Out

[View example](flex-10-vary-justify.html)

------

# Align

---

# `align-items: center`

[View example](flex-11-align-center.html)

---

# `align-items: flex-end`

[View example](flex-12-align-end.html)

------

# Axes

---

# `flex-start` `flex-end`

---

# `left` `right`
# `top` `bottom`

---

# Flex Direction

---

# Horizontal
# Vertical

---

# Main axis
# Cross axis

---

# Main axis: Horizontal
`flex-direction: row`

---

# Main axis: Vertical
`flex-direction: column`

[View example](flex-13-column.html)

---

# Reverse

`flex-direction: row-reverse`
[View example](flex-14-row-reverse.html)

`flex-direction: column-reverse`
[View example](flex-15-column-reverse.html)

---

# Defaults based on Language

------

# Axes, Justify, and Align

[View Example](flex-column-from-middle.html)

------

# Responsive

[View example](flex-responsive-row.html)

------

# Other Stuff

------

# Order

[View example](flex-order.html)

---

# Good with `@media` queries

[View example](flex-order-layout.html)

------

# Questions?

---

# Thank You

<http://preaction.github.io/CSS-All-About-Flexbox/>

<div style="width: 40%; float: left">

by [Doug Bell](http://preaction.me)  
<small>(he, him, his)</small>  
[<i class="fa fa-twitter"></i> @preaction](http://twitter.com/preaction)  
[<i class="fa fa-github"></i> preaction](http://github.com/preaction)  
<img src="http://chicago.pm.org/theme/images/chicagopm-small.png" style="border: none; vertical-align: middle" />
[Chicago.PM](http://chicago.pm.org)  

</div>
<div style="width: 20%; float: left; text-align: center">
<img src="http://preaction.me/images/avatar-small.jpg" style="display: inline-block; max-width: 100%"/>
</div>
<div style="width: 40%; float: left">

[<i class="fa fa-file-text-o"></i> Notes](https://github.com/preaction/CSS-All-About-Flexbox/blob/master/NOTES.md)  
<small> </small>  
[Source on <i class="fa fa-github"></i>](https://github.com/preaction/CSS-All-About-Flexbox/)  

[CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode)  

</div>

