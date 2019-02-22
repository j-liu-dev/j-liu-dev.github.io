---
layout: default
title: Linux Academy Online Training Platform
category: portfolio
modal-id: 2
img: linux.png
alt: Linux Academy reports page
client: Linux Academy
application: Training Progress Reports
project-date: May 2018 - Sep 2018
tech:
- Angular 5
- Ruby on Rails
- ElasticSearch
- Angular Material
- NgRx
- Karma & Protractor
tools:
- TravisCI
- Docker
- CompoDoc
- Github
concepts:
- Agile
- TDD
- Devops
- Line Organization
stack:
- Linux
- PostgreSQL
- Redis
- AWS
---

### Client

<a href="http://www.linuxacademy.com" target="_blank">Linux Academy</a>, a training platform for technicians, was in the midst of creating a more performant and maintainable reporting section.  
I was added to the task force, in the hopes that I could help them deliver promptly and meet the deadline.

### Contributions

The team lacked the necessary manpower who could handle Angular 5 code-base.  
Urgency-stricken code-base lacked quality and I could see that it was holding back the productivity of the team big time. It needed some serious surgery.

I worked out a refactoring plan that spanned over 2 weeks and put it into action from day 3.  
For me, it was going an extra mile, and it definitely contributed to the timely delivery of the product.

In the first place, they hired me for the Ruby on Rails back-end. **They were thrilled to have me actively taking lead in the Angular front-end as well**, for it being what they needed the most help with.

### Challenges

Angular Material is a great library - no doubt in that. But it isn't very customization-friendly.

I had to deal with a lot of difficulties making an Angular Material component look exactly the way the design illustrated it.  
Sometimes, I used some elaborate hacks to deliver an aesthetically and egonomically pleasing UI/UX.

For example, to render a table that had a couple of column-grouping braces over the header, I tried 6 different approaches with different drawbacks.  
Finally, I settled with absolutely-positioned child <abbr title="HTML tag">div</abbr>s of the <abbr title="HTML tag for table header">th</abbr>s so they could share the parents' width while overlapping with its peers using z-Index.  

<p class="codepen" data-height="265" data-theme-id="0" data-default-tab="result" data-user="zixingliu" data-slug-hash="omVPWK" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid black; margin: 1em 0; padding: 1em;" data-pen-title="MAT - header cells grouping labels">
  <span>See the Pen <a href="https://codepen.io/zixingliu/pen/omVPWK/">
  MAT - header cells grouping labels</a> by Zixing Liu (<a href="https://codepen.io/zixingliu">@zixingliu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
[Check the details of this challenge](/blog/2019/02/18/Challenge-And-Solution-2)

### Accomplishments, My lesson

You have to actively communicate with the designers.  
This makes everyone's life easier and keeps the project from being stuck by some insignificant details.

Here's the story.  
The design has a fancy border effect to a component, and I could **finish the component in 8 hours** except that part.  
Now the fancy border is going to eat up more than 4 hours of my precious time.  
Rather than trying hard to do it, I would ask the designer if it really matters. He could say YES, but learning that **4 hours will be spent on this little nuance**, he agrees to reconsider it.

I have learned another lesson in the prioritization of tasks in favor of the bigger picture.  
**Urgency-importance matrix** also helped.
