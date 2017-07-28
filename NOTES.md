<style>
.outline * {
    outline: 1px dotted hotpink;
}
<%= import 'flex.css' %>
</style>

# Intro

Where HTML is the language of web data, and JavaScript the language of
web interactivity, CSS is the language of web design. CSS makes things
look good.

However, CSS has not always made it easy to look good. Sometimes, it's
been downright impossible. But, necessity is the mother of invention,
and so there have been sub-optimal patterns invented to create things
CSS could not.

As the web has evolved, occupying new territories and disappearing into
every new technology we purchase, so too must the languages for the web.

Over time, CSS has evolved to make the hard things easier and the
impossible things possible. Flexbox is one of those things. Where in the
past we might have used HTML tables or CSS floats to lay out our content
boxes, flexbox makes it possible to align our boxes in rows or columns,
expand them to take up available space, and react to differences in the
device displaying our page.

# Old Solutions

To truly appreciate what Flexbox lets us do, a quick refresher on how it
once was:

## Tables

<%= include 'table-layout.html' %>

This doesn't look so bad, does it? Let's see what it looks like to the web
browser:

<div class="outline">
<%= include 'table-layout.html' %>
</div>

Ouch. There's a lot of stuff here. This stuff all takes time for the browser to
download and render. Worse, because we're using tables extensively, it's going
to be more difficult to edit our page.

## Floats

With CSS and HTML5, we could make this a lot better: Semantic elements
make our page easier to organize, and we can use floats to get our
elements side-by-side.

<%= include 'float-layout.html' %>

This looks approximately the same, but it has a lot less markup.
Instead, more of our page is being controlled by CSS (as it should be).

<pre><code><%= include 'float-layout.html' %></code></pre>

But this still isn't optimal: There are a lot of places where I had to
write `clear: both` and `overflow: hidden`. Without this, the content
would look more like this:

<%= include 'float-noclear.html' %>

This is just one of `float`'s quirks. Float containment is the most
common question we get in the #css IRC channel on Freenode, and is
another topic for a later date. Floats were not meant to be used for
layout, but it was all we had.

So "grid" libraries were invented to try to smooth some of the
complexity and get some responsiveness for smaller devices. That's yet
another topic for a later date. These libraries often use media queries
to achieve responsiveness, increasing their complexity.

# New Solution: Flexbox

Let's see the same site using Flexbox.

It looks pretty similar in the amount of markup we have, and even in the
size of our stylesheet, but our rules are simpler: We add style to what
needs it to achieve a goal, not to fix a problem caused by a different
style.

Also, watch what happens when the browser is resized. The rules we added
make our content wrap and flow to keep everything readable as we get
smaller, without using media queries (which would make our float layout
stylesheet much larger, and I did not have time to do).

# Flex Basics

Flexbox is like much everything else in CSS: It requires some learning.
Too many of the problems I deal with in helping people in CSS boil down
to "this isn't programming, so it should be easy." I can say that CSS is
simple, yes, but not easy. That's what this talk is for.

At its simplest, a flexbox is a container whose contents will
be arranged on a line. This is different from a normal container, whose
content is arranged based on the content's properties. Flexbox
containers impose some changes on their contents, which we'll discuss as
we go. Basically, a flex container is a new context where new rules
apply.

<div class="flex">
    <div></div>
    <div></div>
    <div></div>
</div>

## Grow/Shrink

By default, the flexbox items will shrink to fit if the line is too
small, but they will not grow if the line is too long:

<%= include 'flex-02.html' %>

We can control this with `flex-shrink` and `flex-grow`.

By setting `flex-shrink` to `0` on our items, our items will no longer
shrink and will overflow:

<%= include 'flex-03-shrink.html' %>

If we have only a few items, we can set `flex-grow` to `1` to make them
grow to fill the space.

<%= include 'flex-04-grow.html' %>

These values for `flex-shrink` and `flex-grow` are numbers, not
booleans. If you use larger numbers, it means that the element should
grow/shrink more than the other elements.

For example, I could make the middle element biggest by giving it
`flex-grow: 9`.

<%= include 'flex-05-grow-2.html' %>

Or I could make the first and last elements the smallest by giving them
`flex-shrink: 6`.

<%= include 'flex-06-shrink-2.html' %>

## Wrap

If I don't want things to shrink, I can instead make them wrap with
`flex-wrap: wrap`:

<%= include 'flex-wrap.html' %>

## Justify/Align

On our first example, we had a lot of empty space. The default settings
for a flexbox is to keep everything towards the top/left. But our
content would look better if we could spread it out across the space we
have. To control how extra space is used, we can use the
`justify-content` property.

By setting `justify-content: center`, we can center our items:

<%= include 'flex-07-justify-1.html' %>

But we can also distribute space between our items by using
`justify-content: space-between` and `justify-content: space-around`

<%= include 'flex-08-justify-2.html' %>

Those were simple examples: All of the content has the same
height/width. What happens when our content isn't all the same?

<%= include 'flex-09-varying.html' %>

Here we can see that the default settings for a flexbox is to keep
everything towards the top and left, right next to each other, leaving
all the space on the right. If we make our browser smaller, we can see
that the items will eventually start shrinking, just like before.

We can use the same `justify-content` property as before to achieve some
spacing out:

<%= include 'flex-10-vary-justify.html' %>

### Align

But this only affects their behavior on the horizontal. It would look
much nicer if we could also center them vertically. For this, we have
`align-items`.

We can align all of our items to the center with `align-items: center`:

<%= include 'flex-11-align-center.html' %>

We can align them to the bottom with `align-items: flex-end`:

<%= include 'flex-12-align-end.html' %>

## Axes

I've been saying things like `flex-start` and `flex-end` instead of
`top`, `bottom`, `left`, and `right`. This is because a flex container
has a direction which can be left-to-right, right-to-left, or even
top-to-bottom and bottom-to-top, arranging content in a column instead
of a row.

So, rather than thinking of two axes "horizontal" and "vertical", flex
thinks of two axes as "main axis" and "cross axis". By default, the main
axis is the horizontal, and the cross axis is the vertical. But, by
setting `flex-direction: column`, we can reverse that:

<%= include 'flex-13-column.html' %>

Note how our items don't shrink in the vertical direction. CSS tries to
ensure that all your content is shown and prefers taking up vertical
space to horizontal space. Welcome to the things that make even experts
pull their hair out...

We can even reverse the flow of the row or column by using
`flex-direction: row-reverse` or `flex-direction: column-reverse`:

<%= include 'flex-14-row-reverse.html' %>
<%= include 'flex-15-column-reverse.html' %>

I should also point out that the default direction of a row is the
direction of the current language: If the language is right-to-left, the
default flex direction is right-to-left. Then the reverse direction
would be left-to-right. CSS's support for content languages other than
English continues to improve!

### Axes, Justify, and Align

So, combining all this knowledge, we can precisely control how our items
are rendered:

<%= include 'flex-column-from-middle.html' %>

## Responsiveness

Combining all of these properties can also help us make responsive
elements without using media queries. Media queries allow us to say
"when a screen is smaller than 400px wide, use these CSS rules instead."
Media queries are wonderfully-useful, but can cause a stylesheet to
quickly grow out of control.

Flexbox gives us more options to be responsive without media queries:

<%= include 'flex-responsive-row.html' %>

## Order

Flexbox allows re-ordering content. Normally items have to be in the
same order as in the markup, but we can change that now using CSS:

<%= include 'flex-order.html' %>

