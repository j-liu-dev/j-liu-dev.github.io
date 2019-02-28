---
layout: default
title: uStrive Virtual Mentoring SaaS
category: portfolio
modal-id: 5
img: ustrive.png
alt: Ustrive student dashboard page
client: Strive for College
application: Virtual Mentoring via Mobile Interface
project-date: Jan 2018 - Apr 2018
tech:
- React
- React Native
- Node
- Mobx
- Twilio
concepts:
- Async & Await
- Hybrid
- REST Api
- Scalability
- Porting
tools:
- xCode
- Android Studio
- Trello
- Git
- Postman
stack:
- iOS
- Android
- Parse
---

### Client

The company, <a href="http://www.ustrive.com" target="_blank">Strive for College</a>, hired me to write a React Native app that'd synchronize with its web counterpart.  
The web version was built in React/Redux, and they had a running Node back-end.

My responsibility was to leverage the existing code-base and deliver as soon as possible.

### Contributions

I delivered the RN app in 4 months, single-handedly.

During the process, I integrated Twilio API, so the instant messaging and video calls could be done within the platform.  
The integration was done on the back-end to fit Twilio API in the common API format of the project.

### Challenges

The trickiest thing was maximizing the sharing (reuse) of web code-base.  
One might call it a <abbr title="process of adapting software in an environment for which was not originally written or intended to execute in">porting</abbr>, but **it was way far from <abbr title="process of adapting software in an environment for which was not originally written or intended to execute in">porting</abbr>**.
I decided to do some research before getting my hands dirty, so I could make the best use of the existing code-base. As a result, I was able to base **65%** of the RN app development on shared code.

Technologically, implementing the typing indicator (like Skype) was the most challenging one.  
Twilio API provided such interface, rather implicitly. I did the obvious - put the pieces together to compose a dedicated API endpoint for the typing status.

<img src="/img/portfolio/ustrive-mobile.jpg" alt="Messaging Screen on Ustrive App">

### Accomplishments, My lesson

I could draw a fine line when sharing code between React Web and Native apps.
- Components are not shareable, as they are designed with different underlying engines in mind.
- Component styles are partially shareable.
- Redux state management is almost 100% shareable.

I also learned how to operate well under pressure.  
When the client tries to light you on fire, there's nothing personal. So it's your decision to be stressed out or not.  
Personally, I steer it in a way that positively affects my productivity.

### Testimonial

Sebastian, who managed me directly, commented in his recommendation.
> I can see that Liu has a deep, formal understanding of software development. He employed thoughtful techniques and was very thorough on the project.
