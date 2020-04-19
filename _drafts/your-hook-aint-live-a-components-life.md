---
layout: blog_post
title: Living as a custom hook in the React world
category: blog
---

As confusing as the title is, the life cycle of my custom hooks confused me a big time.  
If you've ever wondered why `useState` and other hooks / functions wouldn't behave as expected inside a custom hook, this article could shed a light on your confusion.

## the Prelude - hooks
We all remember that inspiring moment when React v16.8 introduced hooks and context API.  
Fascinated by hooks and the new potential of functional components, I immediately started adapting those in my React projects.  

The default hooks, namely `useState`, `useEffect`, `useLayoutEffect`, `useReducer` and `useCallback`, opened a new world to us developers and affected the way we use dependencies like `Redux`; in a good way.  
I literally couldn't complain until I faced the biggest confusion of my React-ish life.  

## enter the Custom hooks
At one point of my hooks journey, I knew I was ready to ditch HOCs(High Order Components) and bring about the new level of DRY(Do not Repeat Yourself). But how? Using the __custom hooks__!  

I enjoyed the initial success and was more than eager to hookerize each and every bit of my React codebase.
___
![hamburger menu animation hook in action, find the code below](/img/portfolio/sigsense_machine_learning.png)  
```javascript
import { useState, useEffect } from 'react';
import { Animated } from 'react-native';
import { Metrics } from '../Themes';

const useMenuAnimation = (isExpanded, fullSize = Metrics.mainMenuWidth) => {
  const [animation] = useState(new Animated.Value(0));

  useEffect(() => {
    if (isExpanded === undefined) {
      animation.setValue(0);
      return;
    }

    let initialValue;
    let finalValue;
    if (isExpanded) {
      initialValue = 0;
      finalValue = fullSize;
    } else {
      initialValue = fullSize;
      finalValue = 0;
    }

    animation.setValue(initialValue);
    Animated.spring(animation, {
      toValue: finalValue
    }).start();
  }, [isExpanded]);

  return [animation];
};

export default useMenuAnimation;

```
Custom hooks were quite intriguing, and I definitely loved the applauds of the teammates who appreciated the smarter sharing of logic between the components.  
