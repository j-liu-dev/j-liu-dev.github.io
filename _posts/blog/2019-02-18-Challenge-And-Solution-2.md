---
layout: blog_post
title: Challenge & Solution (CSS)
category: blog
---
Styling-wise, have you ever experienced the dilemma between the pure-CSS solution and Javascript-driven solution?

As a developer, I frequently find myself wondering between the two, especially when the UI needs more than just the conventional CSS rules.  
Recently, while working at <a href="http://www.linuxacademy.com" target="_blank">Linux Academy</a>, I came across one of the most tricky issues in my CSS journey.

Simply put, they wanted an extra bit of decor to their report tables - **grouping braces for table columns**.

<img src="/img/blog/th-grouping-mock.png" alt="Table column grouping braces" width="100%">

Before moving onto my solution, you could also give it a little thought, just for fun.

The easy solution could be :
- Give the <abbr title="Table column header">th</abbr>s fixed width or proportional width
- Attach grouping brace <abbr title="HTML tag">div</abbr>s on top of the table, and sync their width with the <abbr title="Table column header">th</abbr> counter-parts

However, this solution doesn't apply to the scenario of elastic/dynamic column widths.  
In my experience, fixed or proportional column widths are not effective. Try not giving them explicit widths, and you will see how elastic they are on different screen sizes.  
I, as well as the client, wanted the solution that does not rely upon explicit column widths.

I opted to go with a pure-CSS solution. Javascript simply didn't sound right.  
And here's how I visualized the solution.

<img src="/img/blog/css-grouping-brace.png" alt="Table column grouping braces" width="100%">

The colored blocks (from the above figure) were made _absolute_ children of the first columns of the groups.
```
  position: absolute;
  top: -25px;
  background-color: white;
  width: 2000px;
  text-align: left;
```
_2000px_ is a randomly-picked big value that enables the block extend past the right edge of the table.


<p class="codepen" data-height="524" data-theme-id="0" data-default-tab="result" data-user="zixingliu" data-slug-hash="omVPWK" style="height: 524px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid black; margin: 1em 0; padding: 1em;" data-pen-title="MAT - header cells grouping labels">
  <span>See the Pen <a href="https://codepen.io/zixingliu/pen/omVPWK/">
  MAT - header cells grouping labels</a> by Zixing Liu (<a href="https://codepen.io/zixingliu">@zixingliu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

This solution made grouping braces always attached to their corresponding columns no matter what.  
I admit this was a _hack_ and might not be the best solution. Please feel free to message me if you have better ideas.

Cheers!
