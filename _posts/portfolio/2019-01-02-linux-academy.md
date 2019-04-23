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
- React
- Ruby on Rails
- ElasticSearch
- Material UI
- Redux
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
- MongoDB
- Redis
- AWS
---

### Client

<a href="http://www.linuxacademy.com" target="_blank">Linux Academy</a>, a training platform for technicians, was in the midst of creating a more performant and maintainable reporting section.  
I was added to the task force, in the hopes that I could help them deliver promptly and meet the deadline.

### Contributions

The team lacked the necessary manpower who could handle newly-built ReactJS code-base.  
Urgency-stricken code-base lacked quality and I could see that it was holding back the productivity of the team big time. It needed some serious surgery.

I worked out a refactoring plan that spanned over 2 weeks and put it into action from day 3.  
For me, it was going an extra mile, and it definitely contributed to the timely delivery of the product.

In the first place, they hired me for the Ruby on Rails back-end. **They were thrilled to have me actively taking lead in the ReactJS front-end as well**, for it being what they needed the most help with.

### Challenges

Material UI is a great library - no doubt in that. But it isn't very customization-friendly.

I had to deal with a lot of difficulties making an Material UI component look exactly the way the design illustrated it.  
Sometimes, I used some elaborate hacks to deliver an aesthetically and egonomically pleasing UI/UX.

For example, to render a table that had a couple of column-grouping braces over the header, I tried 6 different approaches with different drawbacks.  
Finally, I settled with absolutely-positioned child <abbr title="HTML tag">div</abbr>s of the <abbr title="HTML tag for table header">th</abbr>s so they could share the parents' width while overlapping with its peers using z-Index.  

<a href="/blog/2019/02/18/Challenge-And-Solution-2" target="_blank">Check the details of this challenge</a>

### Accomplishments, My lesson

You have to actively communicate with the designers.  
This makes everyone's life easier and keeps the project from being stuck by some insignificant details.

Here's the story.  
The design has a fancy border effect to a component, and I could **finish the component in 8 hours** except that part.  
Now the fancy border is going to eat up more than 4 hours of my precious time.  
Rather than trying hard to do it, I would ask the designer if it really matters. He could say YES, but learning that **4 hours will be spent on this little nuance**, he agrees to reconsider it.

I have learned another lesson in the prioritization of tasks in favor of the bigger picture.  
**Urgency-importance matrix** also helped.
